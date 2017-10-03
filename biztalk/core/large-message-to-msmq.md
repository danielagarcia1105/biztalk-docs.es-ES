---
title: "Mensajes de gran tamaño a MSMQ | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, examples
- examples, MSMQ adapters
ms.assetid: 1fb87b46-5656-42c0-be99-8ab66e51bb4d
caps.latest.revision: "35"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e6a3fda3082260338bd387dfe84fe48c7aed565
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="large-message-to-msmq"></a>Mensajes de gran tamaño a MSMQ
Los mensajes de gran tamaño al ejemplo MSMQ se muestra cómo enviar un documento .xml mayor de 4 megabytes (MB) de Message Queue Server (también conocido como MSMQ) para el adaptador de MSMQ de BizTalk mediante el uso de la **MQSendLargeMessage** API implementada por MQRTLarge.dll.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 El ejemplo funciona como se describe a continuación:  
  
1.  Un usuario usa SendLargeMessage.exe para enviar un archivo .xml de gran tamaño a una cola de un equipo local.  
  
2.  [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] recibe el archivo .xml de gran tamaño de la cola y lo copia en un directorio local.  
  
 Muchas de las operaciones de Message Queue Server son asíncronas. Es decir, muchas llamadas de API MSMQ (por ejemplo, **MQSendLargeMessage**) devuelto al llamador antes de que la operación solicitada se haya completado.  
  
 MSMQ proporciona un mecanismo de envío de comentarios a la aplicación una vez completada la operación. Este mecanismo implica el uso de una cola de administración. MSMQ devuelve los comentarios en forma de mensaje en la cola de administración. La cola de administración a la que MSMQ devolverá los comentarios se especifica cuando se efectúe la llamada original de la API MSMQ. Así, por ejemplo, cuando envía un mensaje mediante la **MQSendLargeMessage** API, la aplicación puede especificar el nombre de una cola de administración mediante la **PROPID_M_ADMIN_QUEUE** message (propiedad) en el mensaje pasa en la llamada a **MQSendLargeMessage**. Aunque la aplicación puede obtener un código devuelto correctamente el **MQSendLargeMessage** llamada, si el mensaje de operación de envío posteriormente se produce un error, MSMQ escribirá un mensaje a tal efecto en la cola de administración especificada.  
  
 Si la aplicación no especifica ninguna cola de administración, un error de envío tendrá como consecuencia la pérdida del mensaje y la ausencia de captura del diagnóstico (el mensaje desaparece sin dejar rastro). Un número de situaciones de error en MSMQ puede hacer que esto ocurra, por ejemplo, realizar un envío no transaccional a una cola transaccional.  
  
 En el contexto de este ejemplo, es importante que el código especifique un tipo de transacción en la llamada a **MQSendLargeMessage** que es coherente con la compatibilidad de transacción especificada para la cola a la que se envía el mensaje. Si esto último no se lleva a cabo y no se especifica ninguna cola de administración (como en el caso de este ejemplo), MSMQ descarta el mensaje enviado sin dar ninguna indicación de ello (es decir, sin que se devuelva código de error alguno a la aplicación, sin que se escriba ningún diagnóstico en el registro de eventos, etc.).  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 \<Ruta de acceso de ejemplos > \AdaptersUsage\MSMQLarge  
  
> [!NOTE]
>  Si usa una versión de 64 bits de Windows y [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], el ejemplo se instalará en el **C:\Program Files (x86) \Microsoft BizTalk Server \<versión > \SDK\Samples\AdaptersUsage\MSMQLarge** carpeta.  Tenga en cuenta este cambio para el resto de instrucciones de este documento mediante el **C:\Program Files** carpeta.  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|**Archivo**|**Description**|  
|--------------|---------------------|  
|**MQRTLarge.dll**|Proporciona un complemento para la versión nativa de Message Queue Server. Expone el **MQSendLargeMessage** y **MQReceiveLargeMessage** API.<br /><br /> Se debe instalar [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] en una versión de 64 bits de Windows para obtener acceso a la versión de 64 bits de MQRTLarge.dll.<br /><br /> Para una solución MSMQ sin [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], es posible que MQRTLarge.dll funcione correctamente. Sin embargo, esto no es una configuración recomendada que admita Microsoft, y pueden producirse resultados inesperados si se utiliza fuera de la [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] entorno.|  
|||  
|**LargeMessages.sln**|Proporciona una solución de [!INCLUDE[vs2010](../includes/vs2010-md.md)] para crear el ejecutable SendLargeMessage que se usa en el ejemplo.|  
|**XMLCreator.sln**|Proporciona una solución de [!INCLUDE[vs2010](../includes/vs2010-md.md)] para crear el ejecutable XMLCreator a fin de generar un archivo .xml de prueba para el ejemplo de SDK.|  
  
