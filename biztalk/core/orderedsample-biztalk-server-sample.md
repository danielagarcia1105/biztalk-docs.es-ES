---
title: OrderedSample (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, MQSeries adapters
- orchestrations, examples
- examples, orchestrations
- MQSeries adapters, examples
ms.assetid: 7e59ff43-d425-40cd-9725-af13084f83d9
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b9e93c7bb9cb59088e465dc53dd992ffd5f1c11
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974754"
---
# <a name="orderedsample-biztalk-server-sample"></a>OrderedSample (ejemplo de BizTalk Server)
El ejemplo OrderedSample muestra cómo usar una orquestación para recibir y enviar un serie ordenada de mensajes en un modo de envío y recepción.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 El ejemplo asume que existen mensajes en la cola MQSeries desde la que recibe mensajes. Cuando el adaptador lee los mensajes de la cola MQSeries, lo hace en orden y los envía a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 El puerto de recepción en la orquestación, **mqreceive**, tiene su **entrega ordenada** propiedad establecida en **True**.  
  
 En cuanto al envío, la orquestación envía un mensaje y, a continuación, espera por la notificación de entrega antes de enviar el siguiente mensaje. El puerto de envío **mqsend** tiene su **notificación de entrega** propiedad establecida en **transmitido**. Para que el ejemplo siga siendo sencillo, la orquestación usa un bucle infinito.  
  
 La orquestación puede recibir lotes de mensajes, así como un único mensaje.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 *\<Ejemplos de ruta de acceso\>* \AdaptersUsage\MQSeriesAdapter\OrderedSample  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivo|Description|  
|----------|-----------------|  
|OrderedReceiveSend.btproj,<br /><br /> OrderedReceiveSend.sln|Archivos de proyectos y soluciones para la aplicación.|  
|OrderedReceiveSendOrchestration.odx|La orquestación de la aplicación.|  
|OrderedSample.snk|Archivo de clave de nombre seguro.|  
|**Setup.bat**|Crea e inicializa este ejemplo.|  
  
## <a name="building-and-running-the-sample"></a>Generar y ejecutar el ejemplo  
  
#### <a name="to-build-and-deploy-the-sample"></a>Para generar e implementar el ejemplo  
  
1.  En una ventana de comandos, desplácese a la siguiente carpeta:  
  
     `<Samples Path>\AdaptersUsage\MQSeriesAdapter\OrderedSample`  
  
2.  Ejecute el archivo Setup.bat que realiza las acciones siguientes:  
  
    1.  Crea una clave de nombre seguro para el proyecto.  
  
    2.  Compila e implementa el proyecto de orquestación.  
  
 Si dispone de los permisos necesarios para la instalación de MQSeries Server para Windows, puede crear la cola MQSeries mediante los cuadros de diálogo del adaptador y puede omitir el procedimiento siguiente. Si no dispone de este acceso, puede crear la cola con IBM WebSphere MQ Explorer. Para crear las colas con WebSphere MQ Explorer, realice los siguientes pasos.  
  
## <a name="creating-the-mqseries-queues-through-the-websphere-mq-explorer"></a>Crear las colas MQSeries con WebSphere MQ Explorer  
  
#### <a name="to-create-the-mqseries-queues-through-the-websphere-mq-explorer"></a>Para crear las colas MQSeries con WebSphere MQ Explorer  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **IBM WebSphere MQ**y, a continuación, haga clic en **WebSphere MQ Explorer**.  
  
2.  Haga doble clic en **administradores de cola**y, a continuación, haga doble clic en el **Administrador de cola predeterminado**. Normalmente, el administrador de cola predeterminado se denomina QM_<nombre_equipo>, donde nombre_equipo es el nombre del equipo.  
  
3.  Haga clic en **colas**, seleccione **New**y, a continuación, haga clic en **cola Local**.  
  
4.  En **Create Local Queue** cuadro de diálogo **nombre de la cola**, tipo **"queue1"** y, a continuación, haga clic en **Aceptar**.  
  
5.  Haga clic en **colas**, haga clic en **New**y, a continuación, haga clic en **cola Local**.  
  
6.  En el **Create Local Queue** cuadro de diálogo **nombre de la cola**, tipo **"queue2"** y, a continuación, haga clic en **Aceptar**.  
  
## <a name="creating-the-receive-location-and-the-mqseries-queue"></a>Crear la ubicación de recepción y la cola MQSeries  
 Este procedimiento crea el puerto de envío y la ubicación de recepción para enviar el mensaje y recibir el mensaje de correlación de MQSeries. La cola MQSeries también se creará al crear la ubicación de recepción si no se ha creado anteriormente.  
  
#### <a name="to-create-the-receive-location-and-the-mqseries-queue"></a>Para crear la ubicación de recepción y la cola de MQSeries  
  
1.  Abra la consola de administración de BizTalk Server.  
  
2.  Expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda la aplicación necesaria.  
  
3.  Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.  
  
4.  En el **propiedades del puerto de recepción unidireccional** cuadro de diálogo, en la **nombre** cuadro, escriba **OrderedSampleReceive** y haga clic en **Aceptar**.  
  
5.  En el panel izquierdo, haga clic en **ubicaciones de recepción** ficha y, a continuación, haga clic en **nuevo**.  
  
6.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **nombre** cuadro, escriba "**OrderedSampleReceiveLocation**".  
  
7.  En el **tipo de transporte** cuadro, seleccione **MQSeries**.  
  
8.  En el **controlador de recepción** cuadro, seleccione **BizTalkServerApplication**.  
  
9. En el **canalización de recepción** cuadro, seleccione **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.  
  
10. Haga clic en **configurar**.  
  
11. En el **propiedades de transporte MQSeries** cuadro de diálogo, en la **intervalo de sondeo** , escriba **"10"**.  
  
12. En el **definición de la cola** cuadro, haga clic en el **puntos suspensivos (...)**  botón.  
  
13. En el **definición de la cola** cuadro de diálogo, en la **nombre del servidor** , escriba el nombre del equipo.  
  
14. En el **Administrador de cola** cuadro, seleccione la **Administrador de cola predeterminado**.  
  
15. En el **cola** , escriba " **queue1**" y, a continuación, haga clic en **exportar**.  
  
16. En el **exportar** cuadro de diálogo, haga clic en **Create Queue**y, a continuación, haga clic en **Aceptar** o **realiza** hasta que haya salido de todos los cuadros de diálogo.  
  
## <a name="creating-the-send-port-and-mqseries-queue"></a>Crear el puerto de envío y la cola MQSeries  
  
#### <a name="to-create-the-send-port-and-mqseries-queue"></a>Para crear el puerto de envío y la cola MQSeries  
  
1.  Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.  
  
2.  En el **propiedades del puerto estático** cuadro de diálogo, en la **nombre** , escriba "**OrderedSampleSend**".  
  
3.  En el **tipo de transporte** cuadro, seleccione **MQSeries**.  
  
4.  En el **canalización de envío** cuadro, seleccione **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**.  
  
5.  Haga clic en **configurar**.  
  
6.  En el **propiedades de transporte MQSeries** cuadro de diálogo, en la **definición de la cola** cuadro, haga clic en el **puntos suspensivos (...)**  botón.  
  
7.  En el **definición de la cola** cuadro de diálogo, en la **nombre del servidor** , escriba el nombre del equipo.  
  
8.  En el **Administrador de cola** cuadro, seleccione la **Administrador de cola predeterminado**.  
  
9. En el **cola** , escriba " **queue2**" y, a continuación, haga clic en **exportar**.  
  
10. En el **exportar** cuadro de diálogo, haga clic en **Create Queue**y, a continuación, haga clic en **Aceptar** o **realiza** hasta que haya salido de todos los cuadros de diálogo.  
  
#### <a name="to-enable-the-receive-location-and-start-the-send-port"></a>Para habilitar la ubicación de recepción e iniciar el puerto de envío  
  
1.  En la consola de administración de BizTalk Server, haga clic en **puertos de recepción**.  
  
2.  En el panel de detalles, haga clic en el **MQIn** ubicación de recepción y haga clic en **habilitar**.  
  
3.  En el panel de detalles, haga clic en el **MQOut** puerto de envío y haga clic en **iniciar.**  
  
#### <a name="to-bind-and-start-the-orchestration"></a>Para enlazar e iniciar la Orquestación  
  
1.  En la consola de administración de BizTalk Server, expanda el **orquestaciones** carpeta.  
  
2.  Haga doble clic en el **OrderedSampleOrchestration** orquestación y, a continuación, haga clic en **enlaces**.  
  
3.  Enlace los puertos de orquestación con los siguientes puertos de envío y ubicaciones de recepción:  
  
    |Puerto de orquestación|Puerto de mensajería/ubicación de recepción|  
    |------------------------|----------------------------------------|  
    |mqreceive|OrderedSampleReceive|  
    |mqsend|OrderedSampleSend|  
  
4.  Haga clic en **Host**.  
  
5.  En el **Host** cuadro, seleccione **BizTalkServerApplication**y haga clic en **Aceptar**.  
  
6.  Haga clic con el **orquestación** y haga clic en **iniciar**.  
  
#### <a name="to-run-the-sample"></a>Para ejecutar el ejemplo  
  
1.  Iniciar la orquestación.  
  
2.  Colocar los mensajes en la cola MQSeries desde la que ha configurado la ubicación de recepción para realizar la lectura.  
  
3.  Ver los mensajes en la cola de envío de WebSphere MQ Explorer en la que ha configurado el puerto de envío para enviar mensajes.  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos del adaptador de MQSeries](../core/mqseries-adapter-samples.md)