---
title: MQSCorrelationSetOrchestrationWithSolicitResponse (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, MQSeries adapters
- orchestrations, examples
- examples, orchestrations
- examples, messages
- messages, examples
- MQSeries adapters, examples
ms.assetid: 5127d743-bb79-4e97-a2f3-446892e1bfa0
caps.latest.revision: "29"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2665967e27cf708fcdbbddf61a7b66c619757223
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="mqscorrelationsetorchestrationwithsolicitresponse-biztalk-server-sample"></a>MQSCorrelationSetOrchestrationWithSolicitResponse (ejemplo de BizTalk Server)
En el ejemplo MQSCorrelationSetOrchestrationWithSolicitResponse se muestra cómo usar un identificador de correlación producido por MQSeries Server en lugar de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 La orquestación envía un mensaje con un valor vacío para la **MQMD_MsgID** propiedad en el encabezado del mensaje. MQSeries genera MessageID y CorrelationID y devuelve un mensaje con un valor asignado a **MQMD_MsgID** y **MQMD_CorrelId** puerto del adaptador de envío como parte de la respuesta en la petición-respuesta . La orquestación utiliza el identificador de correlación generado para inicializar el conjunto de correlaciones y se indica a continuación, el conjunto de correlaciones en la siguiente ubicación de recepción mediante la comprobación de la **MQMD_CorrelId** propiedad del mensaje. El adaptador también asigna el identificador de correlación para **BizTalk_CorrelationID**, que también se puede utilizar en una orquestación. Para obtener más información sobre el uso de identificadores de correlación con el adaptador, vea [correlación de solicitud y respuesta utilizando mensajes](../core/correlating-messages-using-request-reply.md).  
  
> [!IMPORTANT]
>  Las orquestaciones que utilizan esta técnica pueden experimentar problemas si el mensaje de MQSeries Server llega antes que el identificador de correlación. Asegúrese de diseñar las orquestaciones de modo que otorgue el tiempo suficiente a MQSeries Server para devolver el identificador de correlación. Este ejemplo no considera esta posible condición de anticipación.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 *\<Ejemplos de ruta de acceso >*\AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestrationWithSolicitResponse  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|**Archivo**|**Description**|  
|--------------|---------------------|  
|**MQSCorrelationSolicitResponse.btproj,**<br /><br /> **MQSCorrelationSolicitResponse.sln**|Archivos de proyectos y soluciones para la aplicación.|  
|**MQSCorrelationSolicitResponse.odx**|El archivo de orquestación de BizTalk para la aplicación.|  
|**MQSCorrelationSolicitResponse.snk**|Archivo de clave de nombre seguro.|  
|Setup.bat|Crea e inicializa este ejemplo.|  
  
## <a name="how-to-use-this-sample"></a>Uso del ejemplo  
 Para crear la aplicación, debe realizar los siguientes pasos:  
  
-   Crear dos colas MQSeries.  
  
-   Configurar una ubicación de recepción y un puerto de envío de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
-   Habilitar la ubicación de recepción.  
  
-   Inicie el puerto de envío.  
  
-   Crear las carpetas correspondientes.  
  
-   Modificar la orquestación.  
  
-   Implementar, enlazar e iniciar la orquestación.  
  
 Si dispone de los permisos necesarios para la instalación de MQSeries Server para Windows, puede crear la cola MQSeries mediante los cuadros de diálogo del adaptador y puede omitir el procedimiento siguiente. Si no dispone de este acceso, puede crear la cola con IBM WebSphere MQ Explorer. Para crear las colas con WebSphere MQ Explorer, realice los siguientes pasos.  
  
## <a name="creating-the-mqseries-queues-through-the-websphere-mq-explorer"></a>Crear las colas MQSeries con WebSphere MQ Explorer  
  
#### <a name="to-create-the-mqseries-queues-through-the-websphere-mq-explorer"></a>Para crear las colas MQSeries con WebSphere MQ Explorer  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **IBM WebSphere MQ**y, a continuación, haga clic en **WebSphere MQ Explorer**.  
  
2.  Haga doble clic en **administradores de cola**y, a continuación, haga doble clic en el Administrador de cola predeterminado. El Administrador de cola predeterminado se suele llamar **QM_***< nombre_equipo >* donde *nombre_equipo* es el nombre del equipo.  
  
3.  Haga clic en **colas**, seleccione **New**y, a continuación, haga clic en **cola Local**.  
  
4.  En **Create Local Queue** cuadro de diálogo **nombre de la cola**, escriba "REPLYTOQ" y, a continuación, haga clic en **Aceptar**.  
  
5.  Haga clic en **colas**, haga clic en **New**y, a continuación, haga clic en **cola Local**.  
  
6.  En el **Create Local Queue** cuadro de diálogo **nombre de la cola**, escriba "SOLICITRESPONSEQ" y, a continuación, haga clic en **Aceptar**.  
  
## <a name="creating-the-receive-location-and-the-mqseries-queue"></a>Crear la ubicación de recepción y la cola MQSeries  
 Este procedimiento crea el puerto de envío y la ubicación de recepción para enviar el mensaje y recibir el mensaje de correlación de MQSeries. La cola MQSeries también se creará al crear la ubicación de recepción si no se ha creado anteriormente.  
  
#### <a name="to-create-the-receive-location-and-the-mqseries-queue"></a>Para crear la ubicación de recepción y la cola de MQSeries  
  
1.  Abra la consola de administración de BizTalk Server.  
  
2.  Expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda la aplicación necesaria.  
  
3.  Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.  
  
4.  En el **propiedades del puerto de recepción unidireccional** cuadro de diálogo, en la **nombre** cuadro, escriba "MQReply" y haga clic en **Aceptar**.  
  
5.  En el panel izquierdo, haga clic en **ubicaciones de recepción** ficha y, a continuación, haga clic en **nuevo**.  
  
6.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **nombre** , escriba "MQReply".  
  
7.  En el **tipo de transporte** cuadro, seleccione **MQSeries**.  
  
8.  En el **controlador de recepción** cuadro, seleccione **BizTalkServerApplication**.  
  
9. En el **canalización de recepción** cuadro, seleccione **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.  
  
10. Haga clic en **configurar**.  
  
11. En el **propiedades de transporte MQSeries** cuadro de diálogo, en la **intervalo de sondeo** , escriba "10".  
  
12. En el **definición de la cola** cuadro, haga clic en el botón de puntos suspensivos (...).  
  
13. En el **definición de la cola** cuadro de diálogo, en la **nombre del servidor** , escriba el nombre del equipo.  
  
14. En el **Administrador de cola** , seleccione el Administrador de cola predeterminado.  
  
15. En el **cola** , escriba "REPLYTOQ" y, a continuación, haga clic en **exportar**.  
  
16. En el **exportar** cuadro de diálogo, haga clic en **Create Queue**y, a continuación, haga clic en**Aceptar**o **realiza** hasta que haya salido de todos los cuadros de diálogo.  
  
## <a name="creating-the-send-port-and-mqseries-queue"></a>Crear el puerto de envío y la cola MQSeries  
  
#### <a name="to-create-the-send-port-and-mqseries-queue"></a>Para crear el puerto de envío y la cola MQSeries  
  
1.  Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.  
  
2.  En el **propiedades de puerto de envío** cuadro de diálogo, en la **nombre** , escriba "MQSolicitResponse".  
  
3.  En el **tipo de transporte** cuadro, seleccione **MQSeries**.  
  
4.  En el **canalización de envío** cuadro, seleccione **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**.  
  
5.  En el **canalización de recepción** cuadro, seleccione **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.  
  
6.  Haga clic en **configurar**.  
  
7.  En el **propiedades de transporte MQSeries** cuadro de diálogo, en la **definición de la cola** cuadro, haga clic en el botón de puntos suspensivos (...).  
  
8.  En el **definición de la cola** cuadro de diálogo, en la **nombre del servidor** , escriba el nombre del equipo.  
  
9. En el **Administrador de cola** , seleccione el Administrador de cola predeterminado.  
  
10. En el **cola** , escriba "SOLICITRESPONSEQ" y, a continuación, haga clic en **exportar**.  
  
11. En el cuadro de diálogo Exportar, haga clic en **Create Queue**y, a continuación, haga clic en **Aceptar** o **realiza** hasta que haya salido de todos los cuadros de diálogo.  
  
## <a name="enabling-the-receive-location-and-starting-the-send-port"></a>Habilitar la ubicación de recepción e iniciar el puerto de envío  
 Este procedimiento crea las carpetas requeridas para recibir el archivo en la orquestación y envía el mensaje correlacionado y el mensaje de respuesta a las carpetas de salida.  
  
#### <a name="to-enable-the-receive-location-and-start-the-send-port"></a>Para habilitar la ubicación de recepción e iniciar el puerto de envío  
  
1.  En la consola de administración de BizTalk Server, haga clic en **puertos de recepción**.  
  
2.  En el panel de detalles, haga clic en el **MQIn** ubicación de recepción y haga clic en **habilitar**.  
  
3.  En el panel de detalles, haga clic en el **MQOut** puerto de envío y haga clic en **iniciar.**  
  
## <a name="creating-the-folders-used-by-the-application"></a>Crear las carpetas usadas por la aplicación  
  
#### <a name="to-create-the-folders-used-by-the-application"></a>Para crear las carpetas usadas por la aplicación  
  
1.  Si no existe ninguna, cree una carpeta denominada "temp" en la unidad C:\.  
  
2.  Cree las carpetas en el **C:\temp** directorio denominado "Pickup2", "Dropit2" y "MoveIt".  
  
## <a name="modifying-the-orchestration-used-by-the-application"></a>Modificar la orquestación usada por la aplicación  
 Este procedimiento modifica la orquestación usada por la aplicación.  
  
||  
|-|  
|Para modificar la orquestación usada por la aplicación|  
|-En Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], haga doble clic en el archivo de solución, **MQSCorrelationSolicitResponse.sln**, para abrir la solución.<br /><br /> -En el panel Explorador de soluciones, haga doble clic en la orquestación **MQSCorrelationSolicitResponse.odx** para ver la orquestación.<br /><br /> -Haga doble clic en la forma asignación de mensajes **MessageAssignment_1** para iniciar el Editor de expresiones de BizTalk.<br /><br /> : Especifique el nombre de administrador de cola de MQSeries apropiado para la expresión siguiente:<br /><br /> `MQSeriesRequestSendMessage(MQSeries.MQMD_ReplyToQMgr) = "QM_<machine_name>";`<br /><br /> -Si desea que el mensaje de respuesta enviado desde BizTalk contenga todo el contenido del mensaje original en lugar de solo los primeros 100 bytes, modifique la línea siguiente en el Editor de expresiones de BizTalk.<br /><br /> -Línea original:<br /><br /> `MQSeriesRequestSendMessage(MQSeries.MQMD_Report) = 768;`<br /><br /> Cambiar por:<br /><br /> `MQSeriesRequestSendMessage(MQSeries.MQMD_Report) = 1792;`<br /><br /> -En el Editor de expresiones de BizTalk, haga clic en **Aceptar** para guardar la expresión modificada.<br /><br /> -En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], seleccione **archivo**y, a continuación, seleccione **guardar todo**.|  
  
