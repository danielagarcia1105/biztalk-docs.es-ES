---
title: 'Paso 1: Crear una nueva solución de BizTalk para la solicitud de disponibilidad y el precio de Contoso | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating solutions
ms.assetid: e323ce26-2031-4293-95bd-a3bf02e535a5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee09981b11be8892eefe8d73d526e5712145c9c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-creating-a-new-biztalk-solution-for-the-contoso-price-and-availability-request"></a><span data-ttu-id="80260-102">Paso 1: Crear una nueva solución de BizTalk para la solicitud de disponibilidad y el precio de Contoso</span><span class="sxs-lookup"><span data-stu-id="80260-102">Step 1: Creating a New BizTalk Solution for the Contoso Price and Availability Request</span></span>
<span data-ttu-id="80260-103">En este paso, creará un [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] solución para el proyecto de Contoso Price y solicitudes de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="80260-103">In this step, you create a [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] solution for the Contoso Price and Availability Request project.</span></span> <span data-ttu-id="80260-104">Este proyecto contendrá los esquemas y asignaciones para las solicitudes y respuestas para los mensajes de precio y disponibilidad 3A2.</span><span class="sxs-lookup"><span data-stu-id="80260-104">This project will contain the schemas and maps for the requests and responses for the 3A2 Price and Availability messages.</span></span>  
  
### <a name="to-create-a-blank-solution"></a><span data-ttu-id="80260-105">Para crear una solución en blanco</span><span class="sxs-lookup"><span data-stu-id="80260-105">To create a blank solution</span></span>  
  
1.  <span data-ttu-id="80260-106">Inicie **Microsoft Visual Studio 2012**.</span><span class="sxs-lookup"><span data-stu-id="80260-106">Start **Microsoft Visual Studio 2012**.</span></span>  
  
2.  <span data-ttu-id="80260-107">En el menú **Archivo** , seleccione **Nuevo**y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="80260-107">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="80260-108">En el cuadro de diálogo Nuevo proyecto, en la sección **Tipos de proyecto** , expanda **Otros tipos de proyecto**, seleccione **Soluciones de Visual Studio**y, a continuación, en la sección **Plantillas** , seleccione **Solución en blanco**.</span><span class="sxs-lookup"><span data-stu-id="80260-108">In the New Project dialog box, in the **Project Types** section, expand **Other Project Types**, select **Visual Studio Solutions**, and then in the **Templates** section, select **Blank Solution**.</span></span>  
  
4.  <span data-ttu-id="80260-109">En el cuadro **Nombre** , escriba **Contoso** como nombre de la solución y, a continuación, haga clic en **Aceptar** para abrir la nueva solución.</span><span class="sxs-lookup"><span data-stu-id="80260-109">In the **Name** box, type **Contoso** as the solution name, and then click **OK** to open the new solution.</span></span>  
  
### <a name="to-create-the-price-and-availability-project"></a><span data-ttu-id="80260-110">Para crear el proyecto de precio y disponibilidad</span><span class="sxs-lookup"><span data-stu-id="80260-110">To create the Price and Availability project</span></span>  
  
1.  <span data-ttu-id="80260-111">En Visual Studio, en el menú **Archivo** , seleccione **Nuevo**y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="80260-111">In Visual Studio, on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="80260-112">En el cuadro de diálogo Nuevo proyecto, en la sección **Tipos de proyecto** , seleccione **Proyectos de BizTalk**y, a continuación, en la sección **Plantillas** , seleccione **Proyecto vacío de servidor BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="80260-112">In the New Project dialog box, in the **Project Types** section, select **BizTalk Projects**, and then in the **Templates** section, select **Empty BizTalk Server Project**.</span></span>  
  
3.  <span data-ttu-id="80260-113">En el cuadro **Nombre** , escriba **ContosoPriceAndAvailability** como el nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="80260-113">In the **Name** box, type **ContosoPriceAndAvailability** as the project name.</span></span> <span data-ttu-id="80260-114">Para **Solución**, seleccione **Agregar a solución**.</span><span class="sxs-lookup"><span data-stu-id="80260-114">For **Solution**, select **Add to Solution**.</span></span> <span data-ttu-id="80260-115">Haga clic en **Aceptar** para abrir el nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="80260-115">Click **OK** to open the new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80260-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="80260-116">See Also</span></span>  
 [<span data-ttu-id="80260-117">Paso 2: Crear los esquemas de aplicación de LOB de Contoso para el precio y el proyecto de disponibilidad mediante el Editor de BizTalk</span><span class="sxs-lookup"><span data-stu-id="80260-117">Step 2: Creating the Contoso LOB Application Schemas for the Price and Availability Project Using BizTalk Editor</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-create-contoso-lob-application-schema-for-price-and-availability.md)