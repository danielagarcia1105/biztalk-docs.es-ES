---
title: SendMSMQMessage | Documentos de Microsoft
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
ms.assetid: 398bc396-0c66-4d55-886a-0d9bdab6476f
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39fd92c3d017e9ee88fe60f14c8baf9cb0ff941d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sendmsmqmessage"></a>SendMSMQMessage
En el ejemplo SendMSMQMessage se muestra cómo enviar un mensaje a un puerto de MSMQ desde una aplicación basada en .NET. También se proporcionan instrucciones sobre cómo configurar Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usar ubicación de recepción de MSMQ.  
  
 Debe tener en cuenta que muchas operaciones en MSMQ son asíncronas. Es decir, muchas llamadas de API MSMQ (por ejemplo, **System.Messaging.MessageQueue.Send**) devuelto al llamador antes de que la operación solicitada se haya completado. MSMQ proporciona un mecanismo de envío de comentarios a la aplicación una vez completada la operación. Este mecanismo implica el uso de una cola de administración. MSMQ devuelve los comentarios en forma de mensaje en la cola de administración. La cola de administración a la que MSMQ devolverá los comentarios se especifica cuando se efectúe la llamada original de la API MSMQ. Así, por ejemplo, cuando envía un mensaje mediante la **System.Messaging.MessageQueue.Send** API, la aplicación puede especificar el nombre de una cola de administración mediante la **PROPID_M_ADMIN_QUEUE** message (propiedad) en el mensaje se pasa en la llamada a **System.Messaging.MessageQueue.Send**. Aunque la aplicación puede obtener un código devuelto correctamente el **System.Messaging.MessageQueue.Send** llamada, si el mensaje de operación de envío posteriormente se produce un error, MSMQ escribirá un mensaje a tal efecto en la cola de administración especificada. Si la aplicación no especifica ninguna cola de administración, el error de envío da lugar a la pérdida del mensaje y no capturado del diagnóstico, de hecho, el mensaje desaparece sin dejar rastro. Hay varias situaciones de error en MSMQ que pueden hacer que esto ocurra; por ejemplo, la realización de un envío no transaccional a una cola transaccional.  
  
 En el contexto de este ejemplo, es importante que el código especifique un tipo de transacción en la llamada a **System.Messaging.MessageQueue.Send** que es coherente con la compatibilidad de transacción especificada para la cola a la que el mensaje es envía. Si esto último no se lleva a cabo y no se especifica ninguna cola de administración (como en el caso de este ejemplo), MSMQ descarta el mensaje enviado sin dar ninguna indicación de ello (es decir, sin que se devuelva código de error alguno a la aplicación, sin que se escriba ningún diagnóstico en el registro de eventos, etc.).  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 \<Ruta de acceso de ejemplos > \AdaptersUsage\SendMSMQMessage\  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|-----------|-----------------|  
|App.ico, AssemblyInfo.cs, SendMSMQMessage.csproj, SendMSMQMessage.sln|Proporciona archivos de proyecto y de solución, así como los archivos relacionados para la aplicación gráfica simple para este ejemplo.|  
|Form1.cs, Form1.resx|Proporciona archivos de origen y formulario de [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] .NET formulario para la aplicación gráfica simple para este ejemplo.|  
  
## <a name="how-to-use-this-sample"></a>Uso del ejemplo  
 Puede usar el código de la aplicación gráfica simple incluido en este ejemplo como un ejemplo de cómo enviar mensajes a ubicaciones de recepción de MSMQ en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] desde aplicaciones compatibles con .NET, tal como Microsoft Office, desde páginas ASP.NET, etc.  
  
## <a name="building-and-initializing-the-sample"></a>Crear e inicializar el ejemplo  
  
#### <a name="to-build-the-sample-executable"></a>Para generar el ejecutable de ejemplo  
  
