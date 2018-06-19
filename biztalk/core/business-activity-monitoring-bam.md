---
title: La actividad económica (BAM) de supervisión | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, tools
- utilities, Tracking Profile Deployment Utility
- BAM, deployment process
- BAM
- BAM, presentation layers
- BAM, Tracking Profile Deployment utility
- BAM, about BAM
- BAM, data storage
- BAM Management utility
- Tracking Profile Deployment utility
- BAM, runtime process
- BAM, design time
- BAM, data insertion
- BAM, data consumption
- BAM, BAM Management utility
- BAM, processing
ms.assetid: a8ad48b1-6891-4bbb-b125-27d224e49293
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fea5ce33dddc0f40eaabd6ef34e6035e50c9fab9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234788"
---
# <a name="business-activity-monitoring-bam"></a>Supervisión de la actividad económica (SAE)
El diagrama siguiente muestra la arquitectura de la característica Supervisión de la actividad económica (BAM).  
  
 ![](../core/media/architecture-bam-01.gif "architecture_bam_01")  
  
## <a name="tools"></a>Herramientas  
 Puede usar las siguientes herramientas para diseñar, desarrollar e implementar soluciones de BizTalk que se integren con BAM.  
  
-   **Microsoft Excel**. El complemento BAM para Excel proporciona una interfaz de usuario que guía a los analistas de negocios durante la creación de actividades y vistas. Excel sirve como herramienta de diseño para los analistas de negocios y como herramienta de consumo de datos para los usuarios empresariales. Para obtener más información sobre el complemento de BAM para Excel, vea [requisitos para usar el complemento de BAM para Excel](../core/requirements-for-using-the-bam-add-in-for-excel.md).  
  
-   **Utilidad de administración de BAM**. La utilidad de administración de BAM es una herramienta de implementación que permite implementar en la empresa las definiciones de BAM creadas en Excel. Esta utilidad crea las bases de datos de SQL Server, los cubos de Analysis Services, las bases de datos de Servicios de notificación de SQL y las tareas DTS o SSIS necesarias (según la versión de SQL Server instalada). Para obtener más información acerca del Administrador de BAM, consulte [utilidad de administración de BAM](../core/bam-management-utility.md).  
  
-   **Editor de perfiles de seguimiento**. El Editor de perfiles de seguimiento permite a los programadores de BizTalk asignar los elementos de datos definidos por los analistas de negocios en la implementación de BizTalk, incluidas las orquestaciones y la mensajería. Para obtener más información sobre el Editor de perfiles de seguimiento, vea [Editor de perfiles de seguimiento](../core/tracking-profile-editor.md).  
  
-   **Utilidad de implementación de perfil de seguimiento**. La utilidad de implementación de perfiles de seguimiento permite a los profesionales de TI implementar perfiles de seguimiento nuevos y actualizados en la infraestructura de BAM. Para obtener más información acerca de la herramienta de implementación de perfiles de seguimiento, vea [utilidad de implementación de perfiles de seguimiento](../core/tracking-profile-deployment-utility.md).  
  
## <a name="presentation"></a>Presentación  
 La capa de presentación consta de lo siguiente:  
  
-   **Portal de BAM**. El portal de BAM en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona visibilidad en tiempo real, to-end a un proceso empresarial. Es una característica basada en web que consta de una colección de páginas ASP .NET. Puede personalizar BAM para mejorar el rendimiento y la experiencia de los usuarios. Para obtener más información sobre el Portal de BAM, consulte [Portal de BAM](../core/bam-portal.md).  
  
-   **Microsoft Excel**. El complemento BAM para Excel proporciona una interfaz de usuario que guía a los analistas de negocios durante la creación de actividades y vistas. Excel sirve como herramienta de diseño para los analistas de negocios y como herramienta de consumo de datos para los usuarios empresariales. Para obtener más información sobre el complemento de BAM para Excel, vea [requisitos para usar el complemento de BAM para Excel](../core/requirements-for-using-the-bam-add-in-for-excel.md).  
  
-   **Interfaz de usuario personalizada**. Los ISV y programadores pueden crear aplicaciones personalizadas que muestren los datos de BAM.  
  
