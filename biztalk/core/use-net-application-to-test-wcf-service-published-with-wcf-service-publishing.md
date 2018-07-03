---
title: Cómo crear una aplicación .NET para probar un servicio WCF publicado con el Asistente para publicar el servicio de WCF de BizTalk | Microsoft Docs
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
ms.openlocfilehash: d81b18e4fe2180ed3d4e58bfb7bec5e31c1d6a84
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996645"
---
# <a name="how-to-create-a-net-application-to-test-a-wcf-service-published-with-the-biztalk-wcf-service-publishing-wizard"></a><span data-ttu-id="3fb4a-102">Cómo crear una aplicación .NET para probar un Servicio WCF publicado con el Asistente para publicación de Servicio WCF de BizTalk</span><span class="sxs-lookup"><span data-stu-id="3fb4a-102">How to Create a .NET Application to Test a WCF Service Published with the BizTalk WCF Service Publishing Wizard</span></span>
<span data-ttu-id="3fb4a-103">Para probar un Servicio WCF publicado, puede crear una aplicación .NET que consuma el Servicio WCF publicado.</span><span class="sxs-lookup"><span data-stu-id="3fb4a-103">To test your published WCF service, you can create a .NET application that consumes your published WCF service.</span></span> <span data-ttu-id="3fb4a-104">En este tema se describe cómo crear una aplicación .NET para probar un Servicio WCF publicado.</span><span class="sxs-lookup"><span data-stu-id="3fb4a-104">This topic describes how to create a .NET application to test a published WCF service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3fb4a-105">La colección de Ayuda de Visual Studio contiene un tutorial muy valioso para crear una aplicación .NET que consuma servicios WCF.</span><span class="sxs-lookup"><span data-stu-id="3fb4a-105">The Visual Studio Help Collection contains a valuable walkthrough for creating a .NET application that consumes WCF services.</span></span> <span data-ttu-id="3fb4a-106">Puede utilizar el tutorial para probar el Servicio WCF publicado.</span><span class="sxs-lookup"><span data-stu-id="3fb4a-106">You can use the walkthrough to test your published WCF service.</span></span> <span data-ttu-id="3fb4a-107">Para obtener información y procedimientos acerca de cómo crear un proyecto de cliente WCF, vea "Tutorial: acceso a un XML Web Service utilizando Visual Basic o Visual C#" en la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] colección de ayuda en [ http://go.microsoft.com/fwlink/?LinkId=62263 ](http://go.microsoft.com/fwlink/?LinkId=62263).</span><span class="sxs-lookup"><span data-stu-id="3fb4a-107">For information and procedures about creating a WCF client project, see "Walkthrough: Accessing an XML Web Service Using Visual Basic or Visual C#" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Help Collection at [http://go.microsoft.com/fwlink/?LinkId=62263](http://go.microsoft.com/fwlink/?LinkId=62263).</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="3fb4a-108">Este tema usa la herramienta de utilidad de metadatos del modelo de servicio (SvcUtil.exe) para crear las clases de proxy de WCF y el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3fb4a-108">This topic uses the Service Model Metadata Utility tool (SvcUtil.exe) to create the WCF proxy classes and application configuration file.</span></span> <span data-ttu-id="3fb4a-109">El archivo SvcUtil.exe está incluido en el kit de desarrollo de software (SDK) de Microsoft Windows de los componentes en tiempo de ejecución de .NET Framework y Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="3fb4a-109">SvcUtil.exe is included in the Microsoft Windows Software Development Kit (SDK) of Windows Vista and .NET Framework Runtime Components.</span></span>  
  
### <a name="to-create-a-simple-wcf-proxy-class-and-application-configuration-file"></a><span data-ttu-id="3fb4a-110">Para crear una clase de proxy de WCF simple y un archivo de configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="3fb4a-110">To create a simple WCF proxy class and application configuration file</span></span>  
  
1.  <span data-ttu-id="3fb4a-111">Abra el Shell CMD como sigue: haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft Windows SDK**y, a continuación, haga clic en **Shell de CMD**.</span><span class="sxs-lookup"><span data-stu-id="3fb4a-111">Open CMD Shell as follows: click **Start**, point to **All Programs**, point to **Microsoft Windows SDK**, and then click **CMD Shell**.</span></span>  
  
2.  <span data-ttu-id="3fb4a-112">En el shell de CMD, obtenga acceso al directorio en el que desee colocar la clase de proxy y el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3fb4a-112">In CMD Shell, go to the directory where you want to place the proxy class and application configuration file.</span></span>  
  