1.  Mediante [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el archivo de solución SendMSMQMessage.sln.  
  
2.  En el menú **Compilar** , haga clic en **Compilar solución**.  
  
## <a name="configuring-biztalk-server-and-creating-the-msmq-queue"></a>Configuración de BizTalk Server y creación de la cola MSMQ  
 Use los procedimientos siguientes para configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y crear la cola de MSMQ para ejecutar el ejemplo.  
  
#### <a name="to-create-the-msmq-queue-in-windows-server-2008-r2-or-windows-server-2008-sp2"></a>Para crear la cola MSMQ en Windows Server 2008 R2 o Windows Server 2008 SP2  
  
1.  Haga clic en **iniciar**, haga clic en **equipo**y, a continuación, haga clic en **administrar**.  
  
2.  Expanda el **características** nodo.  Si **Message Queue Server** no es está instalado, haga clic en **características** y seleccione **agregar características**.  Comprobar **Message Queue Server**, haga clic en **siguiente**y, a continuación, haga clic en **instalar** para instalar MSMQ en el sistema.  
  
3.  Expanda el **Message Queue Server** nodo.  
  
4.  Haga clic en el **colas privadas** nodo, haga clic en **New**y, a continuación, haga clic en **cola privada**.  
  
5.  En **nombre de la cola**, escriba `test`. Asegúrese de que el **transaccional** casilla está activada.  
  
6.  Haga clic en **Aceptar**.  
  
#### <a name="to-create-the-msmq-queue-in-windows-7-or-windows-vista-sp2"></a>Para crear la cola MSMQ en Windows 7 o Windows Vista SP2  
  
1.  Haga clic en **iniciar**, haga clic en **equipo**y, a continuación, haga clic en **administrar**.  
  
2.  Expanda **servicios y aplicaciones**y, a continuación, expanda el **Message Queue Server** nodo.  
  
    > [!NOTE]
    >  Si **Message Queue Server** no está instalado en el equipo, vaya a **el Panel de Control > Programas > programas y características**y, a continuación, seleccione **o desactivar las características de Windows Active**. Compruebe todas las características de **Microsoft Message Queue (MSMQ) Server**y, a continuación, haga clic en **Aceptar**.  
  
3.  Haga clic en el **colas privadas** nodo, haga clic en **New**y, a continuación, haga clic en **cola privada**.  
  
4.  En **nombre de la cola**, escriba **probar**. Asegúrese de que el **transaccional** casilla está activada.  
  
5.  Haga clic en **Aceptar**.  
  
#### <a name="to-configure-biztalk-server"></a>Para configurar BizTalk Server  
  
1.  Seleccione una carpeta en la que recibir mensajes. En los siguientes pasos se da por supuesto que ha seleccionado C:\Demo\Report, pero puede ajustar los pasos según sea necesario para otra carpeta.  
  
2.  Abra el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
3.  Crear una nueva aplicación denominada **MSMQSample**.  
  
4.  Haga clic en **puertos de recepción**, haga clic en **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.  
  
5.  En el **propiedades de puerto de recepción** cuadro de diálogo, en la **nombre** escriba **MyReceivePort**y, a continuación, haga clic en **Aceptar**.  
  
6.  Haga clic en **ubicaciones de recepción**, haga clic en **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**. En el **seleccionar un puerto de recepción** cuadro de diálogo, seleccione el puerto de recepción recién creado y haga clic en **Aceptar**.  
  
7.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **nombre** , escriba un nombre para el puerto de recepción, como **MSMQReceiveLocation**.  
  
8.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, el tipo de transporte, seleccione **MSMQ** .  
  
9. Haga clic en **configurar** para abrir el **propiedades de transporte de MSMQ** cuadro de diálogo. Establecer **cola** a `localhost\private$\test`, establezca **transaccional** a `True`y, a continuación, haga clic en **Aceptar**.  
  
10. Expanda la aplicación, seleccione **puertos de envío**, seleccione **New**, seleccione **puerto de envío unidireccional estático**.  
  
11. En el **propiedades de puerto de envío** cuadro de diálogo, en la **nombre** , escriba un nombre para el puerto de envío, como **MySendPort**.  
  
12. Establecer el **tipo de transporte** propiedad **archivo**.  
  
13. Haga clic en **configurar** para abrir el **propiedades de transporte de archivo** cuadro de diálogo.  
  
14. En el **propiedades de transporte de archivo** cuadro de diálogo, establezca la **carpeta de destino** propiedad **C:\Demo\Report**, mantenga la configuración predeterminada para las demás propiedades y, a continuación, Haga clic en **Aceptar**.  
  
15. Seleccione **filtros**y, a continuación, agregue una nueva fila estableciendo **propiedad** a **BTS. ReceivePortName**. Deje el **operador** columna establecida en  **==** , establezca el **valor** columna **MyReceivePort**y, a continuación, haga clic en **Aceptar**.  
  
16. Menú contextual el nuevo puerto de envío y, a continuación, haga clic en **dar de alta**.  
  
17. Menú contextual el nuevo puerto de envío nuevo y, a continuación, haga clic en **iniciar**.  
  
18. Menú contextual de la nueva ubicación de recepción y, a continuación, haga clic en **habilitar**.  
  
 Ahora, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] estará preparado para trabajar con este ejemplo.  
  
## <a name="running-the-sample"></a>Ejecutar el ejemplo  
 Utilice el siguiente procedimiento para ejecutar el ejemplo SendMSMQMessage.  
  
#### <a name="to-run-the-sample"></a>Para ejecutar el ejemplo  
  
1.  En una ventana de comandos, desplácese a la siguiente carpeta:  
  
     \<Ruta de acceso de ejemplos > \AdaptersUsage\SendMSMQMessage\bin\Debug  
  
2.  Ejecute el archivo SendMSMQMessage.exe, que inicia la aplicación gráfica que proporciona la interfaz de usuario de este ejemplo.  
  
3.  En la aplicación gráfica, en la **nombre de la máquina de BizTalk** , escriba el nombre del equipo local.  
  
4.  Pruebe la **enviar con ajuste** opción:  
  
    1.  Si lo desea, cambie el texto en el **cuerpo del mensaje** cuadro.  
  
    2.  Haga clic en **enviar ajustada**.  
  
     Si la operación se realiza correctamente, verá lo siguiente:  
  
    -   La palabra **correcto** aparece en color rojo en el cuadro justo encima de los botones.  
  
    -   Aparecerá un archivo en la carpeta de destino, C:\Demo\Reports. Este archivo contiene el texto de la **cuerpo del mensaje** cuadro ajustado en etiquetas simples de XML por la biblioteca de puesta en cola de mensajes. NET.  
  
     Si se produce un error en la operación, verá un mensaje de error en el cuadro justo encima de los botones.  
  
5.  Pruebe la **envío exacto** opción:  
  
    1.  Si lo desea, cambie el texto en el **cuerpo del mensaje** cuadro.  
  
    2.  Haga clic en **envío exacto**.  
  
     Si la operación se realiza correctamente, verá lo siguiente:  
  
    -   La palabra **correcto** aparece en color rojo en el cuadro justo encima de los botones.  
  
    -   Aparecerá un archivo en la carpeta de destino, C:\Demo\Reports. Este archivo contiene el texto de la **cuerpo del mensaje** cuadro tal y como aparece en el cuadro de texto.  
  
     Si se produce un error en la operación, verá un mensaje de error en el cuadro justo encima de los botones.  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de adaptadores - uso](../core/adapter-samples-usage.md)