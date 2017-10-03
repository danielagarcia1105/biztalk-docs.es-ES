---
title: 'Tutorial 3: Aloja el adaptador de eco en IIS | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3044cdea-e9b2-4cc2-b66e-799da1dfc07e
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74addb5a69e8f17319a7019167eac1415a3a88d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-3-hosting-the-echo-adapter-in-iis"></a><span data-ttu-id="7f336-102">Tutorial 3: Aloja el adaptador de eco en IIS</span><span class="sxs-lookup"><span data-stu-id="7f336-102">Tutorial 3: Hosting the Echo Adapter in IIS</span></span>
<span data-ttu-id="7f336-103">Este tutorial proporciona instrucciones paso a paso para hospedar el adaptador de eco desarrollado en [Tutorial 1: desarrollar el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="7f336-103">This tutorial provides step-by-step instructions for hosting the Echo Adapter developed in [Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md).</span></span> <span data-ttu-id="7f336-104">Más específicamente, los pasos explica cómo puede hospedar el adaptador en Internet Information Services (IIS) mediante el [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f336-104">More specifically, the steps show how you can host the adapter in Internet Information Services (IIS) by using the [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)].</span></span> <span data-ttu-id="7f336-105">Se usan también la característica de catálogo de datos profesionales en SharePoint para llamar a la operación de EchoGreetings del adaptador hospedado en IIS y, a continuación, mostrar los resultados en un elemento Web.</span><span class="sxs-lookup"><span data-stu-id="7f336-105">You will also use the Business Data Catalog feature in SharePoint to call the EchoGreetings operation of the IIS-hosted adapter, and then display the results in a Web Part.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="7f336-106">El adaptador de eco, el código de prueba y el script de instalación se incluyen con los archivos de instalación de BizTalk en `\BizTalk Server\ASDK_x86\Program Files\WCF LOB Adapter SDK\Documents\Samples` o `\BizTalk Server\ASDK_x64\Program Files\WCF LOB Adapter SDK\Documents\Samples`.</span><span class="sxs-lookup"><span data-stu-id="7f336-106">The Echo Adapter, test code, and installation script are included with your BizTalk installation files at `\BizTalk Server\ASDK_x86\Program Files\WCF LOB Adapter SDK\Documents\Samples` or `\BizTalk Server\ASDK_x64\Program Files\WCF LOB Adapter SDK\Documents\Samples`.</span></span> 
  
## <a name="in-this-section"></a><span data-ttu-id="7f336-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7f336-107">In This Section</span></span>  
  
-   [<span data-ttu-id="7f336-108">Paso 1: Utilizar al Asistente para desarrollo de servicio de adaptador para crear el proyecto Web</span><span class="sxs-lookup"><span data-stu-id="7f336-108">Step 1: Use the Adapter Service Development Wizard to Create the Web Project</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md)  
  
-   [<span data-ttu-id="7f336-109">Paso 2: Implementar el proyecto Web</span><span class="sxs-lookup"><span data-stu-id="7f336-109">Step 2: Deploy the Web Project</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-deploy-the-web-project.md)  
  
-   [<span data-ttu-id="7f336-110">Paso 3: Crear un archivo de definición de aplicación</span><span class="sxs-lookup"><span data-stu-id="7f336-110">Step 3: Create an Application Definition File</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md)  
  
-   [<span data-ttu-id="7f336-111">Paso 4: Crear una aplicación de Sharepoint para tener acceso el adaptador</span><span class="sxs-lookup"><span data-stu-id="7f336-111">Step 4: Create a Sharepoint Application to Access the Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-create-a-sharepoint-application-to-access-the-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="7f336-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f336-112">See Also</span></span>  
 <span data-ttu-id="7f336-113">[Tutorial 1: Desarrollar el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="7f336-113">[Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) </span></span>  
  [<span data-ttu-id="7f336-114">Tutoriales del SDK de adaptador de LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="7f336-114">WCF LOB Adapter SDK Tutorials</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorials-to-learn-the-wcf-lob-adapter-sdk.md)