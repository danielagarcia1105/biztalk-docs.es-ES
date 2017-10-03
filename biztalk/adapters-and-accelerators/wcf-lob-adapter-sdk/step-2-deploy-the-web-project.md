---
title: 'Paso 2: Implementar el proyecto Web | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cb775a89-2e2d-43e5-94ae-f75c1756dbd7
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 503ce37fd06f91d5036f08c9eee752017c0ad21c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-deploy-the-web-project"></a><span data-ttu-id="a7e7e-102">Paso 2: Implementar el proyecto Web</span><span class="sxs-lookup"><span data-stu-id="a7e7e-102">Step 2: Deploy the Web Project</span></span>
<span data-ttu-id="a7e7e-103">![Paso 2 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span><span class="sxs-lookup"><span data-stu-id="a7e7e-103">![Step 2 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span></span>  
  
 <span data-ttu-id="a7e7e-104">**Tiempo en completarse:** 5 minutos</span><span class="sxs-lookup"><span data-stu-id="a7e7e-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="a7e7e-105">En este paso se publicará el proyecto Web generado en [paso 1: usar el Asistente para desarrollo de servicio de adaptador para crear el proyecto Web](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md) para Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="a7e7e-105">In this step you will publish the Web project generated in [Step 1: Use the Adapter Service Development Wizard to Create the Web Project](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md) to Internet Information Services (IIS).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a7e7e-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a7e7e-106">Prerequisites</span></span>  
 <span data-ttu-id="a7e7e-107">Para completar este paso, debe haber completado [paso 1: usar el Asistente para desarrollo de servicio de adaptador para crear el proyecto Web](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md).</span><span class="sxs-lookup"><span data-stu-id="a7e7e-107">To complete this step, you should have completed [Step 1: Use the Adapter Service Development Wizard to Create the Web Project](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md).</span></span> <span data-ttu-id="a7e7e-108">El servidor Web también debe tener un certificado SSL instalado para habilitar la comunicación HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a7e7e-108">Your Web server must also have an SSL certificate installed to enable HTTPS communication.</span></span>  
  
### <a name="to-compile-and-deploy-the-web-project"></a><span data-ttu-id="a7e7e-109">Para compilar e implementar el proyecto Web</span><span class="sxs-lookup"><span data-stu-id="a7e7e-109">To compile and deploy the Web project</span></span>  
  
1.  <span data-ttu-id="a7e7e-110">En [!INCLUDE[vs2010](../../includes/vs2010-md.md)], cargar el proyecto EchoWeb que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a7e7e-110">In [!INCLUDE[vs2010](../../includes/vs2010-md.md)], load the EchoWeb project created previously.</span></span>  
  
2.  <span data-ttu-id="a7e7e-111">Abra un [!INCLUDE[vs2010](../../includes/vs2010-md.md)] símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="a7e7e-111">Open a [!INCLUDE[vs2010](../../includes/vs2010-md.md)] command prompt.</span></span>  
  
3.  <span data-ttu-id="a7e7e-112">En el símbolo del sistema, desde la carpeta C:\tutorials\echoweb, escriba el siguiente comando y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="a7e7e-112">At the command prompt, from the C:\tutorials\echoweb folder, type the following command, and then press ENTER:</span></span>  
  
     <span data-ttu-id="a7e7e-113">**sn /k EchoWebKey.snk**</span><span class="sxs-lookup"><span data-stu-id="a7e7e-113">**sn /k EchoWebKey.snk**</span></span>  
  
     <span data-ttu-id="a7e7e-114">Un mensaje de confirmación, **clave par escrito en EchoWebKey.snk**, se muestra en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="a7e7e-114">A confirmation message, **Key pair written to EchoWebKey.snk**, displays on the command line.</span></span>  
  
4.  <span data-ttu-id="a7e7e-115">Cierre el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="a7e7e-115">Close the command prompt.</span></span>  
  
5.  <span data-ttu-id="a7e7e-116">En **el Explorador de soluciones**, haga clic en el proyecto de EchoWeb y, a continuación, seleccione **Publicar sitio Web**.</span><span class="sxs-lookup"><span data-stu-id="a7e7e-116">In **Solution Explorer**, right click the EchoWeb project, and then select **Publish Web Site**.</span></span>  
  
6.  <span data-ttu-id="a7e7e-117">En el **Publicar sitio Web** cuadro de diálogo para **ubicación de destino**, escriba **http://machinename/EchoWeb**.</span><span class="sxs-lookup"><span data-stu-id="a7e7e-117">In the **Publish Web Site** dialog box, for **Target location**, enter **http://machinename/EchoWeb**.</span></span> <span data-ttu-id="a7e7e-118">Seleccione **permitir que este sitio precompilado se actualizables**, **uso corregido únicos y nomenclatura de ensamblados de página**, y **habilitar nombres seguros en los ensamblados precompilan**.</span><span class="sxs-lookup"><span data-stu-id="a7e7e-118">Select **Allow this precompiled site to be updatable**, **Use fixed naming and single page assemblies**, and **Enable strong naming on precompiled assemblies**.</span></span> <span data-ttu-id="a7e7e-119">En el **ubicación del archivo de clave** , a continuación, haga clic en los puntos suspensivos **(...)**  botón, seleccione el archivo EchoWebKey.snk creado anteriormente y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a7e7e-119">In the **Key file location** field, click the ellipsis **(…)** button, select the EchoWebKey.snk file created previously, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="a7e7e-120">Para comprobar que el sitio Web se ha creado correctamente, inicie Internet Explorer, escriba **HYPERLINK "http://localhost/EchoWeb/EchoOutboundContract.svc" http://localhost/EchoWeb/EchoOutboundContract.svc** en la barra de direcciones, y a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="a7e7e-120">To verify that the Web site was correctly created, start Internet Explorer, enter  **HYPERLINK "http://localhost/EchoWeb/EchoOutboundContract.svc" http://localhost/EchoWeb/EchoOutboundContract.svc** in the address bar, and then press ENTER.</span></span> <span data-ttu-id="a7e7e-121">Debe aparecer una página Web que describe la EchoOutboundContractClient.</span><span class="sxs-lookup"><span data-stu-id="a7e7e-121">A Web page that describes the EchoOutboundContractClient should appear.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="a7e7e-122">Síntesis</span><span class="sxs-lookup"><span data-stu-id="a7e7e-122">What did I just do?</span></span>  
 <span data-ttu-id="a7e7e-123">Acaba de publicar el proyecto Web en IIS.</span><span class="sxs-lookup"><span data-stu-id="a7e7e-123">You have just published your Web project to IIS.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a7e7e-124">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a7e7e-124">Next Steps</span></span>  
 <span data-ttu-id="a7e7e-125">Ahora que ha compilado e implementado el proyecto, puede continuar con [paso 3: crear un archivo de definición de aplicación](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md)</span><span class="sxs-lookup"><span data-stu-id="a7e7e-125">Now that you have compiled and deployed the project, you can proceed to [Step 3: Create an Application Definition File](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7e7e-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7e7e-126">See Also</span></span>  
 [<span data-ttu-id="a7e7e-127">Tutorial 3: Aloja el adaptador de eco en IIS</span><span class="sxs-lookup"><span data-stu-id="a7e7e-127">Tutorial 3: Hosting the Echo Adapter in IIS</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)