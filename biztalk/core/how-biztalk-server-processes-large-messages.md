---
title: "Cómo BizTalk Server procesa los mensajes grandes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 62c070be-dff5-4349-9e36-dd3a7caf1752
caps.latest.revision: "33"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26ecae241e1e41fdb67204c7975741a240979c2d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-biztalk-server-processes-large-messages"></a>Cómo procesa BizTalk Server los mensajes de gran tamaño
## <a name="what-is-a-large-message"></a>¿Qué es un mensaje de gran tamaño?  
 Desgraciadamente, la respuesta a esta pregunta no está vinculada directamente a un tamaño específico de mensaje sino que depende de los cuellos de botella específicos de su sistema Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Los problemas vinculados a los mensajes de gran tamaño se pueden dividir en las siguientes categorías:  
  
-   **Errores de memoria insuficiente** ciertos tipos de procesamiento de mensajes - como la promoción de propiedades -, validaciones y asignaciones, cargan el mensaje completo en la memoria. Si el tamaño del mensaje en memoria es superior a los recursos disponibles, se produce un error de memoria insuficiente. El umbral de tamaño para los mensajes que quedan dentro de esta categoría es muy inferior al umbral de tamaño para los mensajes que no se cargan en la memoria. Por ejemplo, un archivo sin formato de 10 MB que se analiza en XML y después se asigna, puede crecer en un factor de 10 o más y consumir más de 100 MB de memoria, mientras que un documento XML de 100 MB que no se analiza o asigna podría consumir solo 1 MB de memoria al transmitirlo a la base de datos de cuadro de mensajes.  
  
-   **Problemas de rendimiento para los mensajes que no se cargan en memoria** mensajes que no tienen que estar cargado en memoria se transmiten a la base de datos de cuadro de mensajes mediante la interfaz .NET XmlReader. Aunque no están sujetos a las limitaciones de tamaño de los mensajes que deben cargarse en memoria, existen algunos factores importantes que afectan al modo en que BizTalk Server procesa los mensajes que se transmiten a la base de datos de cuadro de mensajes.  
  
## <a name="factors-that-affect-the-processing-of-large-messages"></a>Factores que afectan al procesamiento de mensajes de gran tamaño  
 Tanto el tamaño del mensaje original, el formato del mensaje como el tipo de procesamiento afectan al modo en que procesa BizTalk Server los mensajes de gran tamaño.  
  
-   **Tamaño del mensaje original** el tamaño del mensaje recibido por BizTalk Server es la indicación más visible del tamaño que tendrá el mensaje cuando se procesa por BizTalk Server. El tamaño original de un mensaje tiene un impacto mucho mayor sobre el rendimiento si se carga el mensaje completo en la memoria en vez de transmitirlo a la base de datos de cuadro de mensajes.  
  
-   **Formato de mensaje** mensajes se reciben en BizTalk Server en uno de dos formatos principales: XML archivos o archivos sin formato.  
  
    -   **Archivos XML** en orden para que BizTalk Server realizar cualquier procesamiento en un mensaje distinto de pasarlo a través de enrutamiento, el mensaje debe estar en el formato de archivo XML. Si los archivos que se van a procesar se reciben en formato XML, en su mayoría retendrán su tamaño original.  
  
    -   **Archivos planos** archivos sin formato deben analizarse en un formato XML para que BizTalk Server pueda realizar cualquier procesamiento distinto de pasarlo a través de enrutamiento. Al analizar un archivo sin formato en un archivo XML, el tamaño del archivo puede aumentar considerablemente. Los archivos sin formato no contienen etiquetas XML con información descriptiva acerca de sus datos. Por otro lado, los archivos XML ajustan todos sus datos en etiquetas XML descriptivas. En algunos casos, el análisis puede aumentar el tamaño de un archivo sin formato en un factor de 10 o más, en función de cuántos datos descriptivos incluyan las etiquetas XML para el archivo.  
  
    -   **Planos documentos de archivos que se encapsulan en un único nodo de sección CDATA en un documento XML** este tipo de documento es una combinación de XML y archivos sin formato y puede resultar problemático porque BizTalk Server debe cargar el documento de archivo sin formato ajustado completo en memoria antes de procesarlo.  
  
