---
title: 'Tutorial 1: Presentar datos desde un sistema Siebel en un sitio de SharePoint | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9dd06f75-75d1-4fad-8f34-51c97c7790e3
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7f31de42694cfa81a800d63f1c1d77ffff0bbaa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site"></a><span data-ttu-id="09092-102">Tutorial 1: Presentar datos desde un sistema Siebel en un sitio de SharePoint</span><span class="sxs-lookup"><span data-stu-id="09092-102">Tutorial 1: Presenting Data From a Siebel System on a SharePoint Site</span></span>
<span data-ttu-id="09092-103">Este tutorial proporciona instrucciones detalladas sobre cómo utilizar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] con Microsoft Office SharePoint Server para presentar datos de negocio de un sistema Siebel en un portal de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="09092-103">This tutorial provides detailed instructions on using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] with Microsoft Office SharePoint Server to present business data from a Siebel system on a SharePoint portal.</span></span> <span data-ttu-id="09092-104">Para demostrar cómo usar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] con Office SharePoint Server, crearemos una aplicación de Office SharePoint Server para recuperar una lista de cuentas de cliente desde el repositorio de Siebel mediante el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09092-104">To demonstrate how to use the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] with Office SharePoint Server, we create an application in Office SharePoint Server to retrieve a list of customer accounts from the Siebel repository using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
 <span data-ttu-id="09092-105">Para extraer esta información en el sistema Siebel, el ejemplo invoca el método de consulta en el **cuenta** componentes empresariales.</span><span class="sxs-lookup"><span data-stu-id="09092-105">To extract this information from the Siebel system, the example invokes the Query method on the **Account** business components.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09092-106">Antes de continuar con el tutorial, asegúrese de que ha instalado todos los requisitos previos para usar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] con Office SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="09092-106">Before proceeding with the tutorial, make sure you have installed all the prerequisites for using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] with Office SharePoint Server.</span></span> <span data-ttu-id="09092-107">Para obtener más información sobre los requisitos previos, consulte la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] Guía de instalación, normalmente se instalan al \<unidad de instalación >: \Program [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.</span><span class="sxs-lookup"><span data-stu-id="09092-107">For more information about the prerequisites, see the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation guide, typically installed at \<installation drive>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="09092-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="09092-108">In This Section</span></span>  
  
-   [<span data-ttu-id="09092-109">Paso 1: Publicar las operaciones de componente de negocios de Siebel como un servicio WCF</span><span class="sxs-lookup"><span data-stu-id="09092-109">Step 1: Publish the Siebel Business Component Operations as a WCF Service</span></span>](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md)  
  
-   [<span data-ttu-id="09092-110">Paso 2: Crear un archivo de definición de aplicación para operaciones de componente de negocio de Siebel</span><span class="sxs-lookup"><span data-stu-id="09092-110">Step 2: Create an Application Definition File for Siebel Business Component Operations</span></span>](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md)  
  
-   [<span data-ttu-id="09092-111">Paso 3: Crear una aplicación de SharePoint para recuperar datos de Siebel</span><span class="sxs-lookup"><span data-stu-id="09092-111">Step 3: Create a SharePoint Application to Retrieve Data from Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md)  
  
-  [<span data-ttu-id="09092-112">Paso 4: Probar la aplicación de SharePoint</span><span class="sxs-lookup"><span data-stu-id="09092-112">Step 4: Test Your SharePoint Application</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/step-4-test-your-sharepoint-application.md)  
  
## <a name="see-also"></a><span data-ttu-id="09092-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="09092-113">See Also</span></span>  
 [<span data-ttu-id="09092-114">Tutoriales del adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="09092-114">Siebel Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-siebel/siebel-adapter-tutorials.md)