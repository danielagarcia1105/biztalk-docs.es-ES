---
title: Optimizar los grupos de archivos de base de datos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d7fa4c9-e504-4f43-a308-517a4a574c26
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9333a88817e96b52ffe186f0a6a598b225ef5202
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
ms.locfileid: "26010701"
---
# <a name="optimizing-filegroups-for-the-databases"></a>Optimizar los grupos de archivos para las bases de datos
Archivo de entrada/salida contención (E/S) suele ser un factor limitador o cuello de botella en un entorno de BizTalk Server de producción. BizTalk Server es una aplicación de uso intensivo de la parte de la base de datos y a su vez, la base de datos de SQL Server que utiliza BizTalk Server es intensivo de E/S de archivo muy. En este tema se describe cómo realizar un uso óptimo de los archivos y la característica de grupos de archivos de SQL Server para minimizar la aparición de contención de E/S de archivo y mejorar el rendimiento general de una solución de BizTalk Server.  
  
## <a name="overview"></a>Información general  
 Cada solución de BizTalk Server finalmente experimentarán contención de E/S de archivo tal y como se aumenta el rendimiento. El subsistema de E/S o el motor de almacenamiento, es un componente clave de cualquier base de datos relacional. Una implementación correcta de base de datos suele requerir un diseño cuidadoso en las primeras etapas de un proyecto. Este planeamiento o diseño debería tener en cuenta lo siguiente:  
  
-   El tipo de disco que se va a utilizar, por ejemplo, los dispositivos RAID (matriz redundante de discos independientes). 
  
