---
title: Crear y configurar la solución de Fabrikam | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, creating solutions
- double action tutorial, configuring solutions
ms.assetid: 463d55ef-12b6-49e1-a1b8-9081cfb0abed
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 923e5fb3ba8e50f87538c77b354434cac952d9d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209972"
---
# <a name="creating-and-configuring-the-fabrikam-solution"></a><span data-ttu-id="cd85d-102">Crear y configurar la solución de Fabrikam</span><span class="sxs-lookup"><span data-stu-id="cd85d-102">Creating and Configuring the Fabrikam Solution</span></span>
<span data-ttu-id="cd85d-103">En esta sección del tutorial se detalla los pasos que debe seguir para la organización de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="cd85d-103">This section of the tutorial details the steps that you have to follow for the Fabrikam organization.</span></span> <span data-ttu-id="cd85d-104">La organización de Fabrikam representa el comprador y, por tanto, actúa como iniciador para todas las solicitudes de proceso de interfaz de socio (PIP).</span><span class="sxs-lookup"><span data-stu-id="cd85d-104">The Fabrikam organization represents the buyer and therefore acts as the initiator for all Partner Interface Process (PIP) requests.</span></span> <span data-ttu-id="cd85d-105">En este tutorial, crear acuerdos para cuatro PIP de socios comerciales y compilar e implementar un línea de negocio (LOB) ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] aplicación para enviar una solicitud al equipo de Contoso se basa en un determinado tipo PIP.</span><span class="sxs-lookup"><span data-stu-id="cd85d-105">In this tutorial, you create partner agreements for four PIPs, and build and deploy a line-of-business (LOB) ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] application to send a request to the Contoso computer based on a certain PIP type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cd85d-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="cd85d-106">In This Section</span></span>  
  
-   [<span data-ttu-id="cd85d-107">Paso 1: Crear la organización principal de Fabrikam</span><span class="sxs-lookup"><span data-stu-id="cd85d-107">Step 1: Creating the Fabrikam Home Organization</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-1-creating-the-fabrikam-home-organization.md)  
  
-   [<span data-ttu-id="cd85d-108">Paso 2: Crear la organización del asociado de Contoso</span><span class="sxs-lookup"><span data-stu-id="cd85d-108">Step 2: Creating the Contoso Partner Organization</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-the-contoso-partner-organization.md)  
  
-   [<span data-ttu-id="cd85d-109">Paso 3: Crear el acuerdo de socio comercial Fabrikam 0c comerciales 2</span><span class="sxs-lookup"><span data-stu-id="cd85d-109">Step 3: Creating the Fabrikam 0C2 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-creating-the-fabrikam-0c2-trading-partner-agreement.md)  
  
-   [<span data-ttu-id="cd85d-110">Paso 4: Crear el acuerdo de socios comerciales 4 de Fabrikam 0c</span><span class="sxs-lookup"><span data-stu-id="cd85d-110">Step 4: Creating the Fabrikam 0C4 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-creating-the-fabrikam-0c4-trading-partner-agreement.md)  
  
-   [<span data-ttu-id="cd85d-111">Paso 5: Crear el acuerdo de socio comercial Fabrikam 3A2</span><span class="sxs-lookup"><span data-stu-id="cd85d-111">Step 5: Creating the Fabrikam 3A2 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-5-creating-the-fabrikam-3a2-trading-partner-agreement.md)  
  
-   [<span data-ttu-id="cd85d-112">Paso 6: Crear el acuerdo de socio comercial Fabrikam 3A4</span><span class="sxs-lookup"><span data-stu-id="cd85d-112">Step 6: Creating the Fabrikam 3A4 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-6-creating-the-fabrikam-3a4-trading-partner-agreement.md)  
  
-   [<span data-ttu-id="cd85d-113">Paso 7: Crear e implementar el ejemplo de SDK de LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="cd85d-113">Step 7: Building and Deploying the LOBWebApplication SDK Sample</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-7-building-and-deploying-the-lobwebapplication-sdk-sample.md)