## <a name="building-and-deploying-the-sample"></a>Generar e implementar el ejemplo  
 Este procedimiento genera e implementa la solución que contiene la orquestación usada en esta aplicación.  
  
#### <a name="to-build-and-deploy-the-sample"></a>Para generar e implementar el ejemplo  
  
1.  En una ventana de comandos, desplácese a la siguiente carpeta:  
  
     `<Samples Path>\AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestrationWithSolicitResponse`  
  
2.  Ejecute el archivo Setup.bat que realiza las acciones siguientes:  
  
    1.  Crea una clave de nombre seguro para el proyecto.  
  
    2.  Compila e implementa el proyecto de orquestación.  
  
    3.  Crea un puerto de envío y un puerto de recepción con el adaptador de archivo.  
  
    > [!NOTE]
    >  Puesto que esta orquestación especifica los enlaces para el envío y la recepción de archivos con el adaptador de archivos, al implementar la orquestación, se crearán los puertos de envío, puertos de recepción y la ubicación de recepción necesarios para la recepción de un archivo en la orquestación y la salida del mensaje de correlación y el mensaje de respuesta.  
  
## <a name="binding-and-starting-the-orchestration"></a>Enlazar e iniciar la orquestación  
 Este procedimiento enlaza la orquestación al host y a los puertos de envío y ubicaciones de recepción correspondientes.  
  
