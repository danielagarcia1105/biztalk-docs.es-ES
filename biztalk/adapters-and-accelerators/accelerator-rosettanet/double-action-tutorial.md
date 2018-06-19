---
title: Tutorial de doble acción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tutorials, PIPs
- double action tutorial, about the tutorial
- trading partners, tutorials
- double action tutorial
- tutorials, trading partners
- PIPs, tutorials
- tutorials, double action tutorial
ms.assetid: b692c043-82ef-46f4-8683-7ae1fd6e4421
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5243fb2547f27b113e3096d6c93d233e22aae3e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210124"
---
# <a name="double-action-tutorial"></a><span data-ttu-id="706fb-102">Tutorial de doble acción</span><span class="sxs-lookup"><span data-stu-id="706fb-102">Double Action Tutorial</span></span>
<span data-ttu-id="706fb-103">Este tutorial trata de una solución de extremo a extremo mediante [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span><span class="sxs-lookup"><span data-stu-id="706fb-103">This tutorial covers an end-to-end solution using [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span> <span data-ttu-id="706fb-104">El tutorial detalla los pasos que se deben seguir para implementar una solución compatible con RosettaNet mediante la creación de un escenario de socio comercial entre dos empresas ficticias: la organización del proveedor, Contoso y Fabrikam, la organización del comprador.</span><span class="sxs-lookup"><span data-stu-id="706fb-104">The tutorial details the steps that you have to follow to implement a RosettaNet-compliant solution by creating a trading partner scenario between two fictitious companies: Contoso, the supplier organization, and Fabrikam, the buyer organization.</span></span>  
  
 <span data-ttu-id="706fb-105">Este tutorial utiliza cuatro procesos de interfaz de socio (PIP) diferentes:</span><span class="sxs-lookup"><span data-stu-id="706fb-105">This tutorial uses four different Partner Interface Processes (PIPs):</span></span>  
  
-   <span data-ttu-id="706fb-106">0c2 - solicitud de prueba asincrónica</span><span class="sxs-lookup"><span data-stu-id="706fb-106">0C2 - Asynchronous Test Request</span></span>  
  
-   <span data-ttu-id="706fb-107">0c4: consulta sincrónica de prueba</span><span class="sxs-lookup"><span data-stu-id="706fb-107">0C4 - Synchronous Test Query</span></span>  
  
-   <span data-ttu-id="706fb-108">3A2 - solicitud precio y disponibilidad</span><span class="sxs-lookup"><span data-stu-id="706fb-108">3A2 - Request Price and Availability</span></span>  
  
-   <span data-ttu-id="706fb-109">3A4 - pedido de compra de solicitud</span><span class="sxs-lookup"><span data-stu-id="706fb-109">3A4 - Request Purchase Order</span></span>  
  
 <span data-ttu-id="706fb-110">Este tutorial trata varias áreas distintas de una solución basada en RosettaNet, incluido el trabajo con el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] consola de administración, creación de aplicaciones de línea de negocio (LOB) y la creación de orquestaciones personalizadas que puede usar para integrar Sistemas de planificación de recursos empresariales (ERP).</span><span class="sxs-lookup"><span data-stu-id="706fb-110">This tutorial addresses several distinct areas of a RosettaNet-based solution, including working with the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console, creating line-of-business (LOB) applications, and creating custom orchestrations that you can use to integrate Enterprise Resource Planning (ERP) systems.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="706fb-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="706fb-111">In This Section</span></span>  
  
-   [<span data-ttu-id="706fb-112">Preparar el Tutorial de doble acción</span><span class="sxs-lookup"><span data-stu-id="706fb-112">Preparing for the Double Action Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/preparing-for-the-double-action-tutorial.md)  
  
-   [<span data-ttu-id="706fb-113">Crear y configurar la solución de Contoso</span><span class="sxs-lookup"><span data-stu-id="706fb-113">Creating and Configuring the Contoso Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-the-contoso-solution.md)  
  
-   [<span data-ttu-id="706fb-114">Crear y configurar la solución de Fabrikam</span><span class="sxs-lookup"><span data-stu-id="706fb-114">Creating and Configuring the Fabrikam Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-the-fabrikam-solution.md)  
  
-   [<span data-ttu-id="706fb-115">Probar el Tutorial de doble acción</span><span class="sxs-lookup"><span data-stu-id="706fb-115">Testing the Double Action Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/testing-the-double-action-tutorial.md)