## <a name="configuring-biztalk-server-and-creating-the-msmq-queue"></a>Configuración de BizTalk Server y creación de la cola MSMQ  
 Asegúrese de que tiene [!INCLUDE[vs2010](../includes/vs2010-md.md)], Microsoft Message Queueing y [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] instalados.  
  
#### <a name="to-configure-biztalk-server"></a>Para configurar BizTalk Server  
  
1.  En [!INCLUDE[vs2010](../includes/vs2010-md.md)], abra el **C:\Program Files\Microsoft BizTalk Server \<versión > \SDK\Samples\AdaptersUsage\MSMQLarge\LargeMessages.sln** archivo de solución.  Cree el ejemplo.  
  
2.  Crear un **C:\Demo** directorio donde [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] colocará los mensajes de MSMQ.  
  
3.  Abra el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
4.  Cree un puerto de envío para el ejemplo para escribir el mensaje.  
  
    -   Expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**, haga clic en **puertos de envío**, haga clic en **Nuevo**y, a continuación, haga clic en **puerto de envío unidireccional estático**.  
  
5.  En el **propiedades de puerto de envío de unidireccional estático** diálogo cuadro, establezca el nombre del puerto **MySendPort**.  
  
6.  Establece el tipo de transporte en **archivo**.  
  
7.  Haga clic en el **configurar** para abrir el **propiedades de transporte de archivo** formulario. Escriba **C:\Demo** en **carpeta de destino**. Asegúrese de que la identidad de la instancia de host tiene acceso a la carpeta C:\Demo.  
  
8.  Asegúrese de que **nombre de archivo** está establecido en **%MessageID%.xml**. Haga clic en **Aceptar**.  
  
9. Haga clic en **Filtros**.  
  
    1.  Establecer **propiedad** a **BTS. ReceivePortName**.  
  
    2.  Establecer **operador** a  **=** .  
  
    3.  Establecer **valor** a **MyReceivePort**.  
  
    4.  Haga clic en **Aceptar**.  
  
10. Cree un puerto de recepción para aceptar el mensaje de MSMQ.  
  
    1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **puertos de recepción**.  
  
    2.  Haga clic en **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.  
  
11. En el **propiedades de puerto de recepción** diálogo cuadro, establezca el nombre del puerto **MyReceivePort**y, a continuación, haga clic en **Aceptar**.  
  
12. Tras crear un puerto de recepción para el ejemplo, es preciso crear una ubicación de recepción.  
  
    1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **ubicaciones de recepción**.  
  
    2.  Haga clic en **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**.  
  
    3.  Establecer el nombre de la ubicación de recepción **MSMQReceiveLocation**.  
  
    4.  En el **seleccionar un puerto de recepción** cuadro de diálogo, seleccione **MyReceivePort**.  
  
    5.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, establezca **tipo de transporte** a **MSMQ**.  
  
    6.  En el **dirección (URI)** sección, haga clic en **configurar** para abrir el **propiedades de transporte de MSMQ** formulario. Establecer **cola** a **localhost\private$ \test**.  
  
    7.  Establecer **transaccional** a `True`y, a continuación, haga clic en **Aceptar**.  
  
13. Es necesario hacer que los puertos y las ubicaciones de recepción se encuentren disponibles para su uso a través de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
    1.  Haga clic en **MySendPort**y, a continuación, haga clic en **dar de alta**.  
  
    2.  Haga clic en **MySendPort**y, a continuación, haga clic en **iniciar**.  
  
    3.  Haga clic en **MSMQReceiveLocation**y, a continuación, haga clic en **habilitar**.  
  
#### <a name="to-create-the-msmq-queue-in-windows-server-2008-r2-or-windows-server-2008-sp2"></a>Para crear la cola MSMQ en Windows Server 2008 R2 o Windows Server 2008 SP2  
  
1.  Haga clic en **iniciar**, haga clic en **equipo**y, a continuación, haga clic en **administrar**.  
  