## <a name="processing"></a>Procesamiento  
 La capa de procesamiento consta de lo siguiente:  
  
-   **Servicio Web de administración de BAM**. La aplicación del portal de BAM usa este servicio web para comunicarse con las tablas de importación principal (PIT) de BAM. La comunicación con la base de datos se realiza a través de credenciales suplantadas almacenadas en el Registro que se crean durante la configuración. Los clientes personalizados pueden usar los métodos expuestos por este servicio web para obtener vistas y los detalles correspondientes, además de actividades relacionadas y diseños de tabla dinámica para cualquier usuario. Los métodos también se pueden usar para administrar alertas en la base de datos.  
  
-   **Bus de eventos** . El servicio de bus de eventos BAM procesa los datos de seguimiento (secuencias) almacenados en una base de datos de origen y los guarda con formato de tabla de consulta en la base de datos de destino.  
  
-   **Servicios de notificación SQL**. Los servicios de notificación SQL evalúan las alertas de instancias y agregados de BAM que define el usuario empresarial.  
  
 El diagrama siguiente muestra los procesos físicos subyacentes de la arquitectura de BAM.  
  
 ![](../core/media/architecture-bam-02.gif "architecture_bam_02")  
  
## <a name="design-time-experience"></a>Experiencia en tiempo de diseño  
 El diagrama siguiente muestra la experiencia en tiempo de diseño.  
  
 ![](../core/media/architecture-bam-03.gif "architecture_bam_03")  
  
 Los pasos siguientes describen la secuencia que se muestra en la ilustración de arriba.  
  
1.  El Editor de perfiles de seguimiento considera que BizTalk Server se ha configurado, que ya se ha implementado al menos una definición de BAM (con BM.exe) y que se ha creado la infraestructura, incluida la base de datos de importación principal. El Editor de perfiles de seguimiento utiliza una clave del Registro establecida durante la configuración de BizTalk para determinar la ubicación en la que se encuentra la base de datos de administración.  
  
    1.  BAM enumera las actividades de la base de datos de importación principal cuando se detecta. Los programadores de BizTalk seleccionan las actividades implementadas que se extraen de la base de datos de importación principal de BAM.  
  
    2.  El programador de BizTalk asigna éstas a una implementación física. Para ello, examina los ensamblados implementados que se recuperan de la base de datos de administración de BizTalk.  
  
    3.  Una vez que el programador las ha asignado visualmente a los artefactos de BizTalk, se envían metadatos al tiempo de ejecución de BizTalk Server para recopilar y almacenar los datos. Esto se realiza mediante anotaciones (para la información de mensajería usada para descodificar los datos recopilados) y el perfil de seguimiento (utilizado para recuperar los datos de tiempo de ejecución).  
  
2.  Microsoft Excel se usa como herramienta en tiempo de diseño y como herramienta de consumo de datos o de presentación. La experiencia de Excel en tiempo de diseño permite a los usuarios crear una definición de BAM mediante la creación de actividades y vistas de BAM. También permite crear los controles y gráficos dinámicos que se muestran posteriormente en el portal de BAM.  
  
## <a name="deployment"></a>Implementación  
 Hay dos categorías de implementación:  
  
-   Crear la infraestructura dinámica  
  
-   Instrumentar el tiempo de ejecución para recopilar datos  
  
 El siguiente diagrama ilustra la implementación de BAM.  
  
 ![](../core/media/architecture-bam-04.gif "architecture_bam_04")  
  
 Los pasos siguientes describen la secuencia que se muestra en la ilustración de arriba.  
  
