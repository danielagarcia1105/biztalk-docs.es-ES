---
title: Tutorial de doble acción | Microsoft Docs
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
ms.openlocfilehash: 220f853788462d3c9b53b8fb043c65ac54872fd0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973981"
---
# <a name="double-action-tutorial"></a><span data-ttu-id="3bce2-102">Tutorial de doble acción</span><span class="sxs-lookup"><span data-stu-id="3bce2-102">Double Action Tutorial</span></span>
<span data-ttu-id="3bce2-103">Este tutorial describe una solución de extremo a otro mediante Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3bce2-103">This tutorial covers an end-to-end solution using Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span> <span data-ttu-id="3bce2-104">El tutorial detalla los pasos que se deben seguir para implementar una solución compatible con RosettaNet mediante la creación de un escenario de socio comercial entre dos empresas ficticias: Contoso, la organización del proveedor y Fabrikam, la organización del comprador.</span><span class="sxs-lookup"><span data-stu-id="3bce2-104">The tutorial details the steps that you have to follow to implement a RosettaNet-compliant solution by creating a trading partner scenario between two fictitious companies: Contoso, the supplier organization, and Fabrikam, the buyer organization.</span></span>  
  
 <span data-ttu-id="3bce2-105">Este tutorial utiliza cuatro procesos de interfaz de socio (PIP) diferentes:</span><span class="sxs-lookup"><span data-stu-id="3bce2-105">This tutorial uses four different Partner Interface Processes (PIPs):</span></span>  
  
- <span data-ttu-id="3bce2-106">0c2 - solicitud asincrónica de prueba</span><span class="sxs-lookup"><span data-stu-id="3bce2-106">0C2 - Asynchronous Test Request</span></span>  
  
- <span data-ttu-id="3bce2-107">0c4: consulta sincrónica de prueba</span><span class="sxs-lookup"><span data-stu-id="3bce2-107">0C4 - Synchronous Test Query</span></span>  
  
- <span data-ttu-id="3bce2-108">3A2: solicitud de precio y disponibilidad</span><span class="sxs-lookup"><span data-stu-id="3bce2-108">3A2 - Request Price and Availability</span></span>  
  
- <span data-ttu-id="3bce2-109">3A4: solicitud de pedido de compra</span><span class="sxs-lookup"><span data-stu-id="3bce2-109">3A4 - Request Purchase Order</span></span>  
  
  <span data-ttu-id="3bce2-110">Este tutorial trata varias áreas de una solución basada en RosettaNet, incluido el trabajo con el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] consola de administración, creación de aplicaciones de línea de negocio (LOB) y la creación de orquestaciones personalizadas que puede usar para integrar Sistemas de planeación de recursos empresariales (ERP).</span><span class="sxs-lookup"><span data-stu-id="3bce2-110">This tutorial addresses several distinct areas of a RosettaNet-based solution, including working with the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console, creating line-of-business (LOB) applications, and creating custom orchestrations that you can use to integrate Enterprise Resource Planning (ERP) systems.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3bce2-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3bce2-111">In This Section</span></span>  
  
-   [<span data-ttu-id="3bce2-112">Preparación para el tutorial de doble acción</span><span class="sxs-lookup"><span data-stu-id="3bce2-112">Preparing for the Double Action Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/preparing-for-the-double-action-tutorial.md)  
  
-   [<span data-ttu-id="3bce2-113">Creación y configuración de la solución de Contoso</span><span class="sxs-lookup"><span data-stu-id="3bce2-113">Creating and Configuring the Contoso Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-the-contoso-solution.md)  
  
-   [<span data-ttu-id="3bce2-114">Creación y configuración de la solución de Fabrikam</span><span class="sxs-lookup"><span data-stu-id="3bce2-114">Creating and Configuring the Fabrikam Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-the-fabrikam-solution.md)  
  
-   [<span data-ttu-id="3bce2-115">Prueba del tutorial de doble acción</span><span class="sxs-lookup"><span data-stu-id="3bce2-115">Testing the Double Action Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/testing-the-double-action-tutorial.md)