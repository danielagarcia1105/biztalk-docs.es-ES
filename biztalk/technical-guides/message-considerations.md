---
title: Consideraciones de mensajes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ca466fa-426c-46f6-a400-747ff51ff8f4
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5499c9535ff822dfec8097185ef17d8d7999e1f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-considerations"></a>Consideraciones de mensaje
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Proporciona un amplio conjunto de capacidades para enviar, recibir, transformar y procesar mensajes. Algunas de estas características incluyen:  
  
-   Capacidad para enviar y recibir mensajes con varios transportes estándar del sector, como HTTP, SMTP, FTP o FTPS y WCF. Compatibilidad de nivel de transporte para enviar y recibir mensajes se realiza mediante [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adaptadores. Integración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesamiento de mensajes con diversos "línea de negocio" aplicaciones (LOB) se logra mediante uno de los muchos disponibles [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aceleradores o adaptadores, como el Acelerador de BizTalk para HIPAA, el Acelerador de BizTalk para SWIFT, o bien, el adaptador de SAP de BizTalk. Estos adaptadores y aceleradores se ajustan a los estándares del sector que permite a su vez la integración directa de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con los sistemas que se ajustan al estándar del sector determinado.  
  
-   Capacidad para procesar varios formatos de mensaje, como texto sin formato, XML, binario y otros. Esta funcionalidad es crucial para proporcionar integración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con un amplio espectro de socios comerciales.  
  
-   Compatibilidad con la asignación de transformación o un documento de mensaje. Asignación se adapta a la transformación de datos entre distintos esquemas. Por ejemplo, podría utilizarse asignación para transformar el contenido de un pedido de compra recibidos del cliente en una confirmación de notificación de envío para enviar al cliente.  
  
-   Orquestaciones de BizTalk Server proporcionan funciones para la creación de procesos empresariales que abarcan el tiempo, las organizaciones, las aplicaciones y usuarios. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]proporciona la interfaz gráfica del Diseñador de orquestaciones para desarrollar procesos empresariales que incluyen compatibilidad con transacciones (tipo tradicional de "atómica" MSDTC y larga ejecución), control de excepciones, la depuración, el seguimiento y la extensibilidad para llamar a código externo.  
  
    > [!NOTE]  
    >  Vea [optimizar el rendimiento de la orquestación](../technical-guides/optimizing-orchestration-performance.md) para obtener instrucciones sobre los procedimientos recomendados que deben seguir al utilizar orquestaciones en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Vea el tema [crear orquestaciones utilizando Diseñador de orquestaciones](http://go.microsoft.com/fwlink/?LinkId=158997) (http://go.microsoft.com/fwlink/?LinkId=158997) en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentación para obtener información detallada acerca de cómo utilizar el Diseñador de orquestaciones.  
  
 El resto de este tema describe las consideraciones de rendimiento relacionadas con el perfil de tamaño, la complejidad y la distribución de mensajes que se procesan en un [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] entorno.  
  
## <a name="message-size-considerations"></a>Consideraciones de tamaño de mensaje  
 Si bien BizTalk Server no impone ninguna restricción sobre el tamaño del mensaje, las dependencias y los límites prácticos pueden requerir minimizar el tamaño de los mensajes debido a mensajes de gran tamaño requieren más recursos de procesamiento. Al igual que aumenta de tamaño, el rendimiento global (mensajes procesados por segundo) de mensajes se reduce. Al diseñar su escenario y planear la capacidad, tenga en cuenta el tamaño medio del mensaje, el tipo de mensaje y el número de mensajes que BizTalk Server procesa. No use un período innecesariamente largo atributo y nombres de etiqueta; Si es posible, mantenga la longitud de menos de 50 caracteres. Por ejemplo, no utilice un nombre de etiqueta de 200 caracteres para un tamaño de mensaje de solo 1 byte.  
  
 Si el tamaño de memoria de un mensaje recibido supera el número de bytes especificado para el tamaño del fragmento del mensaje grande (configurable en la página de propiedades de grupo para el grupo de BizTalk en la consola de administración de BizTalk Server), el mensaje se divide en fragmentos del tamaño especificado. Además, los fragmentos se escriben en el cuadro de mensajes en el contexto de una transacción del Coordinador de transacciones distribuidas de Microsoft (MSDTC) como se indica a continuación:  
  
1.  Si el mensaje entrante se publica en el contexto de una transacción MSDTC existente, se usará esta transacción al escribir los fragmentos de mensajes en la base de datos de BizTalk MessageBox. Por ejemplo, si se publica el mensaje entrante por un adaptador transaccional configurado para requerir que las transacciones, la transacción existente se usará al escribir los fragmentos de mensajes en la base de datos de cuadro de mensajes.  
  
2.  Si el mensaje entrante no se publica en el contexto de una transacción MSDTC existente, se crea una nueva transacción MSDTC para escribir los fragmentos de mensajes en la base de datos de cuadro de mensajes. En este escenario, se aplican las consideraciones siguientes:  
  
    -   Aumente el valor de **tamaño del fragmento del mensaje grande** para reducir la frecuencia con la que los mensajes de gran tamaño se fragmentan y reducen la incidencia de creación de transacciones MSDTC asociadas. Esto es necesario porque un uso excesivo de transacciones MSDTC tiene un gran impacto sobre el rendimiento. Tenga en cuenta que, al aumentar este valor, se aumenta también la cantidad de memoria disponible que se utiliza.  
  
    -   Si se tarda más tiempo que el máximo permitido MSDTC transacción tiempo de espera de 60 minutos para escribir un mensaje en el cuadro de mensajes, la transacción agota el tiempo, se produce un error, y al intentar escribir el mensaje se produce un error y es revierte. El **tamaño del fragmento del mensaje grande** valor debe aumentarse lo suficiente para evitar este problema al procesar mensajes muy grandes. En función de la memoria disponible, este valor debe aumentarse hasta un máximo de 1.000.000 bytes.  
  
    -   Cada fragmento de mensaje en un mensaje crea uno o más bloqueos de base de datos SQL Server en la base de datos de cuadro de mensajes. Cuando el número de bloqueos supera varios cientos de miles, es posible que SQL Server generará errores "sin bloqueo". Si se produce este problema, aumente el valor de **tamaño del fragmento del mensaje grande** para reducir el número de fragmentos (lo que disminuye el número de bloqueos de base de datos de SQL Server realizada en la base de datos de cuadro de mensajes) o considere la posibilidad de alojamiento su Base de datos de cuadro de mensajes en una versión de 64 bits de SQL Server. El número de bloqueos disponibles es significativamente superior en la versión de 64 bits de SQL Server que en una versión de 32 bits de SQL Server. La fórmula siguiente puede utilizarse para calcular el número máximo de mensajes por intercambio cuando se aloja la base de datos de cuadro de mensajes en una versión de 32 bits de SQL Server:  
  
        ```  
        200,000 / (Number of CPUs * BatchSize * MessagingThreadPoolSize)  
        ```  
  
 Para obtener más información acerca de cómo BizTalk Server procesa los mensajes de gran tamaño, incluidas las directrices para procesar mensajes de gran tamaño, vea [cómo BizTalk Server procesa grandes mensajes](http://go.microsoft.com/fwlink/?LinkID=154680) (http://go.microsoft.com/fwlink/?LinkID=154680).  
  
## <a name="message-type-considerations"></a>Consideraciones acerca del tipo de mensaje  
 Los mensajes se reciben en BizTalk Server en uno de dos formatos principales: XML archivos o archivos sin formato. Tipo de mensaje siempre debe tenerlo en cuenta en el perfil de distribución de mensaje debido a los requisitos de recursos distintos de los mensajes de archivo sin formato y XML.  
  
-   **Archivos XML** en orden para que BizTalk Server realizar cualquier procesamiento en un mensaje que no sea la ruta de acceso directo, el mensaje debe estar en el formato de archivo XML.  
  
-   **Archivos planos** archivos sin formato deben analizarse en un formato XML para que BizTalk Server pueda realizar cualquier procesamiento que no sea la ruta de acceso directo. Al analizar un archivo sin formato en un archivo XML, el tamaño del archivo puede aumentar considerablemente. Los archivos sin formato no contienen etiquetas XML con información descriptiva acerca de sus datos. Por otro lado, los archivos XML ajustan todos sus datos en etiquetas XML descriptivas. En algunos escenarios, el análisis puede aumentar el tamaño de un archivo sin formato en un factor de 10 o más, en función de cuántos datos descriptivos se encuentran en las etiquetas XML para el archivo.  
  
-   **Planos documentos de archivos que se encapsulan en un único nodo de sección CDATA en un documento XML** este tipo de documento es una combinación de XML y archivos sin formato y, a menudo es intensivos de memoria, ya que BizTalk Server debe cargar todo el archivo sin formato ajustado en memoria antes de procesarlo.  
  
## <a name="overload-considerations"></a>Consideraciones de sobrecarga  
 La mayoría de las aplicaciones de BizTalk Server no reciben mensajes a una velocidad constante, específico. Por lo general, el procesamiento de mensajes está sujeto a los valores máximos y mínimos. , Por ejemplo, una aplicación de banca en línea puede procesar un mayor volumen de mensajes lo primero en la mañana, a continuación, en el transcurso del día y al final del día. Se deben probar soluciones de BizTalk Server para asegurarse de que podrá administrar estos escenarios de sobrecarga. Para determinar el grado de una solución puede administrar el servidor BizTalk Server sobrecarga escenarios, se debe determinar el rendimiento sostenible máximo (MST) de la solución de BizTalk Server. El MST es la mayor carga de tráfico de mensajes que puede administrar un sistema indefinidamente en un entorno de producción. Para obtener más información sobre el rendimiento máximo Sostenible, consulte [planear el rendimiento sostenido de](http://go.microsoft.com/fwlink/?LinkID=158065) (http://go.microsoft.com/fwlink/?LinkID=158065) y [¿qué es rendimiento sostenible?](http://go.microsoft.com/fwlink/?LinkID=132304) (http://go.microsoft.com/fwlink/?LinkID=132304) en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentación.  
  
## <a name="schema-complexity"></a>Complejidad del esquema  
 El rendimiento de análisis del mensaje (análisis de archivo sin formato especialmente) se ve afectado por la complejidad de los esquemas. A medida que aumenta la complejidad del esquema, se reduce el rendimiento general. Al diseñar esquemas, reduzca la longitud de los nombres de nodo y mover las propiedades promocionadas a la parte superior del esquema. Esto reduce el tiempo de recuperación y, por tanto, aumenta el rendimiento.  
  
## <a name="map-complexity"></a>Complejidad del mapa  
 Según la complejidad de las asignaciones, transformación mapa puede consumir muchos recursos. Al igual que asignar complejidad aumenta, disminuye el rendimiento general. Para mejorar el rendimiento general, minimice el número de vínculos y functoids usados en las asignaciones, especialmente los functoids que llaman a recursos externos, como el functoid búsqueda en base de datos.  
  
## <a name="flat-file-parsing-considerations"></a>Consideraciones de análisis de archivo sin formato  
 Los dos factores que tienen el mayor impacto sobre el rendimiento de análisis de archivo sin formato son complejidad de tamaño y el esquema de archivo. Un esquema ambiguo es un esquema que contiene muchos campos opcionales. Cuando se utilizan los tamaños de archivo grandes, un esquema con muchos campos opcionales puede degradar el rendimiento porque archivos de mayor tamaño pueden coincidir con diferentes bifurcaciones del esquema. Complejidad del esquema tiene un impacto menor en archivos más pequeños que en los archivos de mayor tamaño.  
  
## <a name="see-also"></a>Vea también  
 [Optimizar las aplicaciones de BizTalk Server](../technical-guides/optimizing-biztalk-server-applications.md)