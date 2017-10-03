---
title: "Paso 3a: recibir una notificación de oportunidad de Salesforce en BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: be9de6e3-6bd9-4275-b2fb-0a756c51aabf
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76ab28e8e70c0b8a222f6772a763a93252f2c413
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3a-receive-salesforce-opportunity-notification-into-biztalk-server"></a>Paso 3a: recibir una notificación de oportunidad de Salesforce en BizTalk Server
En este paso, comenzamos creando un servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Debemos incluir primero el esquema para el mensaje de notificación de oportunidades que obtendremos de Salesforce y después comenzaremos a crear una orquestación para procesar el mensaje.  
  
### <a name="to-include-the-salesforce-opportunities-notification-schema"></a>Para incluir el esquema de notificación de oportunidades de Salesforce  
  
1.  Inicie sesión en el portal Salesforce.com. En el portal de Salesforce, haga clic en el nombre de inicio de sesión en la esquina superior derecha de la página y, a continuación, haga clic en **el programa de instalación**.  
  
2.  En el panel izquierdo, bajo **el programa de instalación de la aplicación**, expanda **crear**, expanda **flujo de trabajo y aprobaciones**y, a continuación, haga clic en **reglas de flujo de trabajo**.  
  
3.  En el **todas las reglas de flujo de trabajo** página, haga clic en el **oportunidad cerrada** flujo de trabajo que creó anteriormente.  
  
4.  En el **oportunidad cerrada** página de la regla de flujo de trabajo, haga clic en **NewOp1** acción de flujo de trabajo de mensaje saliente.  
  
5.  En el **NewOp1** acción de flujo de trabajo de mensaje saliente de página, haga clic en el vínculo **clic de WSDL**, haga clic en **Guardar destino como**y, a continuación, especifique la ubicación donde desea guardar el WSDL.  
  
    > [!NOTE]
    >  Debe guardar el archivo con la extensión .wsdl.  
  
6.  Crear un servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. Para este tutorial, daremos el nombre del proyecto como `BtsSalesforceIntegration`.  
  
7.  Haga clic en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el Explorador de soluciones, seleccione **agregar**y, a continuación, haga clic en **agregar elementos generados**.  
  
8.  En el **agregar elementos generados** cuadro de diálogo, haga clic en **consumir servicio WCF**y, a continuación, haga clic en **agregar** para iniciar el **consumición de servicio de WCF de BizTalk**asistente. En la página de bienvenida, haga clic en **siguiente**.  
  
9. En el **origen de metadatos** página, seleccione la **archivos de metadatos (WSDL y XSD)** opción y, a continuación, haga clic en **siguiente**.  
  
10. En el **archivos de metadatos** página, haga clic en **agregar**y, a continuación, navegue hasta la ubicación donde guardó el archivo WSDL descargado desde el portal de Salesforce. Seleccione el archivo WSDL y, a continuación, haga clic en **siguiente**.  
  
