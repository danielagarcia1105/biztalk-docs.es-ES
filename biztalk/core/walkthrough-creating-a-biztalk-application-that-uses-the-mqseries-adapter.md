---
title: "Tutorial: Crear una aplicación de BizTalk que utiliza el adaptador de MQSeries | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IBM WebSphere MQ queues
- MQSeries adapters, tutorial
- MQSeries adapters, testing
- tutorials, MQSeries adapters
- MQSeries adapters, IBM WebSphere MQ queues
- testing, MQSeries adapters
- MQSeries adapters, queues
- configuring [MQSeries adapters], tutorial
ms.assetid: e9e169e4-d41c-4e5d-b165-7bd36b481f24
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0132387b86e048c26c0dab61ca174f3e10c55012
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-creating-a-biztalk-application-that-uses-the-mqseries-adapter"></a>Tutorial: Crear una aplicación de BizTalk que usa el adaptador de MQSeries
Esta sección le muestra cómo crear una sencilla aplicación de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que utilice el adaptador de MQSeries.  
  
> [!NOTE]
>  La aplicación supone que tiene instalado IBM WebSphere MQ, componente del servidor para las plataformas de Windows, en el mismo equipo que BizTalk Server. Asimismo, supone que todavía no ha creado ningún puerto de envío o ubicaciones de recepción. Si dispone de puertos de envío o ubicaciones de recepción existentes, sustituya los nombres correspondientes cuando siga los pasos.  
  
 La aplicación es una sencilla aplicación de enrutamiento por contenidos que sólo utiliza un puerto de envío o una ubicación de recepción. La ubicación de recepción lee de una cola de IBM WebSphere MQ. El puerto de envío obtiene el mensaje a partir de la ubicación de recepción y lo envía a una cola diferente de IBM WebSphere MQ.  
  
 Para crear la aplicación, debe crear las colas de IBM WebSphere MQ, configurar el puerto de envío y la ubicación de recepción de BizTalk Server, iniciar el puerto de envío, habilitar la ubicación de recepción y colocar un mensaje de prueba en la cola.  
  
 Si dispone de los permisos necesarios para instalar IBM WebSphere MQ, puede crear colas de IBM WebSphere MQ mediante los cuadros de diálogo del adaptador y omitir el procedimiento siguiente. Si no dispone de este acceso, puede crear colas mediante IBM WebSphere MQ, componentes cliente para el explorador de las plataformas de Windows. Para crear las colas mediante el complemento de IBM WebSphere MQ Explorer, realice el procedimiento siguiente:  
  
## <a name="to-create-the-ibm-websphere-mq-queues-through-the-ibm-websphere-mq-explorer"></a>Para crear las colas de IBM WebSphere MQ mediante IBM WebSphere MQ Explorer  
 Para crear las colas de IBM WebSphere MQ mediante IBM WebSphere MQ Explorer, siga estos pasos:  
  
1.  Haga clic en **iniciar**, seleccione **programas**, seleccione **IBM WebSphere MQ**y, a continuación, haga clic en **WebSphere MQ Explorer**.  
  
2.  Haga doble clic en **administradores de cola**y, a continuación, haga doble clic en el Administrador de cola predeterminado. El Administrador de cola predeterminado se suele llamar **QM_***< nombre_equipo >* donde *nombre_equipo* es el nombre del equipo.  
  
3.  Haga clic en **colas**, seleccione **New**y, a continuación, haga clic en **cola Local**.  
  
4.  En **Create Local Queue** cuadro de diálogo **nombre de la cola**, tipo **BTStoMQS**y, a continuación, haga clic en **Aceptar**.  
  
5.  Haga clic en **colas**, seleccione **New**y, a continuación, haga clic en **cola Local**.  
  
6.  En **Create Local Queue** cuadro de diálogo **nombre de la cola**, tipo **MQStoBTS**y, a continuación, haga clic en **Aceptar**.  
  
 En los siguientes pasos se crea el puerto de envío y la ubicación de recepción, se inicia el puerto de envío y la ubicación de recepción. También se crean las colas de IBM WebSphere MQ.  
  
## <a name="to-create-the-receive-location-and-the-mqseries-queue"></a>Para crear la ubicación de recepción y la cola de MQSeries  
 Para crear la ubicación de recepción y la cola de MQSeries, siga estos pasos:  
  
1.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el valor predeterminado aplicación (**BizTalk Application 1** de forma predeterminada).  
  
2.  Haga clic en el **puertos de recepción** nodo, haga clic en **New**y seleccione **Puerto unidireccional**.  
  
3.  En el **propiedades de puerto de recepción** cuadro de diálogo, en la **nombre** , escriba **MQStoBTS**.  
  
4.  En el panel izquierdo, haga clic en **ubicaciones de recepción**y en el panel derecho, haga clic en **nuevo**.  
  
5.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **nombre** , escriba **MQStoBTS**.  
  
6.  Seleccione **MQSeries** en la lista desplegable lista junto a la **tipo** opción.  
  