1.  Se utiliza la utilidad de administración de BAM para crear la infraestructura dinámica. Mediante la definición de BAM o un libro Excel en tiempo de diseño, más el archivo XML de configuración de BAM, la utilidad de administración de BAM crea todas las bases de datos necesarias y las tareas DTS o SSIS correspondientes que el sistema necesita para el funcionamiento.  
  
    1.  Se crean la base de datos de importación principal de BAM y todos los procedimientos almacenados, desencadenadores y tareas DTS o SSIS complementarios.  
  
    2.  Se define la base de datos de archivo de BAM, pero no se crea hasta que se ejecuta la tarea DTS o SSI de archivo.  
  
    3.  Se establece la base de datos de esquema de estrella de BAM si se definieron agregaciones OLAP de BAM. Puede determinar si se han definido agregaciones si el **agregación en tiempo Real** botón en la hoja de cálculo de Excel está deshabilitado o **si CreateOlapCube** está establecido en **true** en la definición de BAM y el archivo de configuración XML tiene una unidad de implementación para **AnalysisDatabase**.  
  
    4.  La definición de BAM y el archivo XML de configuración tienen que tener definida una agregación que no sea en tiempo real (ATR) para que se cree un cubo OLAP de BAM.  
  
    5.  La vista seccionada del proceso del administrador de BAM muestra que se llama al proceso Servicios de notificación (nsontrol.exe) para crear las bases de datos de NS de SQL.  
  
2.  La interfaz de usuario del Editor de perfiles de seguimiento tiene un comando de implementación que instrumenta el tiempo de ejecución para hacer un seguimiento y descodificar los datos de los sistemas en tiempo de ejecución. En este caso, inserta **anotaciones** en la base de datos de importación principal de BAM (si se extraen datos del sistema de mensajería). Se inserta un perfil de seguimiento en la base de datos de administración de BizTalk que utiliza el tiempo de ejecución de BizTalk para determinar los datos que se van a publicar en el sistema de BAM.  
  
3.  La herramienta de línea de comandos de implementación de seguimiento de BizTalk permite publicar perfiles de seguimiento en la base de datos de importación principal y en la base de datos de administración de BAM, que es similar a lo que hace el Editor de perfiles de seguimiento; sin embargo, esta herramienta de línea de comandos no es compatible con funciones de asignación.  
  
## <a name="data-consumption"></a>Consumo de datos  
 Por consumo de datos se entiende el proceso en el que un usuario empresarial consume la información recopilada por la infraestructura de BAM. En ese momento se considera que: 1) la definición de BAM se ha creado (define los datos que se van a recopilar y cómo verlos), 2) la definición de BAM se ha implementado (crea dinámicamente la infraestructura) y 3) la definición de BAM se ha asignado a la implementación física (define la ubicación en la que se recopilan los datos y, en algunos casos, escribe código para la inserción en el sistema).  
  
 El diagrama siguiente ilustra el proceso de consumo de datos.  
  
 ![](../core/media/architecture-bam-05.gif "architecture_bam_05")  
  
 Los pasos siguientes describen la secuencia que se muestra en la ilustración de arriba.  
  
1.  El portal de BAM se divide en dos procesos: el proceso de Internet Explorer y el proceso del portal Web de BAM alojado en los Servicios de Internet Information Server.  
  
    1.  Internet Explorer usa el contexto de seguridad del usuario de negocio que se conecta al sitio web del Portal de BAM. El sitio web del Portal de BAM es una aplicación ASPX que usa el Servicio web de administración de BAM para recopilar información.  
  
    2.  El Portal de BAM llama al servicio Web de administración de BAM para recuperar información; por ejemplo, las actividades o vistas de BAM que el usuario empresarial concreto puede ver. Es importante que el Servicio web de administración de BAM pueda hacerse pasar por el usuario de negocio, por lo tanto, la implementación típica es que el Portal de BAM y el Servicio web se alojen en el mismo equipo.  
  
        > [!NOTE]
        >  Si en la empresa se admite el uso de Kerberos y se configura Active Directory para utilizar las características de delegación, el portal y el servicio Web de BAM pueden estar en equipos diferentes.  
  
    3.  El servicio Web llama a procedimientos almacenados en la base de datos de importación principal de BAM para realizar comprobaciones de seguridad y recuperar metadatos e información acerca de agregaciones en tiempo real de BAM.  
  
        > [!NOTE]
        >  Actualmente el Portal de BAM utiliza un servicio Web no documentado denominado el **servicio Web de consulta**. Este servicio no es compatible y probablemente se deje de utilizar en la próxima versión.  
  
    4.  Internet Explorer aloja Office Web Controls (OWC), que permite realizar conexiones directas a los cubos de Analysis Services de BAM.  
  
2.  Excel  
  