11. En la página siguiente, establezca el espacio de nombres como `NotificationService` y, a continuación, haga clic en **importación**. El asistente agrega los archivos de esquema y una orquestación al proyecto [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El esquema de mensaje para recibir notificaciones de oportunidades de Salesforce es **NotificationService_soap_sforce_com_2005_09_outbound.xsd**.  
  
### <a name="to-create-an-orchestration-to-receive-the-notification-message"></a>Para crear una orquestación para recibir el mensaje de notificación  
  
1.  Después de completar la **consumición de servicio de WCF de BizTalk** asistente, una orquestación (**NotificationService.odx**, en este ejemplo) se agrega a la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proyecto.  
  
2.  Abra el archivo de orquestación y, en la vista Orquestación, agregue dos variables de mensaje nuevas. Denomínelos `NotificationMessage` y `NotificationAck`. Establezca el tipo de mensaje para estas variables de mensaje como se indica a continuación:  
  
    1.  Establecer **NotificationMessage** a *NotificationService.NotificationService_soap_sforce_com_2005_09_outbound.notifications*. Esta variable de mensaje representa el mensaje de notificación de oportunidad recibido de Salesforce.  
  
    2.  Establecer **NotificationAck** a *NotificationService.NotificationService_soap_sforce_com_2005_09_outbound.notificationsResponse*. Esta variable de mensaje representa el mensaje de confirmación de notificación de oportunidad enviado a Salesforce.  
  
3.  Agregar una forma Recepción a la orquestación. Establezca las siguientes propiedades en la forma:  
  
    1.  Establecer **activar** a **True**.  
  
    2.  Establecer **nombre** a *ReceiveNotificationMessage*.  
  
    3.  Establecer **mensaje** a *NotificationMessage*.  
  
4.  Agregue una forma Construir mensaje después de la forma Recepción. Nombre de la forma de mensaje `ConstructNotificationResponse` y establezca el **mensajes construidos** propiedad `NotificationAck`. Como parte de la forma Construir mensaje, crearemos también una asignación para generar un mensaje de confirmación de notificación para enviarlo a Salesforce.  
  
    1.  Dentro de la forma Construir mensaje, agregue una forma Transformación. Haga doble clic en la forma transformación y en el cuadro de diálogo Configuración de transformación, seleccione la **nueva asignación** opción.  
  
    2.  Especifique el nombre de asignación `BtsSalesforceIntegration.MapNotificationResponse`.  
  
    3.  Establezca el origen **NotificationMessage** y el destino **NotificationAck**.  
  
    4.  Asegúrese de que la casilla de verificación **iniciar el asignador de BizTalk al hacer clic en Aceptar,** está seleccionada.  
  
    5.  En **MapNotificationResponse.btm**, vamos a crear una respuesta de notificación para enviar a Salesforce. Cada vez que Salesforce envía una notificación, espera una confirmación de vuelta. El esquema del mensaje de respuesta de notificación muestra que la **confirmación** elemento de la respuesta es de tipo booleano. Por lo tanto, en la asignación, debe quitar un **Value Mapping** functoid y establezca sus dos valores de entrada (condición y resultado) a `true`. Haga clic en **Aceptar** para guardar el functoid.  
  
    6.  Conectar el **Value Mapping** functoid para el **confirmación** elemento del esquema de destino.  
  
5.  En la orquestación, después de la forma Construir mensaje, agregue una forma Envío que se usará para enviar la confirmación a Salesforce.  
  
    -   Establecer **nombre** a *SendNotificationAck*.  
  
    -   Establecer **mensaje** a *NotificationAck*.  
  
6.  En la orquestación, agregue un puerto para recibir el mensaje de notificación de Salesforce y enviar la confirmación en respuesta. En el Asistente para configuración de puertos, seleccione las siguientes opciones:  
  
    -   Especifique el nombre de puerto `SalesforceNotificationPort`.  
  
    -   Seleccione la opción Crear un nuevo tipo de puerto.  
  
    -   Establecer **patrón de comunicación** a *solicitud-respuesta*.  
  
    -   Establecer **dirección de puerto de comunicación** a *podrá recibir una solicitud y enviaré una respuesta* y establecer **enlace de puerto** a *especificar posterior*.  
  
     Conectar el **solicitar** operación del puerto a la forma recepción (*ReceiveNotificationMessage*) y la **respuesta** operación del puerto de la forma envío (*SendNotificationAck*). La siguiente captura de pantalla muestra la parte de la orquestación que recibe una notificación de oportunidad de Salesforce y envía una confirmación de vuelta:  
  
     ![Recibir una notificación de oportunidad y enviar respuesta](../core/media/bts-sf-recvnotificationorch.jpg "BTS_SF_RecvNotificationOrch")  
  
 Por ahora, hemos configurado la solución donde se recibe una notificación de oportunidad de Salesforce y se envía una confirmación de vuelta. En los temas siguientes, ampliaremos esta solución para comenzar a procesar la notificación de oportunidad con el fin de obtener más detalles acerca del tipo de oportunidad de venta disponible.  
  
## <a name="see-also"></a>Vea también  
 [Paso 3: Crear la solución de BizTalk Server en Visual Studio](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)