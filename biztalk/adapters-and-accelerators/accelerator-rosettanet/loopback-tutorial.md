---
title: Tutorial de bucle invertido | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- loopbacks, tutorial
- loopback tutorial, about the loopback tutorial
- loopback tutorial
- tutorials, loopback tutorial
ms.assetid: 0f69c1f1-4039-4949-8eed-127ceabbc3cc
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3b013eb65320dc36dd1319d7332e45ed54b2444
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="loopback-tutorial"></a><span data-ttu-id="72c21-102">Tutorial de bucle invertido</span><span class="sxs-lookup"><span data-stu-id="72c21-102">Loopback Tutorial</span></span>
<span data-ttu-id="72c21-103">Este tutorial contiene los pasos detallados que describen cómo se puede usar [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] para simular una implementación de procesos entre la organización principal y de los asociados en un único equipo.</span><span class="sxs-lookup"><span data-stu-id="72c21-103">This tutorial contains detailed steps that describe how you can use [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] to simulate a process implementation between the home and partner organization on a single computer.</span></span>  
  
 <span data-ttu-id="72c21-104">En un entorno de producción real, la implementación de la organización de socios comerciales reside en un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="72c21-104">In a real production environment, your partner organization implementation resides on a remote computer.</span></span> <span data-ttu-id="72c21-105">Este tutorial usa la utilidad de bucle invertido para crear un espejo de acuerdo para simular al socio comercial en el mismo equipo comercial.</span><span class="sxs-lookup"><span data-stu-id="72c21-105">This tutorial uses the Loopback utility to create a mirror trading agreement to simulate the trading partner on the same computer.</span></span> <span data-ttu-id="72c21-106">El uso de un escenario de bucle invertido único equipo funciona con fines de desarrollo y prueba.</span><span class="sxs-lookup"><span data-stu-id="72c21-106">Using a single computer loop-back scenario works for development and test purposes.</span></span> <span data-ttu-id="72c21-107">Se recomienda que realice para que no utilice la utilidad de bucle invertido en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="72c21-107">It is recommended that you do not to use the Loopback utility in a production environment.</span></span>  
  
 <span data-ttu-id="72c21-108">Este escenario de bucle invertido no es compatible con la firma de mensajes y, por tanto, no admite sin repudio.</span><span class="sxs-lookup"><span data-stu-id="72c21-108">This loopback scenario does not support signing messages, and thus does not support non-repudiation.</span></span>  
  
 <span data-ttu-id="72c21-109">Este escenario admite el cifrado de mensajes si tiene una entidad de certificación configurada y tiene una clave privada para el cifrado disponible para fines de prueba.</span><span class="sxs-lookup"><span data-stu-id="72c21-109">This scenario supports encryption of messages if you have a certification authority configured, and you have a private key for encryption available for test purposes.</span></span>  
  
 <span data-ttu-id="72c21-110">En este tutorial, crear una organización principal, una organización asociada, un acuerdo comercial, use la utilidad de bucle invertido para crear un acuerdo reflejado y, a continuación, ejecutar un proceso de ejemplo para comprobar el escenario de bucle invertido.</span><span class="sxs-lookup"><span data-stu-id="72c21-110">In this tutorial, you create a home organization, a partner organization, a trade agreement, use the Loopback utility to create a mirror agreement, and then run a sample process to verify the loop-back scenario.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="72c21-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="72c21-111">In This Section</span></span>  
  
-   [<span data-ttu-id="72c21-112">Preparar el Tutorial</span><span class="sxs-lookup"><span data-stu-id="72c21-112">Preparing for the Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/preparing-for-the-tutorial.md)  
  
-   [<span data-ttu-id="72c21-113">Paso 1: Crear la organización principal</span><span class="sxs-lookup"><span data-stu-id="72c21-113">Step 1: Create the Home Organization</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-1-create-the-home-organization.md)  
  
-   [<span data-ttu-id="72c21-114">Paso 2: Crear la organización del asociado</span><span class="sxs-lookup"><span data-stu-id="72c21-114">Step 2: Create the Partner Organization</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-create-the-partner-organization.md)  
  
-   [<span data-ttu-id="72c21-115">Paso 3: Modificar el proceso de la interfaz de socio comercial</span><span class="sxs-lookup"><span data-stu-id="72c21-115">Step 3: Edit the Partner Interface Process</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-edit-the-partner-interface-process.md)  
  
-   [<span data-ttu-id="72c21-116">Paso 4: Crear un acuerdo comercial</span><span class="sxs-lookup"><span data-stu-id="72c21-116">Step 4: Create a Trade Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-create-a-trade-agreement.md)  
  
-   [<span data-ttu-id="72c21-117">Paso 5: Crear un acuerdo de reflejo</span><span class="sxs-lookup"><span data-stu-id="72c21-117">Step 5: Create a Mirror Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-5-create-a-mirror-agreement.md)  
  
-   [<span data-ttu-id="72c21-118">Paso 6: Iniciar orquestaciones</span><span class="sxs-lookup"><span data-stu-id="72c21-118">Step 6: Start Orchestrations</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-6-start-orchestrations.md)  
  
-   [<span data-ttu-id="72c21-119">Paso 7: Crear un mensaje de LOB de ejemplo</span><span class="sxs-lookup"><span data-stu-id="72c21-119">Step 7: Create a Sample LOB Message</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-7-create-a-sample-lob-message.md)  
  
-   [<span data-ttu-id="72c21-120">Paso 8: Ver los mensajes en las bases de datos BTARN</span><span class="sxs-lookup"><span data-stu-id="72c21-120">Step 8: View Messages in the BTARN Databases</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-8-view-messages-in-the-btarn-databases.md)