---
title: Consideraciones de mensajes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ca466fa-426c-46f6-a400-747ff51ff8f4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d8a9bcf8b2910f12183db33aa27a74b550c72b8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979685"
---
# <a name="message-considerations"></a>Consideraciones de mensaje
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Proporciona un amplio conjunto de funcionalidades para enviar, recibir, transformar y procesar los mensajes. Algunas de estas funcionalidades incluyen:  
  
- Capacidad para enviar y recibir mensajes con varios transportes estándar del sector, como HTTP, SMTP, FTP o FTPS y WCF. Soporte técnico de nivel de transporte para enviar y recibir los mensajes se logra mediante [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adaptadores. Integración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesamiento de mensajes mediante distintos "línea de negocio" aplicaciones (LOB) se logra mediante uno de los muchos disponibles [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aceleradores o los adaptadores, como el Acelerador de BizTalk para HIPAA, el Acelerador de BizTalk para SWIFT, o el adaptador de BizTalk SAP. Estos adaptadores y aceleradores se ajustan a los estándares del sector, lo que a su vez permite la integración directa de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con sistemas que se ajustan al estándar de la industria determinado.  
  
- Capacidad para procesar varios formatos de mensaje, como texto sin formato, XML, binario y otros. Esta funcionalidad es crucial para proporcionar integración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con un amplio espectro de los socios comerciales.  
  
- Compatibilidad con la asignación de transformación o documento de mensaje. Asignación se adapta a la transformación de datos entre distintos esquemas. Por ejemplo, se podría usar asignación para transformar el contenido de un pedido de compra recibidos del cliente en una confirmación con el trasvase de registros de notificación para enviarse al cliente.  
  
- Orquestaciones de BizTalk Server proporcionan funcionalidad para la creación de procesos empresariales que abarquen el tiempo, las organizaciones, las aplicaciones y las personas. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona la interfaz gráfica del Diseñador de orquestaciones para desarrollar procesos empresariales que incluyen compatibilidad con transacciones (tipo tradicional de MSDTC "atómica" y larga ejecución), control de excepciones, depuración, seguimiento y extensibilidad para llamar a código externo.  
  
  > [!NOTE]
  >  Consulte [optimizar el rendimiento de las orquestaciones](../technical-guides/optimizing-orchestration-performance.md) para obtener instrucciones sobre procedimientos recomendados al usar las orquestaciones en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Vea el tema [crear orquestaciones usar diseñador de orquestaciones](http://go.microsoft.com/fwlink/?LinkId=158997) (<http://go.microsoft.com/fwlink/?LinkId=158997>) en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentación para obtener información detallada acerca de cómo utilizar el Diseñador de orquestaciones.  
  
  El resto de este tema describe las consideraciones de rendimiento relacionados con el perfil de distribución, la complejidad y el tamaño de los mensajes que se procesan en un entorno de BizTalk Server.  
  
## <a name="message-size-considerations"></a>Consideraciones de tamaño de mensaje  
 Mientras que BizTalk Server se impone ninguna restricción sobre el tamaño del mensaje, las dependencias y límites prácticos pueden necesitar minimizar el tamaño de los mensajes debido a mensajes de gran tamaño requieren más recursos de procesamiento. Como mensaje aumenta de tamaño, el rendimiento general (los mensajes procesados por segundo) disminuye. Al diseñar el escenario y planear la capacidad, tenga en cuenta el tamaño medio del mensaje, el tipo de mensaje y el número de mensajes de BizTalk Server procesa. No use un período innecesariamente largo atributo y nombres de etiqueta. Si es posible, mantenga la longitud de menos de 50 caracteres. Por ejemplo, no utilice un nombre de etiqueta de 200 caracteres para un tamaño de mensaje de solo 1 byte.  
  
 Si el tamaño de memoria de un mensaje recibido supera el número de bytes especificado para el tamaño del fragmento del mensaje grande (configurable en la página de propiedades de grupo para el grupo de BizTalk en la consola de administración de BizTalk Server), el mensaje se divide en fragmentos el tamaño especificado. Además, los fragmentos se escriben en el cuadro de mensajes en el contexto de una transacción del Coordinador de transacciones distribuidas de Microsoft (MSDTC) como sigue:  
  
1. Si se publica el mensaje entrante en el contexto de una transacción MSDTC existente, se usará esta transacción al escribir los fragmentos del mensaje en la base de datos de BizTalk MessageBox. Por ejemplo, si el mensaje entrante se publica un adaptador transaccional configurado para requerir que las transacciones, la transacción existente se usará al escribir los fragmentos del mensaje en la base de datos de cuadro de mensajes.  
  
2. Si no se publica el mensaje entrante en el contexto de una transacción MSDTC existente, se crea una nueva transacción MSDTC para escribir los fragmentos del mensaje en la base de datos de cuadro de mensajes. En este escenario, se aplican las consideraciones siguientes:  
  
   -   Aumente el valor de **tamaño del fragmento del mensaje grande** para reducir la frecuencia con la que se fragmentan los mensajes grandes y reducen la incidencia de creación de transacciones MSDTC asociadas. Esto es necesario porque un uso excesivo de transacciones MSDTC tiene un gran impacto sobre el rendimiento. Tenga en cuenta que, al aumentar este valor, se aumenta también la cantidad de memoria disponible que se utiliza.  
  
   -   Si supera el máximo permitido MSDTC transacción tiempo de espera de 60 minutos para escribir un mensaje en el cuadro de mensajes, la transacción agota el tiempo, se produce un error, y el intento de escribir el mensaje tiene errores y se revierte. El **tamaño del fragmento del mensaje grande** valor debe aumentarse lo suficiente para evitar este problema al procesar mensajes muy grandes. En función de la memoria disponible, este valor debe aumentarse hasta un máximo de 1.000.000 bytes.  
  
   -   Cada fragmento de mensaje en un mensaje crea uno o más bloqueos de base de datos SQL Server en la base de datos de cuadro de mensajes. Cuando el número de bloqueos supera varios cientos de miles, es posible que SQL Server generará errores "fuera de bloqueo". Si se produce este problema, aumente el valor de **tamaño del fragmento del mensaje grande** para reducir el número de fragmentos (lo que disminuye el número de bloqueos de base de datos de SQL Server realizada en la base de datos de cuadro de mensajes) o considere la posibilidad de vivienda su Base de datos de cuadro de mensajes en una versión de 64 bits de SQL Server. El número de bloqueos disponibles es significativamente superior en la versión de 64 bits de SQL Server que en una versión de 32 bits de SQL Server. La fórmula siguiente puede utilizarse para calcular el número máximo de mensajes por intercambio cuando la base de datos de cuadro de mensajes está alojado en una versión de 32 bits de SQL Server:  
  
       ```  
       200,000 / (Number of CPUs * BatchSize * MessagingThreadPoolSize)  
       ```  
  
   Para obtener más información acerca de cómo BizTalk Server procesa los mensajes de gran tamaño, incluidas las directrices para el procesamiento de mensajes de gran tamaño, vea [cómo BizTalk Server los procesos de mensajes de gran tamaño](http://go.microsoft.com/fwlink/?LinkID=154680) (http://go.microsoft.com/fwlink/?LinkID=154680).  
  
## <a name="message-type-considerations"></a>Consideraciones acerca del tipo de mensaje  
 Los mensajes se reciben en BizTalk Server en uno de los dos formatos principales: XML archivos o archivos sin formato. Tipo de mensaje siempre debe tenerse en cuenta en el perfil de distribución de mensaje debido a los requisitos de recursos distintos de los mensajes de archivo sin formato y XML.  
  
-   **Archivos XML** en orden para que BizTalk Server realizar cualquier procesamiento en un mensaje que no sea de paso a través de enrutamiento, el mensaje debe estar en el formato de archivo XML.  
  
-   **Archivos planos** archivos sin formato deben analizarse en un formato XML antes de que BizTalk Server puede realizar cualquier procesamiento que no sea de paso a través de enrutamiento. Al analizar un archivo sin formato en un archivo XML, el tamaño del archivo puede aumentar considerablemente. Los archivos sin formato no contienen etiquetas XML con información descriptiva acerca de sus datos. Por otro lado, los archivos XML ajustan todos sus datos en etiquetas XML descriptivas. En algunos escenarios, análisis pueden aumentar el tamaño de un archivo sin formato en un factor de 10 o más, en función de cuántos datos descriptivos se encuentran en las etiquetas XML para el archivo.  
  
-   **Planos de documentos de archivo encapsulados en un nodo de sección CDATA en un documento XML** este tipo de documento es una combinación de XML y archivos sin formato y, a menudo es una gran cantidad de memoria, ya que BizTalk Server debe cargar todo el archivo sin formato ajustado en memoria antes de procesarla.  
  
## <a name="overload-considerations"></a>Consideraciones de sobrecarga  
 La mayoría de las aplicaciones de BizTalk Server no reciben los mensajes a una velocidad constante y específico. Normalmente, el procesamiento de mensajes es sujetos a los valores máximos y mínimos. , Por ejemplo, una aplicación de banca en línea puede procesar un mayor volumen de mensajes primero por la mañana, a continuación, el transcurso del día y al final del día. Soluciones de BizTalk Server deben probarse para asegurarse de que pueda controlar estos escenarios de sobrecarga. Para determinar el grado de un servidor BizTalk Server puede controlar la solución sobrecarga escenarios, se debe determinar el rendimiento sostenible máximo (MST) de la solución de BizTalk Server. El MST es la mayor carga de tráfico de mensajes que puede administrar un sistema indefinidamente en un entorno de producción. Para obtener más información acerca de MST, consulte [planear el rendimiento sostenido](http://go.microsoft.com/fwlink/?LinkID=158065) (<http://go.microsoft.com/fwlink/?LinkID=158065>) y [¿qué es rendimiento sostenible?](http://go.microsoft.com/fwlink/?LinkID=132304) (<http://go.microsoft.com/fwlink/?LinkID=132304>) en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentación.  
  
## <a name="schema-complexity"></a>Complejidad del esquema  
 El rendimiento de análisis del mensaje (análisis de archivo sin formato especial) se ve afectado por la complejidad de los esquemas. A medida que aumenta la complejidad del esquema, se reduce el rendimiento general. Al diseñar esquemas, reduzca la longitud de los nombres de nodo y mover las propiedades promocionadas en la parte superior del esquema. Esto reduce el tiempo de recuperación y, por tanto, aumenta el rendimiento.  
  
## <a name="map-complexity"></a>Complejidad del mapa  
 Según la complejidad de las asignaciones, transformación mapa puede consumir muchos recursos. Igual que aumenta la complejidad, disminuye el rendimiento general de mapa. Para mejorar el rendimiento general, minimizar el número de vínculos y functoids usados en los mapas, especialmente los functoids que llaman a recursos externos, como el functoid búsqueda en base de datos.  
  
## <a name="flat-file-parsing-considerations"></a>Consideraciones de análisis de archivo sin formato  
 Los dos factores que tienen el mayor impacto en el rendimiento de análisis de archivo sin formato son la complejidad de tamaño y el esquema de archivo. Un esquema ambiguo es un esquema que contiene muchos campos opcionales. Cuando se utilizan tamaños de archivo grandes, un esquema con muchos campos opcionales puede degradar el rendimiento porque los archivos más grandes pueden coincidir con distintas ramas del esquema. Complejidad del esquema tiene un impacto menor en archivos más pequeños que en los archivos de mayor tamaño.  
  
## <a name="see-also"></a>Vea también  
 [Optimización de las aplicaciones de BizTalk Server](../technical-guides/optimizing-biztalk-server-applications.md)