## <a name="runtime"></a>Tiempo de ejecución  
 Después de que la definición de BAM se haya definido, la infraestructura se haya creado y el programador haya instrumentado los sistemas necesarios para habilitar la visibilidad, los datos pueden empezar a circular por el sistema.  
  
### <a name="data-insertion"></a>Inserción de datos  
 Una de las formas principales de permitir el flujo de datos en los sistemas de BAM es a través del Servicio de BizTalk (BTSNTSvc.exe). La arquitectura del Servicio de BizTalk está diseñada de modo que puede contener subsistemas lógicos.  
  
 En el diagrama siguiente se muestra este proceso.  
  
 ![](../core/media/architecture-bam-06.gif "architecture_bam_06")  
  
 Los pasos siguientes describen la secuencia que se muestra en la ilustración de arriba.  
  
1.  Un subsistema aloja el propio motor de BizTalk Server. El motor es responsable de ejecutar las orquestaciones y la mensajería.  
  
2.  Otro subsistema es el servicio de bus de eventos. Este servicio se encarga de escribir datos de secuencias de eventos almacenados en búfer en la base de datos de importación principal de BAM.  
  
### <a name="booting-the-runtime"></a>Iniciar el tiempo de ejecución  
 Cuando se inicia el Servicio de BizTalk, cada subsistema carga los metadatos necesarios para el funcionamiento del sistema.  
  
 En el diagrama siguiente se muestra este proceso.  
  
 ![](../core/media/architecture-bam-07.gif "architecture_bam_07")  
  
 Los pasos siguientes describen la secuencia que se muestra en la ilustración de arriba.  
  
1.  Cuando el motor de BizTalk está en ejecución (bien con orquestaciones o mensajería), llama a interceptores que regulan el flujo de datos desde el motor a BAM. Cuando el motor llama al interceptor, el interceptor analiza la ubicación en la que se encuentra el motor con relación al orden de ejecución de la orquestación o los artefactos de mensajería. Si hay datos que es necesario recuperar de la ubicación en la que se está ejecutando actualmente el motor, el interceptor recopila los datos apropiados. Los metadatos que determinan dónde es necesario capturar los datos y qué datos es necesario capturar se encuentran en el perfil de seguimiento. Durante el inicio del Servicio de BizTalk, los interceptores del motor se pondrán en contacto con la base de datos de administración de BizTalk para extraer el perfil de seguimiento adecuado para los artefactos que se estén ejecutando.  
  
2.  La función principal del servicio de bus de eventos es convertir los BLOB de datos (escritos por el motor de BizTalk) en elementos de datos utilizables e insertar los datos en la base de datos de importación principal de BAM. El interceptor de mensajería escribe los datos sin procesar en un formato comprimido. Para ello, se evita utilizar un espacio de trabajo de memoria grande. Para que el servicio de bus de eventos convierta los datos de mensajería en elementos de datos utilizables, primero debe cargar metadatos que puedan interpretar los datos sin procesar. Estos metadatos se conocen como **anotaciones**. Los metadatos de anotaciones se colocan ahí mediante el Editor de perfiles de seguimiento o la herramienta de línea de comandos de implementación de perfiles de seguimiento. Si la solución implementada no recupera datos de mensajería, no habrá ninguna anotación. Los interceptores de orquestación codifican suficiente información en formato sin procesar para el servicio de bus de eventos con el fin de realizar correctamente la descodificación sin anotaciones adicionales.  
  
### <a name="storing-data"></a>Almacenar datos  
 En esta sección se describe cómo se capturan datos del Servicio de BizTalk.  
  
 En el diagrama siguiente se muestra este proceso.  
  
 ![](../core/media/architecture-bam-08.gif "architecture_bam_08")  
  
 Los pasos siguientes describen la secuencia que se muestra en la ilustración de arriba.  
  
1.  El motor de BizTalk, como se ha descrito anteriormente, tiene interceptores a los que se llama durante la ejecución soluciones de mensajería y orquestaciones. En función de la información de perfiles de seguimiento existente, los interceptores determinan los datos que se capturarán y que se enviarán posteriormente al cuadro de mensajes de BizTalk en formato binario. Hay una tabla denominada TrackingData que almacena los datos BLOB serializados que se han capturado en tiempo de ejecución. Durante el procesamiento, hay ocasiones en las que el motor debe almacenar los datos que contiene en memoria. A esto se les denomina puntos de persistencia y el motor decide el momento en el que se ejecutan dichos puntos. Cuando se produce un punto de persistencia, los datos capturados de los interceptores también se vacían y se guardan dentro de la misma transacción. Esto garantiza la coherencia de los datos en el motor y, en última instancia, lo que BAM puede ver. Si se produce un error y si se revierte la transacción, también se revertirán los datos de BAM asociados.  
  
