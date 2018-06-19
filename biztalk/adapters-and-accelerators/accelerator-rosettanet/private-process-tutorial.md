---
title: Tutorial de procesos privados | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private processes, tutorial
- private process tutorial
- tutorials, private process tutorial
ms.assetid: 58affc48-af73-406e-895f-696bc284d945
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c017d8b9b52c1f477aba62308ca2e65a1550564
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209924"
---
# <a name="private-process-tutorial"></a><span data-ttu-id="7547d-102">Tutorial de procesos privado</span><span class="sxs-lookup"><span data-stu-id="7547d-102">Private Process Tutorial</span></span>
<span data-ttu-id="7547d-103">Este tutorial contiene una completa solución de extremo a extremo mediante [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7547d-103">This tutorial contains a complete end-to-end solution using [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span> <span data-ttu-id="7547d-104">El tutorial detalla los pasos que se deben seguir para implementar una solución compatible con RosettaNet mediante la creación de un escenario comercial entre dos empresas ficticias: la organización del proveedor, Contoso y Fabrikam, la organización del comprador.</span><span class="sxs-lookup"><span data-stu-id="7547d-104">The tutorial details the steps that you have to follow to implement a RosettaNet-compliant solution by creating a trading scenario between two fictitious companies: Contoso, the supplier organization, and Fabrikam, the buyer organization.</span></span>  
  
 <span data-ttu-id="7547d-105">El escenario que implementa este tutorial usa el precio de 3A2 y el proceso de interfaz de socio (PIP) de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="7547d-105">The scenario this tutorial implements uses the 3A2-Price and Availability Partner Interface Process (PIP).</span></span> <span data-ttu-id="7547d-106">Antes de una compra, el comprador, Fabrikam, envía un 3A2 precio y disponibilidad de solicitud al proveedor, Contoso.</span><span class="sxs-lookup"><span data-stu-id="7547d-106">Before a purchase, the buyer, Fabrikam, sends a 3A2-Price and Availability Request to the supplier, Contoso.</span></span> <span data-ttu-id="7547d-107">Este PIP permite Fabrikam obtener información sobre un determinado producto que, a continuación, puede procesar a través de las reglas de negocios para tomar una decisión sobre si se debe adquirir el producto.</span><span class="sxs-lookup"><span data-stu-id="7547d-107">This PIP enables Fabrikam to obtain information about a certain product that they can then process through business rules to make a determination about whether to purchase the product.</span></span> <span data-ttu-id="7547d-108">La siguiente ilustración muestra el patrón de comunicación entre las organizaciones de iniciador y el contestador durante un intercambio PIP 3A2.</span><span class="sxs-lookup"><span data-stu-id="7547d-108">The following figure shows the communication pattern between the initiator and responder organizations during a 3A2 PIP exchange.</span></span>  
  
 <span data-ttu-id="7547d-109">![&#60; No hay ningún cambio &#62; ] (../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-intro-eetut-3a2flow.gif "RN3_Intro_EETut_3A2Flow")</span><span class="sxs-lookup"><span data-stu-id="7547d-109">![&#60;No Change&#62;](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-intro-eetut-3a2flow.gif "RN3_Intro_EETut_3A2Flow")</span></span>  
  
 <span data-ttu-id="7547d-110">El objetivo de este tutorial está en la solución de Contoso.</span><span class="sxs-lookup"><span data-stu-id="7547d-110">The focus of this tutorial is on the Contoso solution.</span></span> <span data-ttu-id="7547d-111">Se describen los distintos aspectos de crear una solución basada en RosettaNet, incluidas la integración de ERP, la aplicación de directivas empresariales, personalización de procesos privados y fomentar una comunicación segura.</span><span class="sxs-lookup"><span data-stu-id="7547d-111">It outlines various aspects of creating a RosettaNet-based solution, including ERP integration, business policy enforcement, private process customization, and promoting secure communication.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7547d-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7547d-112">In This Section</span></span>  
  
-   [<span data-ttu-id="7547d-113">Preparar el Tutorial de procesos privado</span><span class="sxs-lookup"><span data-stu-id="7547d-113">Preparing for the Private Process Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/preparing-for-the-private-process-tutorial.md)  
  
-   [<span data-ttu-id="7547d-114">Creación de la solución de Contoso</span><span class="sxs-lookup"><span data-stu-id="7547d-114">Creating the Contoso Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-contoso-solution.md)  
  
-   [<span data-ttu-id="7547d-115">Creación de la solución de Fabrikam</span><span class="sxs-lookup"><span data-stu-id="7547d-115">Creating the Fabrikam Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-fabrikam-solution.md)  
  
-   [<span data-ttu-id="7547d-116">Probar la solución</span><span class="sxs-lookup"><span data-stu-id="7547d-116">Testing the Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/testing-the-solution.md)