#### <a name="to-bind-and-start-the-orchestration"></a>Procedimiento para enlazar e iniciar la orquestación  
  
1.  En la consola de administración de BizTalk Server, expanda el **orquestaciones** carpeta.  
  
2.  En el panel de detalles, haga clic en el **MQSCorrelationSolicitResponse** orquestación y haga clic en **enlazar**.  
  
3.  Enlace los puertos de orquestación con los siguientes puertos de envío y ubicaciones de recepción:  
  
    |**Puerto de orquestación**|**Puerto de mensajería / ubicación de recepción**|  
    |----------------------------|--------------------------------------------|  
    |FileReceivePort|MQSCorrelationSolicitResponse.Orchestration.FileReceivePort|  
    |MQSeriesResponseReceivePort|MQReply|  
    |SolicitResponsePort|MQSolicitResponse|  
    |TempPort|MQSCorrelationSolicitResponse.Orchestration.TempPort|  
    |FileSendPort|MQSCorrelationSolicitResponse.Orchestration.FileSendPort|  
  
4.  Haga clic en **Host**.  
  
5.  En el **Host** cuadro, seleccione **BizTalkServerApplication** y haga clic en **Aceptar**.  
  
6.  En **puertos de envío**, haga clic en **MQSCorrelationSolicitResponse.Orchestration.TempPort**y, a continuación, seleccione **iniciar**.  
  