-   **Tipo de procesamiento de mensajes** en BizTalk Server, hay dos tipos de procesamiento de mensajes: enrutamiento solo y asignación. Las variables de rendimiento vinculadas al tipo de procesamiento de mensajes que se realiza son el tamaño del mensaje y si está cargado en memoria.  
  
    -   **Sólo enrutamiento** si BizTalk Server sólo se utiliza para enrutar mensajes según las propiedades de mensaje en cuestión, a continuación, se transmite el mensaje en la base de datos de cuadro de mensajes mediante la interfaz .NET XmlReader y partes del mensaje no son individualmente carga en memoria. En este caso, los errores de memoria insuficiente no constituyen un problema y la consideración principal es el tiempo necesario para escribir mensajes de gran tamaño (más de 100 MB) en la base de datos de cuadro de mensajes. El equipo de programación de BizTalk Server ha comprobado el procesamiento correcto de mensajes de un tamaño máximo de 1 GB al realizar solo enrutamiento.  
  
         El factor principal que determina el rendimiento en este escenario es la **tamaño del fragmento del mensaje grande** usado para fragmentar los datos en la base de datos. El **tamaño del fragmento del mensaje grande** es una opción configurable en el **propiedades del grupo de BizTalk** página de configuración y tiene un valor predeterminado de 102400 bytes (100 KB). Al aumentar este valor se reduce el número de acciones de ida y vuelta necesarias para transmitir un mensaje a la base de datos de cuadro de mensajes.  
  
    -   **Asignación de** transformar un documento con un mapa puede ser una operación que utilizan mucha memoria. Cuando un documento se transforma mediante una asignación, BizTalk Server pasa el mensaje a la clase .Net XSLCompileTransform, que carga la hoja de estilo XSL. Cuando el método Load se complete correctamente, el método Transform se puede llamar simultáneamente desde varios subprocesos. [Clase XslCompiledTransform](http://go.microsoft.com/fwlink/p/?LinkID=282683) proporciona más información sobre la clase XSLCompiledTransform.  
  
         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mejora significativamente la administración de memoria para los documentos de gran tamaño mediante la implementación de un umbral de tamaño de mensaje configurable para cargar documentos en memoria durante las transformaciones. Los mensajes con un tamaño inferior a este umbral se administran en memoria. Los mensajes con un tamaño superior a este umbral se almacenan en el búfer del sistema de archivos para reducir las necesidades de memoria. El tamaño de umbral de mensaje predeterminado es 1 MB.  
  
## <a name="guidelines-for-processing-large-messages"></a>Directrices para procesar mensajes de gran tamaño  
 Siga estas directrices para mejorar el rendimiento al procesar mensajes de gran tamaño en BizTalk Server.  
  
1.  Ajuste el umbral de tamaño de mensajes por encima del cual se almacenan los documentos en el búfer del sistema de archivos durante la asignación. Para modificar el umbral de tamaño, cree un valor DWORD denominado **TransformThreshold** en la ubicación siguiente en el registro de BizTalk Server:  
  
    ```  
    HKLM\Software\Microsoft\BizTalk Server\3.0\Administration\TransformThreshold  
    ```  
  
     Tras crear este valor, escriba un valor decimal con el número de bytes para establecer el nuevo umbral. Por ejemplo, escriba un valor decimal de 2097152 para aumentar el umbral de tamaño de mensaje a 2 MB (el valor predeterminado es 1 MB). Aumente este valor en los sistemas con una gran cantidad de memoria disponible para mejorar el rendimiento. El almacenamiento de documentos en el búfer del disco conserva memoria con un impacto en el rendimiento global.  
  
    > [!NOTE]
    >  De forma predeterminada, los documentos que están almacenados en búfer en el sistema de archivos durante la asignación se escriben en el *% temp %* directorio del equipo de BizTalk Server. Cambiar la configuración de la *% temp %* variable de entorno para un disco ajeno al sistema para mejorar el rendimiento al almacenar en búfer los mensajes grandes al sistema de archivos durante la asignación.  
  
2.  Minimice el uso de asignaciones en orquestaciones:  
  
    -   Si usa una asignación para extraer o establecer las propiedades usadas con lógica empresarial en una orquestación, utilice campos distintivos o propiedades promocionadas en su lugar. Al extraer o establecer valores con una asignación, se carga el documento en memoria. Al usar campos distintivos o propiedades promocionadas, el motor de orquestaciones obtiene acceso al contexto del mensaje y no carga el documento en memoria.  
  
    -   Si utiliza una asignación para agregar varios campos a un campo, use campos distintivos o propiedades promocionadas con una variable de orquestación para acumular el conjunto de resultados.  
  
    -   No configure una orquestación con varias entradas para formas de transformación. Una orquestación que contiene varias entradas para formas de transformación no se transmitirá por secuencias al sistema de archivos durante la asignación. Esta limitación provocará que todo el documento que se asigna se cargue en memoria si el tamaño del documento supera el valor de Registro de TransformThreshold especificado. Una posible solución para este problema sería aplicar las transformaciones en el nivel de puerto de recepción, de manera que la orquestación nunca acepte más de una única entrada para las formas de transformación.  
  
3.  Ajustar la **tamaño del fragmento del mensaje grande** propiedad expuesta en el **propiedades del grupo de BizTalk** página de configuración:  
  
     Si el tamaño de memoria de un mensaje recibido supera el número de bytes especificado para **tamaño del fragmento del mensaje grande** , a continuación, el mensaje se divide en fragmentos del tamaño especificado y se escriben los fragmentos en el cuadro de mensajes en la contexto de una transacción del Coordinador de transacciones distribuidas de Microsoft (MSDTC) como se indica a continuación:  
  
    1.  Si se publica el mensaje entrante bajo el contexto de una transacción MSDTC existente, se usará esta transacción al escribir los fragmentos del mensaje en el Cuadro de mensajes. Por ejemplo, si un adaptador transaccional configurado para solicitar transacciones publica el mensaje entrante, se utilizará la transacción existente al escribir los fragmentos del mensaje en el Cuadro de mensajes.  
  
    2.  Si no se publica el mensaje entrante bajo el contexto de una transacción MSDTC existente, se crea una transacción MSDTC nueva para escribir los fragmentos del mensaje.  
  
    -   Aumente el valor de **tamaño del fragmento del mensaje grande** para reducir la frecuencia con la que los mensajes de gran tamaño se fragmentan y reducen la incidencia de creación de transacciones MSDTC asociadas. Esto es necesario porque un uso excesivo de transacciones MSDTC tiene un gran impacto sobre el rendimiento. Tenga en cuenta que, al aumentar este valor, se aumenta también la cantidad de memoria disponible que se utiliza.  
  
    -   Si la escritura de un mensaje en el cuadro de mensajes tarda más del tiempo de espera de transacción MSDTC máximo permitido de 60 minutos, la transacción excede el tiempo de espera, se produce un error, la escritura del mensaje no se lleva a cabo correctamente y se deshace. El **tamaño del fragmento del mensaje grande** valor debe aumentarse lo suficiente para evitar este problema al procesar mensajes muy grandes. En función de la memoria disponible, este valor debe aumentarse hasta un máximo de 1.000.000 bytes.  
  
    -   Cada fragmento de mensaje en un mensaje crea uno o más bloqueos de base de datos SQL Server en la base de datos de cuadro de mensajes. Si el número de bloqueos es superior a varios cientos de miles, el servidor SQL Server podría empezar a generar errores de bloqueos insuficientes. Si se produce este problema, aumente la **tamaño del fragmento del mensaje grande** para reducir el número de bloqueos de base de datos de SQL Server realizada en la base de datos de cuadro de mensajes.  
  
4.  Si experimenta errores de bloqueos insuficientes, considere la posibilidad de alojar la base de datos de cuadro de mensajes en una versión de 64 bits de SQL Server. El número de bloqueos disponible es significativamente superior en la versión de 64 bits de SQL Server.  
  
5.  Ajustar la **umbral de mensajes grandes** propiedad expuesta en el **propiedades del grupo de BizTalk** página de configuración:  
  
     Como un mensaje se procesan por lotes, si el tamaño en memoria de un lote de mensajes alcanza el número de bytes especificado para **umbral de mensajes grandes** , la parte del lote de mensajes que se han procesado se escribe en el cuadro de mensajes antes de se procesa el resto del lote de mensajes. Esto se hace bajo el contexto de una transacción MSDTC de la siguiente forma:  
  
    1.  Si se publica el lote de mensajes bajo el contexto de una transacción MSDTC existente, se usará esta transacción al escribir la parte procesada del lote de mensajes en el Cuadro de mensajes. Por ejemplo, si un adaptador transaccional configurado para solicitar transacciones publica el lote de mensajes entrantes, se utilizará la transacción existente al escribir la parte procesada del lote de mensajes en el Cuadro de mensajes.  
  
    2.  Si no se publica el lote de mensajes bajo el contexto de una transacción MSDTC existente, debe crearse una transacción MSDTC nueva al escribir las partes del lote de mensajes en el Cuadro de mensajes. La transacción MSDTC se usa para garantizar que todas las partes de un lote de mensajes específico se escriben correctamente en la base de datos de cuadro de mensajes.  
  
     El **umbral de mensajes grandes** es directamente aplicable a lotes de mensajes, pero dado que un lote de mensajes se puede establecer en un valor de uno, el **umbral de mensajes grandes** también puede ser indirectamente se aplica a los mensajes individuales. Por ejemplo cuando un lote de mensajes de un mensaje supera el **umbral de mensajes grandes** parámetro la **umbral de mensajes grandes** en vigor se aplica solo a ese único mensaje en el lote.  
  
    -   El **umbral de mensajes grandes** parámetro se debería ajustar para mitigar la creación de transacciones MSDTC utilizadas para distribuir lotes de mensajes en el cuadro de mensajes. Esto es necesario porque el uso excesivo de transacciones MSDTC tiene un gran impacto sobre el rendimiento. Utilice el siguiente cálculo para determinar el valor mínimo para el **umbral de mensajes grandes** configuración debe ser evitar la creación innecesaria de transacciones de MSDTC:  
  
        ```  
        Batch Size * Average size (in bytes) of each message in the batch after being processed by the receive pipeline < Large message threshold  
        ```  
  
         Siempre que el tamaño total en bytes de un lote de mensajes no supera el valor especificado para **umbral de mensajes grandes** , no hay ninguna necesidad de BizTalk iniciar una transacción MSDTC para distribuir el lote de mensajes en el cuadro de mensajes base de datos.