3.  <span data-ttu-id="3fb4a-113">En el shell de CMD, ejecute la herramienta de utilidad de metadatos del modelo de servicio (SvcUtil.exe) para crear la clase de proxy de WCF y el archivo de configuración de la aplicación para el Servicio WCF publicado como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="3fb4a-113">In CMD Shell, run the ServiceModel Metadata Utility Tool (SvcUtil.exe) to create the WCF proxy class and application configuration file for the published WCF service as follows:</span></span>  
  
    ```  
    svcutil <http://servername/apppath/wcfservicename.svc> /config:App.config  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="3fb4a-114">Esta línea de comandos genera BizTalkServiceInstance.cs para la clase de proxy y App.config para el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3fb4a-114">This command line generates BizTalkServiceInstance.cs for the proxy class and App.config for the application configuration.</span></span> <span data-ttu-id="3fb4a-115">Para obtener más información acerca de Svcutil.exe, vea "Service Model Metadata utilidad Tool (Svcutil.exe)" en [ http://go.microsoft.com/fwlink/?LinkId=74696 ](http://go.microsoft.com/fwlink/?LinkId=74696).</span><span class="sxs-lookup"><span data-stu-id="3fb4a-115">For more information about Svcutil.exe, see "Service Model Metadata Utility Tool (Svcutil.exe)" at [http://go.microsoft.com/fwlink/?LinkId=74696](http://go.microsoft.com/fwlink/?LinkId=74696).</span></span>  
  
### <a name="to-compile-your-net-application-that-consumes-the-published-wcf-service"></a><span data-ttu-id="3fb4a-116">Para compilar la aplicación .NET que consume el Servicio WCF publicado</span><span class="sxs-lookup"><span data-stu-id="3fb4a-116">To compile your .NET application that consumes the published WCF service</span></span>  
  
1. <span data-ttu-id="3fb4a-117">En el Explorador de soluciones de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], agregue los archivos que crea SvcUtil.exe, BizTalkServiceInstance y App.config al proyecto.</span><span class="sxs-lookup"><span data-stu-id="3fb4a-117">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, add the files that SvcUtil.exe creates, BizTalkServiceInstance and App.config, to your project.</span></span>  
  
2. <span data-ttu-id="3fb4a-118">En el Explorador de soluciones de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], asegúrese de que agrega una referencia a System.ServiceModel.dll para compilar el código de proxy.</span><span class="sxs-lookup"><span data-stu-id="3fb4a-118">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, make sure to add a reference to the System.ServiceModel.dll to compile the proxy code.</span></span>  
  
3. <span data-ttu-id="3fb4a-119">Cree el código para usar el código de proxy generado.</span><span class="sxs-lookup"><span data-stu-id="3fb4a-119">Create the code to use the generated proxy code.</span></span> <span data-ttu-id="3fb4a-120">El siguiente código muestra cómo usar el proxy generado:</span><span class="sxs-lookup"><span data-stu-id="3fb4a-120">The following code shows how to use the generated proxy:</span></span>  
  
   ```  
   DeliveryNotification deliveryNotification= new DeliveryNotification();  
   deliveryNotification.TrackingNumber = "001";  
               Microsoft_Samples_BizTalk_WCFBasicHttp_BizTalkApp_DliveryRequestProcess_DeliveryNotificatonReceivePortClient service = new Microsoft_Samples_BizTalk_WCFBasicHttp_BizTalkApp_DliveryRequestProcess_DeliveryNotificatonReceivePortClient("BasicHttpBinding_ITwoWayAsyncVoid");  
   service.Submit(deliveryNotification);  
   ```  
  
4. <span data-ttu-id="3fb4a-121">Ejecute la aplicación .NET para enviar mensajes al Servicio WCF publicado.</span><span class="sxs-lookup"><span data-stu-id="3fb4a-121">Run your .NET application to send messages to the published WCF service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fb4a-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="3fb4a-122">See Also</span></span>  
 [<span data-ttu-id="3fb4a-123">Consideraciones al publicar servicios WCF con los adaptadores de recepción WCF</span><span class="sxs-lookup"><span data-stu-id="3fb4a-123">Considerations When Publishing WCF Services with the WCF Receive Adapters</span></span>](../core/considerations-when-publishing-wcf-services-with-the-wcf-receive-adapters.md)