7.  En el **transporte** sección, haga clic en **configurar**.  
  
8.  En el **propiedades de transporte MQSeries** cuadro de diálogo, en la **intervalo de sondeo** , escriba **1**.  
  
9. En el **definición de la cola** cuadro, haga clic en el botón de puntos suspensivos (**...** ) botón.  
  
10. En el **definición de la cola** cuadro de diálogo, en la **nombre del servidor** , escriba el nombre del equipo.  
  
11. En el **Administrador de cola** , seleccione el Administrador de cola predeterminado.  
  
12. En el **cola** , escriba **MQStoBTS**y, a continuación, haga clic en **exportar**.  
  
13. En el **exportar** cuadro de diálogo, haga clic en **Create Queue**y, a continuación, haga clic en **Aceptar** y **Aceptar** para regresar a la **recepción Propiedades de la ubicación** cuadro de diálogo.  
  
14. En el **controlador de recepción** cuadro, seleccione **BizTalkServerApplication**.  
  
15. En el **canalización de recepción** cuadro, seleccione **PassThruReceive**.  
  
16. Haga clic en **Aceptar** para aplicar los cambios.  
  
## <a name="to-create-the-send-port-and-the-mqseries-queue"></a>Para crear el puerto de envío y la cola de MQSeries  
 Para crear el puerto de envío y la cola de MQSeries, siga estos pasos:  
  
1.  Haga clic en **puertos de envío**, haga clic en **New**y seleccione **puerto de envío unidireccional estático**.  
  
2.  En el **propiedades de puerto de envío** cuadro de diálogo, en la **nombre** , escriba **BTStoMQS.**  
  
3.  Seleccione **MQSeries** en la lista desplegable lista junto a la **tipo** opción.  
  
4.  En el **transporte** sección, haga clic en **configurar**.  
  
5.  En el **propiedades de transporte MQSeries** cuadro de diálogo, en la **definición de la cola** cuadro, haga clic en el botón de puntos suspensivos (**...** ) botón.  
  
6.  En el **definición de la cola** cuadro de diálogo, en la **nombre del servidor** , escriba el nombre del equipo.  
  
7.  En el **Administrador de cola** , seleccione el Administrador de cola predeterminado.  
  
8.  En el **cola** , escriba **BTStoMQS**y, a continuación, haga clic en **exportar**.  
  
9. En el **exportar** cuadro de diálogo, haga clic en **Create Queue**y, a continuación, haga clic en **Aceptar** y **Aceptar** para regresar a la **puerto de envío Propiedades** cuadro de diálogo.  
  
10. En el **canalización de envío** cuadro, seleccione **PassThruTransmit**.  
  
11. Haga clic para seleccionar **filtros** en el panel izquierdo y, a continuación, configurar las opciones de filtro en el panel derecho.  
  
12. En el **propiedad** lista desplegable, seleccione **BTS. ReceivePortName**.  
  
13. En el **valor** , escriba **MQStoBTS**.  
  
14. Haga clic en **Aceptar** para aplicar los cambios.  
  
## <a name="to-enable-the-receive-location-and-start-the-send-port"></a>Para habilitar la ubicación de recepción e iniciar el puerto de envío  
 Para habilitar la ubicación de recepción e iniciar el puerto de envío, siga estos pasos:  
  
1.  Haga clic en el **MQStoBTS** ubicación de recepción y, a continuación, haga clic en **habilitar**.  
  
2.  Haga clic en el **BTStoMQS** puerto de envío y, a continuación, haga clic en **iniciar**.  
  
 El paso siguiente es comprobar la aplicación mediante el envío de un mensaje de prueba a la cola de recepción.  
  
## <a name="to-test-the-application"></a>Para probar la aplicación  
 Para probar la aplicación, siga estos pasos:  
  
1.  Haga clic en **iniciar**, seleccione **programas**, seleccione **IBM WebSphere MQ**y, a continuación, haga clic en **WebSphere MQ Explorer**.  
  
2.  Haga clic en **MQStoBTS**y, a continuación, haga clic en **Put Test Message**.  
  
3.  En el **datos del mensaje** , escriba un mensaje de prueba. Haga clic en **Aceptar**.  
  
 Después de escribir los datos, el **Current Depth** para el **MQStoBTS** cola es uno (1). Si la aplicación procesa el mensaje, el recuento vuelve a cero (0) y la **Current Depth** para **BTStoMQS** se convierte en uno (1). También puede ver el contenido del mensaje.  
  
## <a name="to-view-the-message"></a>Para ver el mensaje  
 Para ver el mensaje, siga estos pasos:  
  
1.  Haga doble clic en el **BTStoMQS** cola.  
  
2.  Haga doble clic en el mensaje y, a continuación, seleccione la **datos** hoja. Puede ver el texto del mensaje en el **datos del mensaje** cuadro.  
  
3.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [¿Qué es el adaptador de MQSeries?](../core/what-is-the-mqseries-adapter.md)   
 [Arquitectura del adaptador de MQSeries](../core/mqseries-adapter-architecture.md)