-   Cómo distribuir los datos en los discos que utilizan archivos y grupos de archivos. Para obtener más información acerca del uso de archivos y grupos de archivos en SQL Server, vea [archivos de base de datos y grupos de archivos](https://docs.microsoft.com/sql/relational-databases/databases/database-files-and-filegroups).
  
-   Implementar el diseño de índices óptimo para mejorar el rendimiento al obtener acceso a datos. Para obtener más información sobre el diseño de índices, vea [diseñar índices](https://docs.microsoft.com/sql/relational-databases/sql-server-index-design-guide).
  
-   Cómo establecer parámetros de configuración de SQL Server para obtener un rendimiento óptimo. Para obtener más información acerca de cómo establecer los parámetros de configuración óptima para SQL Server, vea [opciones de configuración de servidor](https://docs.microsoft.com/sql/database-engine/configure-windows/server-configuration-options-sql-server).
  
 Uno de los objetivos principales de diseño de BizTalk Server es asegurarse de que un mensaje es **nunca** perdido. Con el fin de reducir la posibilidad de pérdida de mensajes, los mensajes se escriben con frecuencia en la base de datos de cuadro de mensajes cuando se procesa el mensaje. Cuando se procesan los mensajes por una orquestación, el mensaje se escribe en la base de datos de cuadro de mensajes en cada punto de persistencia en la orquestación. Estos puntos de persistencia hacer que el cuadro de mensajes escribir el mensaje y el estado relacionado en el disco físico. En un mayor rendimiento, esta persistencia puede dar lugar a la contención de disco considerable y podría convertirse en un cuello de botella.  
  
 Lo óptimo el uso de los archivos y resolver los cuellos de botella de E/S de archivos de forma efectiva y mejorar el rendimiento general en soluciones de BizTalk Server haya demostrado característica de grupos de archivos de SQL Server.  
  
> [!NOTE]  
>  Esta optimización solo debe realizarse por un administrador experimentado de base de datos de SQL Server y solo después todas las bases de datos de BizTalk Server se han realizado copias correctamente una. Esta optimización debe realizarse en todos los equipos de SQL Server en el entorno de BizTalk Server.  
  
 Archivos y grupos de archivos de SQL Server pueden usarse para mejorar el rendimiento de la base de datos porque esta funcionalidad permite una base de datos se crea en varios discos, varios controladores de disco o RAID de sistemas (matriz redundante de discos independientes). Por ejemplo, si su equipo tiene cuatro discos, puede crear una base de datos que contenga tres archivos de datos y un archivo de registro, y mantener un archivo en cada disco. Tal y como se tiene acceso a datos, cuatro cabezales de lectura/escritura al mismo tiempo pueden tener acceso a los datos en paralelo. Esto acelera significativamente las operaciones de base de datos. Para obtener más información acerca de cómo implementar soluciones de hardware para discos de SQL Server, vea [base de datos de rendimiento](http://go.microsoft.com/fwlink/?LinkID=71419) (http://go.microsoft.com/fwlink/?LinkID=71419) en los libros en pantalla de SQL Server.  
  
 Además, los archivos y grupos de archivos Habilitar selección de ubicación de datos, porque se pueden crear tablas en grupos de archivos específicos. Esto mejora el rendimiento, dado que todas las E/S de archivo para una tabla específica pueden dirigirse a un disco concreto. Por ejemplo, una tabla de usa muy elevado puede colocarse en un archivo en un grupo de archivos ubicado en un disco, y las otras tablas menos utilizadas de la base de datos se pueden ubicar en distintos archivos de otro grupo de archivos, ubicado en un segundo disco.  
  
 Los cuellos de botella de E/S de archivos se tratan detalladamente considerable en [cuellos de botella en el nivel de base de datos](../technical-guides/bottlenecks-in-the-database-tier.md). El indicador más comunes que la E/S de archivo (E/S de disco) es un cuello de botella es el valor del contador de "Longitud de cola de físico: promedio de disco disco". Cuando el valor del contador de "Longitud de cola de físico: promedio de disco disco" es mayor que 3 para cualquier disco determinado en cualquiera de los equipos que ejecutan SQL Server, E/S de archivos es probable que un cuello de botella.  
  
 Si la aplicación de optimización de archivos o no resuelve un problema de cuello de botella de E/S de archivos, puede ser necesario aumentar el rendimiento del subsistema del disco mediante la adición de física adicional o unidades de SAN.  
  
 Este tema describe cómo aplicar manualmente las optimizaciones de file y filegroup, pero estas optimizaciones también pueden incluirse en scripts. Una secuencia de comandos SQL de ejemplo se proporciona en [Script SQL de grupos de archivos de base de datos de cuadro de mensajes de BizTalk Server](../technical-guides/biztalk-server-messagebox-database-filegroups-sql-script.md).  
  
> [!NOTE]  
>  Es importante tener en cuenta que este script deba modificarse para alojar el archivo, el grupo de archivos y la configuración del disco utilizado por las bases de datos de SQL Server para cualquier solución de BizTalk Server determinado.  
  
> [!NOTE]  
>  En este tema también describe cómo crear varios archivos y grupos de archivos de la base de datos de BizTalk MessageBox. Para obtener una lista exhaustiva de recomendada y grupos de archivos para todas las bases de datos de BizTalk Server, consulte el "Apéndice B" de la [optimización de base de datos de BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=101578) notas del producto (http://go.microsoft.com/fwlink/?LinkID=101578).  
  
> [!NOTE]  
>  Aunque la [optimización de base de datos de BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=101578) notas del producto (http://go.microsoft.com/fwlink/?LinkID=101578) se ha redactado teniendo [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] en mente, se aplican los mismos principios a BizTalk Server.  
  
## <a name="databases-created-with-a-default-biztalk-server-configuration"></a>Bases de datos creadas con un valor predeterminado de configuración de BizTalk Server  
 Dependiendo de qué características están habilitadas al configurar BizTalk Server, hasta 13 diferentes bases de datos se puede crear en SQL Server y todas las bases de datos se crean en el grupo de archivos predeterminado. El grupo de archivos predeterminado para SQL Server es el grupo de archivos principal, a menos que se cambie el grupo de archivos predeterminado mediante el comando ALTER DATABASE. En la tabla siguiente se enumera las bases de datos que se crean en SQL Server si todas las características están habilitadas al configurar BizTalk Server.  
  
### <a name="biztalk-server-databases"></a>Bases de datos de BizTalk Server  
  
||||  
|-|-|-|  
|**Base de datos**|**Nombre de base de datos predeterminada**|**Description**|  
|Base de datos de configuración|BizTalkMgmtDb|Almacenar la central de metainformación para todas las instancias del servidor BizTalk Server en el grupo de BizTalk Server.|  
|Base de datos de BizTalk MessageBox|BizTalkMsgBoxDb|Almacena los predicados de suscripción. Es una plataforma de host y mantiene las colas y tablas de estado para cada host de BizTalk Server. La base de datos de cuadro de mensajes también almacena los mensajes y sus propiedades.|  
|Base de datos de seguimiento de BizTalk|BizTalkDTADb|Almacena económicos y mantenimiento de datos de seguimiento por el motor de seguimiento de BizTalk Server.|  
|Base de datos de análisis de BAM|BAMAnalysis|Base de datos de SQL Server Analysis Services que mantiene los datos históricos de las actividades económicas.|  
|Base de datos de esquema de estrella de SAE|BAMStarSchema|Transforma los datos recopilados de supervisión de la actividad de negocio para el procesamiento OLAP. Esta base de datos es necesario cuando se utiliza la base de datos de análisis de BAM.|  
|Base de datos de importación principal de BAM|BAMPrimaryImport|Almacena los eventos de actividades económicas y, a continuación, las consultas para el progreso y los datos después de instancias de actividad. Esta base de datos también realiza agregaciones en tiempo real.|  
|Base de datos de archivo SAE|BAMArchive|Almacena los predicados de suscripción. La base de datos de archivo de BAM minimiza la acumulación de datos de la actividad económica en la base de datos de importación principal de BAM.|  
|base de datos de SSO|SSODB|Almacena la configuración de forma segura información para las ubicaciones de recepción. Almacena la información para SSO afiliadas aplicaciones, así como las credenciales de usuario cifradas a todas las aplicaciones afiliadas.|  
|Base de datos del motor de reglas|BizTalkRuleEngineDb|Repositorio de:<br /><br /> -Directivas, que son conjuntos de reglas relacionadas.<br />-Vocabularios, que son colecciones de nombres descriptivos y específico de dominio para referencias de datos de reglas.|  
|Base de datos EDI base de BizTalk|BizTalkEDIDb|Almacena datos de procesamiento y seguimiento de documentos EDI.|  
|Base de datos de administración de Servicios de flujo de trabajo de usuarios|BizTalkHwsDb|Almacena información administrativa necesaria para los servicios de flujo de trabajo de usuarios de BizTalk.|  
|base de datos de administración de socios comerciales|TPM|Almacenes de datos de socios comerciales de servicios de actividad de negocio (BAS).|  
|Base de datos de administración de servidor de análisis de seguimiento|BizTalkAnalysisDb|Almacena los cubos OLAP de supervisión de estado y de negocios.|  
  
## <a name="separation-of-data-files-and-log-files"></a>Separación de los archivos de datos y archivos de registro  
 Como se indicó anteriormente, un valor predeterminado de configuración de BizTalk Server coloca la base de datos de cuadro de mensajes en un único archivo en el grupo de archivos predeterminado. De manera predeterminada, los registros de transacciones y de datos para la base de datos de cuadro de mensajes se colocan en la misma unidad y ruta de acceso. Esto se hace para dar cabida a sistemas con un único disco. La configuración de una único archivo o grupo de archivos/disco es **no óptimo** en un entorno de producción. Para obtener un rendimiento óptimo, se deben colocar los archivos de datos y archivos de registro en discos independientes.  
  
> [!NOTE]  
>  Los archivos de registro nunca forman parte de un grupo de archivos. El espacio del registro se administra de forma independiente del espacio de datos.  
  
## <a name="the-8020-rule-of-distributing-biztalk-server-databases"></a>La regla 80/20 de distribuir las bases de datos de BizTalk Server  
 El origen principal de contención en la mayoría de soluciones de BizTalk Server, ya sea debido a la contención de E/S de disco o contención de base de datos, es la base de datos de cuadro de mensajes de BizTalk Server. Esto es cierto en escenarios único y múltiple de cuadro de mensajes. Es razonable suponer que siempre que el 80% del valor de la distribución de las bases de datos de BizTalk se derivan de optimizar los archivos de datos de cuadro de mensajes y el archivo de registro. El escenario de ejemplo que se detallan a continuación, se centra en optimizar los archivos de datos para una base de datos de cuadro de mensajes. A continuación, pueden seguir estos pasos para otras bases de datos según sea necesario. Por ejemplo, si la solución requiere seguimiento extensa, también se puede optimizar la base de datos de seguimiento.  
  
## <a name="manually-adding-files-to-the-messagebox-database-step-by-step"></a>Agregar manualmente archivos de la base de datos de cuadro de mensajes, paso a paso  
 Esta sección del tema describen los pasos que pueden seguirse para agregar manualmente archivos de la base de datos de cuadro de mensajes. En este ejemplo se agregan tres grupos de archivos y, a continuación, se agrega un archivo para cada grupo de archivos para distribuir los archivos para el cuadro de mensajes en varios discos.
  
### <a name="manually-adding-files-to-the-messagebox-database-on-sql-server"></a>Agregar manualmente archivos de la base de datos de cuadro de mensajes en SQL Server
   
1.  Abra **SQL Server Management Studio** para mostrar la **conectar al servidor** cuadro de diálogo.  
  
     ![Pantalla de inicio de sesión de SQL Server](../technical-guides/media/sqlserver2008r2-loginscreen.gif "SQLServer2008R2-Loginscreen")  
  
2.  En el **nombre del servidor** cuadro de edición de la **conectar al servidor** diálogo cuadro, escriba el nombre de la instancia de SQL Server que aloja las bases de datos de cuadro de mensajes de BizTalk Server y haga clic en **conectar** para mostrar de SQL Server Management Studio. En el **Explorador de objetos** panel de SQL Server Management Studio, expanda **bases de datos** para ver las bases de datos para esta instancia de SQL Server.  
  
     ![SQL Server 2005 Management Studio, Explorador de objetos](../technical-guides/media/81f13912-fedc-48c3-9669-c18863e637b1.gif "81f13912-fedc-48c3-9669-c18863e637b1")  
  
3.  Haga clic en la base de datos que se va a agregar los archivos y, a continuación, haga clic en **propiedades** para mostrar la **propiedades de la base de datos** cuadro de diálogo de la base de datos.  
  
     ![Cuadro de diálogo de propiedades de la base de datos de SQL Server 2005](../technical-guides/media/82ae7c11-5b3a-4312-876c-70876abdd65c.gif "82ae7c11-5b3a-4312-876c-70876abdd65c")  
  
4.  En el **propiedades de la base de datos** cuadro de diálogo, seleccione la **grupos de archivos** página. Para crear grupos de archivos adicionales para las bases de datos de BizTalkMsgBoxDb, haga clic en **agregar** . En el ejemplo siguiente, se agregan tres grupos de archivos adicionales.  
  
     ![SQL Server 2005, agregar grupos de archivos a una base de datos](../technical-guides/media/6be47c0e-06c3-45d9-bce2-a42453da7d19.gif "6be47c0e-06c3-45d9-bce2-a42453da7d19")  
  
5.  En el cuadro de diálogo **Propiedades de la base de datos** , seleccione la página **Archivos** .  
  
     Para crear archivos adicionales para agregar a los grupos de archivos, haga clic en **agregar** y, a continuación, haga clic en **Aceptar**. La base de datos de cuadro de mensajes ahora se distribuye en varios discos, lo que le proporcionará una importante ventaja de rendimiento respecto a una configuración de uno de los discos.  
  
     En el ejemplo siguiente, se crea un archivo para cada uno de los grupos de archivos creada con anterioridad y se coloca cada archivo en un disco independiente.  
  
     ![SQL Server 2005, agregar archivos a un grupo de archivos](../technical-guides/media/d5d5c5df-d483-4f01-8128-f98228de51b9.gif "d5d5c5df-d483-4f01-8128-f98228de51b9")  
  
## <a name="sample-sql-script-for-adding-filegroups-and-files-to-the-biztalk-messagebox-database"></a>Script SQL de ejemplo para agregar grupos de archivos y archivos de la base de datos de BizTalk MessageBox  
 Esta guía incluye una secuencia de comandos SQL para agregar grupos de archivos y archivos de la base de datos de cuadro de mensajes de BizTalk Server.  
  
> [!NOTE]  
>  Dado que SQL Server se escribe en los archivos de registro secuencialmente, no hay ninguna ventaja de rendimiento realizada mediante la creación de varios archivos de registro para una base de datos de SQL Server.  
  
 Para ejecutar este script, siga estos pasos:  
  
1.  Abra **SQL Server Management Studio** para mostrar la **conectar al servidor** cuadro de diálogo.  
  
2.  En el **nombre del servidor** cuadro de edición de la **conectar al servidor** diálogo cuadro, escriba el nombre de la instancia de SQL Server que aloja las bases de datos de cuadro de mensajes de BizTalk Server y haga clic en **conectar** para mostrar el cuadro de diálogo de SQL Server Management Studio.  
  
3.  En SQL Server Management Studio, haga clic en el **archivo** menú, elija **New**y, a continuación, haga clic en **consulta con conexión actual** para iniciar el Editor de consultas de SQL.  
  
4.  Copie el script de ejemplo de [Script SQL de grupos de archivos de base de datos de cuadro de mensajes de BizTalk Server](../technical-guides/biztalk-server-messagebox-database-filegroups-sql-script.md) en el Editor de consultas.  
  
5.  Edite los parámetros en el script para que coincida con el entorno de BizTalk Server y ejecute el script.  
  
 La ventaja de secuencias de comandos es que las secuencias de comandos pueden realizar varias tareas rápidamente, se pueden reproducir con precisión y reducirán la posibilidad de que se produzcan errores humanos. La desventaja de secuencias de comandos es que la ejecución de una secuencia de comandos incorrecta puede provocar problemas graves que podrían requerir las bases de datos de BizTalk Server para volver a configurarse desde el principio.  
  
> [!IMPORTANT]  
>  Es de máxima importancia que secuencias de comandos SQL como la secuencia de comandos de ejemplo en esta guía se ha probado exhaustivamente antes de que se está ejecutando en un entorno de producción.  
  
## <a name="see-also"></a>Vea también  
 [Optimización del rendimiento de la base de datos](../technical-guides/optimizing-database-performance.md)