---
title: Cómo crear una aplicación .NET para probar un servicio WCF publicado con el Asistente de publicación de servicios de WCF de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF services, .NET applications
- WCF services, WCF Service Publishing Wizard
- creating, .NET applications [WCF services]
- WCF Service Publishing Wizard
ms.assetid: 17e39db2-8471-4f6f-a7f1-833023cdbc39
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb46847361127a915d06ee74eaed549caf40258a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287236"
---
# <a name="how-to-create-a-net-application-to-test-a-wcf-service-published-with-the-biztalk-wcf-service-publishing-wizard"></a>Cómo crear una aplicación .NET para probar un Servicio WCF publicado con el Asistente para publicación de Servicio WCF de BizTalk
Para probar un Servicio WCF publicado, puede crear una aplicación .NET que consuma el Servicio WCF publicado. En este tema se describe cómo crear una aplicación .NET para probar un Servicio WCF publicado.  
  
> [!NOTE]
>  La colección de Ayuda de Visual Studio contiene un tutorial muy valioso para crear una aplicación .NET que consuma servicios WCF. Puede utilizar el tutorial para probar el Servicio WCF publicado. Para obtener información y procedimientos acerca de cómo crear un proyecto de cliente WCF, vea "Tutorial: obtener acceso a un XML Web Service Using Visual Basic o Visual C#" en la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ayudar a la colección [http://go.microsoft.com/fwlink/?LinkId=62263](http://go.microsoft.com/fwlink/?LinkId=62263).  
  
> [!NOTE]
>  Este tema usa la herramienta de utilidad de metadatos del modelo de servicio (SvcUtil.exe) para crear las clases de proxy de WCF y el archivo de configuración de la aplicación. El archivo SvcUtil.exe está incluido en el kit de desarrollo de software (SDK) de Microsoft Windows de los componentes en tiempo de ejecución de .NET Framework y Windows Vista.  
  
### <a name="to-create-a-simple-wcf-proxy-class-and-application-configuration-file"></a>Para crear una clase de proxy de WCF simple y un archivo de configuración de la aplicación  
  
1.  Abra el Shell CMD como sigue: haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Windows SDK**y, a continuación, haga clic en **Shell de CMD**.  
  
2.  En el shell de CMD, obtenga acceso al directorio en el que desee colocar la clase de proxy y el archivo de configuración de la aplicación.  
  
3.  En el shell de CMD, ejecute la herramienta de utilidad de metadatos del modelo de servicio (SvcUtil.exe) para crear la clase de proxy de WCF y el archivo de configuración de la aplicación para el Servicio WCF publicado como se indica a continuación:  
  
    ```  
    svcutil <http://servername/apppath/wcfservicename.svc> /config:App.config  
    ```  
  
    > [!NOTE]
    >  Esta línea de comandos genera BizTalkServiceInstance.cs para la clase de proxy y App.config para el archivo de configuración de la aplicación. Para obtener más información acerca de Svcutil.exe, vea "Service Model Metadata utilidad Tool (Svcutil.exe)" en [http://go.microsoft.com/fwlink/?LinkId=74696](http://go.microsoft.com/fwlink/?LinkId=74696).  
  
### <a name="to-compile-your-net-application-that-consumes-the-published-wcf-service"></a>Para compilar la aplicación .NET que consume el Servicio WCF publicado  
  
1.  En el Explorador de soluciones de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], agregue los archivos que crea SvcUtil.exe, BizTalkServiceInstance y App.config al proyecto.  
  
2.  En el Explorador de soluciones de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], asegúrese de que agrega una referencia a System.ServiceModel.dll para compilar el código de proxy.  
  
3.  Cree el código para usar el código de proxy generado. El siguiente código muestra cómo usar el proxy generado:  
  
    ```  
    DeliveryNotification deliveryNotification= new DeliveryNotification();  
    deliveryNotification.TrackingNumber = "001";  
                Microsoft_Samples_BizTalk_WCFBasicHttp_BizTalkApp_DliveryRequestProcess_DeliveryNotificatonReceivePortClient service = new Microsoft_Samples_BizTalk_WCFBasicHttp_BizTalkApp_DliveryRequestProcess_DeliveryNotificatonReceivePortClient("BasicHttpBinding_ITwoWayAsyncVoid");  
    service.Submit(deliveryNotification);  
    ```  
  
4.  Ejecute la aplicación .NET para enviar mensajes al Servicio WCF publicado.  
  
## <a name="see-also"></a>Vea también  
 [Consideraciones al publicar servicios WCF con WCF adaptadores de recepción](../core/considerations-when-publishing-wcf-services-with-the-wcf-receive-adapters.md)