7.  En **puertos de envío**, haga clic en **MQSCorrelationSolicitResponse.Orchestration.FileSendPort**y, a continuación, seleccione **iniciar**.  
  
8.  En **ubicaciones de recepción**, haga clic en **MQSCorrelationSolicitResponse.Orchestration.FileReceivePort**y, a continuación, seleccione **habilitar**.  
  
9. Haga clic en la orquestación y haga clic en **iniciar**.  
  
    > [!NOTE]
    >  Además, iniciar la orquestación da de alta la orquestación de forma automática.  
  
## <a name="testing-the-application"></a>Probar la aplicación  
 Este procedimiento comprueba la aplicación.  
  
#### <a name="to-test-the-application"></a>Para probar la aplicación  
  
1.  Coloque un archivo el **C:\Temp\Pickup2** carpeta.  
  
2.  Examine los archivos de la **C:\Temp\Dropit2** carpeta y el **C:\Temp\Moveit**carpeta.  
  
    -   El **C:\Temp\Dropit2** carpeta debe contener una copia del mensaje que ha recogido originalmente por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
    -   El **C:\Temp\Moveit**carpeta debería contener un documento de respuesta con el identificador de mensaje (MQMD_MsgId) y el identificador de correlación (MQMD_CorrelId).  
  
    > [!NOTE]
    >  Si deshabilita la **MQReply** ubicación de recepción, puede examinar el mensaje en WebSphere MQ Explorer y observar que se establecen los identificadores de mensaje y correlación. Para ello, inicie la **WebSphere MQ Explorer** y examine el mensaje colocado en el **REPLYTOQ** cola. Los identificadores de mensaje y correlación aparecen en la **identificadores** pestaña de la **Messageproperties** cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Correlacionar mensajes mediante la solicitud y respuesta](../core/correlating-messages-using-request-reply.md)   
 [Ejemplos de adaptadores de MQSeries](../core/mqseries-adapter-samples.md)