2.  El servicio de bus de eventos se aloja en el mismo proceso ejecutable que el motor. El servicio toma datos de la tabla TrackingData almacenada por el motor de BTS (o cualquier origen de datos BufferedEventStream). La imagen muestra un ensamblado: Microsoft.BizTalk.Bam.EventObservation. Este ensamblado no expone un método de recuperación de los datos desde BufferedEventStream. Este código se aloja en el propio servicio de bus de eventos. Los datos se recuperan y, a continuación, se preparan para almacenarse en la base de datos de importación principal. La mayoría de los datos binarios son objetos .NET serializados que se rehidratan, después de lo cual se mueven las propiedades desde el objeto a instrucciones SQL con formato.  
  
3.  Cuando tiene lugar el almacenamiento de los datos, el servicio de bus de eventos intenta usar un lote grande. El lote contiene llamadas a procedimientos almacenados generados por la herramienta de implementación del administrador de BAM. Debido a la elevada actividad de la base de datos o a otras circunstancias de bloqueo de la tabla, es posible que el almacenamiento por lotes tenga errores. En caso de un error, se intenta crear el lote un par de veces más. Si los reintentos no son satisfactorios, el lote se divide en lotes más pequeños y se vuelve a intentar. Si tampoco funciona así, el lote se mueve a la tabla FailedTracking.  
  
### <a name="custom-data-insertion"></a>Inserción de datos personalizados  
 En la sección anterior se han proporcionado detalles acerca de cómo BAM recupera datos del host de BizTalk Server mediante varios métodos: de forma indirecta, mediante el Editor de perfiles de seguimiento para crear un perfil, y de forma más directa, con métodos de secuencia de eventos directamente dentro del código. Sin embargo, no todos los datos relevantes de BAM están necesariamente disponibles en BizTalk. Por lo tanto, hay un ensamblado disponible para aplicaciones personalizadas.  
  
 En el diagrama siguiente se muestra este proceso.  
  
 ![](../core/media/architecture-bam-09.gif "architecture_bam_09")  
  
 Los pasos siguientes describen la secuencia que se muestra en la ilustración de arriba.  
  
1.  La aplicación personalizada debe ser capaz de cargar el [Microsoft.BizTalk.Bam.EventObservation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.aspx) ensamblado para tener acceso a los métodos BAM de insertar datos en una actividad de BAM. Hay dos clases principales que se exponen: DirectEventStream y BufferedEventStream. En la ilustración anterior, aparece resaltada la clase DirectEventStream. Esta clase se escribe directamente en la base de datos de importación principal. Es el método más común de escribir datos en una actividad de BAM.  
  
2.  De forma similar al método de almacenamiento de datos de BizTalk, la clase BufferedEventStream escribe objetos BLOB binarios en una base de datos indirecta. En este caso, se utiliza el cuadro de mensajes de BizTalk con almacén intermedio. La clase elegida depende de varios factores; sin embargo, el factor que más interesa es el rendimiento. La clase BufferedEventStream procesará los datos por lotes y mantendrá el máximo rendimiento posible. El inconveniente es que los datos no se escriben inmediatamente.  
  
3.  Al igual que con el método de inserción de datos de BizTalk, el servicio de bus de eventos procesará los datos binarios, los descodificará y, por último, los almacenará en la base de datos de importación principal de BAM. Esto solamente es necesario para los datos escritos mediante la clase BufferedEventStream.  
  
## <a name="distributed-navigation"></a>Exploración distribuida  
 La característica de exploración distribuida del portal de BAM permite a los usuarios ver las relaciones de actividad a través de límites remotos.  
  
## <a name="see-also"></a>Vea también  
 [Arquitectura de seguimiento y administración](../core/management-and-tracking-architecture.md)