2.  Expanda el **características** nodo.  
  
3.  Expanda el **Message Queue Server** nodo.  
  
4.  Haga clic en el **colas privadas** nodo, haga clic en **New**y, a continuación, haga clic en **cola privada**.  
  
5.  En **nombre de la cola**, escriba **probar**. Asegúrese de que el **transaccional** casilla está activada.  
  
6.  Haga clic en **Aceptar**.  
  
#### <a name="to-create-the-msmq-queue-in-windows-7-or-windows-vista-sp2"></a>Para crear la cola MSMQ en Windows 7 o Windows Vista SP2  
  
1.  Haga clic en **iniciar**, haga clic en **equipo**y, a continuación, haga clic en **administrar**.  
  
2.  Expanda **servicios y aplicaciones**y, a continuación, expanda el **Message Queue Server** nodo.  
  
    > [!NOTE]
    >  Si **Message Queue Server** no está instalado en el equipo, vaya a **el Panel de Control > Programas > programas y características**y, a continuación, seleccione **o desactivar las características de Windows Active**. Compruebe todas las características de **Microsoft Message Queue (MSMQ) Server**y, a continuación, haga clic en **Aceptar**.  
  
3.  Haga clic en el **colas privadas** nodo, haga clic en **New**y, a continuación, haga clic en **cola privada**.  
  
4.  En **nombre de la cola**, escriba **probar**. Asegúrese de que el **transaccional** casilla está activada.  
  
5.  Haga clic en **Aceptar**.  
  
## <a name="creating-a-test-file-and-running-the-sample"></a>Creación de un archivo de prueba y ejecución del ejemplo  
  
#### <a name="to-create-a-large-test-file"></a>Para crear un archivo de prueba de gran tamaño  
  
1.  En [!INCLUDE[vs2010](../includes/vs2010-md.md)], abra la solución **C:\Program Files\Microsoft BizTalk Server \<versión > \SDK\Samples\AdaptersUsage\MSMQLarge\XMLCreator\XMLCreator.sln**.  
  
2.  Cree y ejecute el proyecto.  
  
3.  En **cuerpo XML**, tipo **se trata de un mensaje de prueba**.  
  
4.  En **número de veces para copiar el cuerpo XML**, tipo `250000`.  
  
5.  En **ubicación del archivo XML**, tipo `C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\AdaptersUsage\MSMQLarge\LargeFile.xml`.  
  
6.  Haga clic en **crear XML**y, a continuación, haga clic en **Aceptar**.  
  
#### <a name="to-run-the-sample"></a>Para ejecutar el ejemplo  
  
1.  Abra un símbolo del sistema y cambie al directorio **C:\Program Files\Microsoft BizTalk Server \<versión > \SDK\Samples\AdaptersUsage\MSMQLarge\SendLargeMessage\bin\debug**.  
  
2.  En el símbolo del sistema, ejecute **SendLargeMessage.exe**. El ejecutable SendLargeMessage acepta dos variables: la primera es la ubicación de la cola MSMQ y la segunda es la ubicación del archivo .xml que se va a enviar:  
  
    ```  
    DIRECT=OS:localhost\private$\Test  "C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\AdaptersUsage\MSMQLarge\LargeFile.xml"  
    ```  
  
3.  Compruebe que se creó un archivo del mismo tamaño en el [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] equipo en el **C:\Demo** directory. Éste es el directorio identificado en el puerto de envío MySendPort.  
  
## <a name="comments"></a>Comentarios  
 SendLargeMessage.exe hace referencia a la **LargeMessages** API, que a su vez hace referencia a la BizTalk extensión Message Queue Server grandes mensaje (MQRTLarge.dll) API. La API de extensión de mensajes de gran tamaño de Message Queue Server es un complemento para la versión nativa de Message Queue Server con el que se habilita el procesamiento de mensajes con un tamaño superior al límite de 4 MB de la versión nativa de Message Queue Server.  
  
 Este ejemplo se utiliza la **MQSendLargeMessage** API y expone la API de .NET Framework mediante el uso de la **LargeMessages** API.  
  
## <a name="see-also"></a>Vea también  
 [Extensión de mensajes de BizTalk para Message Queue grandes](../core/biztalk-message-queuing-large-message-extension.md)   
 [Ejemplos de adaptadores - uso](../core/adapter-samples-usage.md)