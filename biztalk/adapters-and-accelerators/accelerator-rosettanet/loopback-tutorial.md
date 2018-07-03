---
title: Tutorial de bucle invertido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- loopbacks, tutorial
- loopback tutorial, about the loopback tutorial
- loopback tutorial
- tutorials, loopback tutorial
ms.assetid: 0f69c1f1-4039-4949-8eed-127ceabbc3cc
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97714d5f7e604acbb798739fc4eb545a07968980
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010101"
---
# <a name="loopback-tutorial"></a><span data-ttu-id="d953e-102">Tutorial de bucle invertido</span><span class="sxs-lookup"><span data-stu-id="d953e-102">Loopback Tutorial</span></span>
<span data-ttu-id="d953e-103">Este tutorial contiene los pasos detallados que describen cómo puede usar Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] para simular una implementación de proceso entre la organización principal y socios en un único equipo.</span><span class="sxs-lookup"><span data-stu-id="d953e-103">This tutorial contains detailed steps that describe how you can use Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] to simulate a process implementation between the home and partner organization on a single computer.</span></span>  
  
 <span data-ttu-id="d953e-104">En un entorno de producción real, la implementación de la organización del asociado que reside en un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="d953e-104">In a real production environment, your partner organization implementation resides on a remote computer.</span></span> <span data-ttu-id="d953e-105">Este tutorial usa la utilidad de bucle invertido para crear un espejo de acuerdo para simular al socio comercial en el mismo equipo comercial.</span><span class="sxs-lookup"><span data-stu-id="d953e-105">This tutorial uses the Loopback utility to create a mirror trading agreement to simulate the trading partner on the same computer.</span></span> <span data-ttu-id="d953e-106">Uso de un escenario de bucle invertido de equipo único funciona para fines de desarrollo y pruebas.</span><span class="sxs-lookup"><span data-stu-id="d953e-106">Using a single computer loop-back scenario works for development and test purposes.</span></span> <span data-ttu-id="d953e-107">Se recomienda que no desea para usar la utilidad de bucle invertido en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="d953e-107">It is recommended that you do not to use the Loopback utility in a production environment.</span></span>  
  
 <span data-ttu-id="d953e-108">Este escenario de bucle invertido no es compatible con la firma de mensajes y, por tanto, no admite sin repudio.</span><span class="sxs-lookup"><span data-stu-id="d953e-108">This loopback scenario does not support signing messages, and thus does not support non-repudiation.</span></span>  
  
 <span data-ttu-id="d953e-109">Este escenario admite el cifrado de mensajes si tiene configurada una entidad de certificación, y tiene una clave privada de cifrado disponible para fines de prueba.</span><span class="sxs-lookup"><span data-stu-id="d953e-109">This scenario supports encryption of messages if you have a certification authority configured, and you have a private key for encryption available for test purposes.</span></span>  
  
 <span data-ttu-id="d953e-110">En este tutorial, cree la organización principal, una organización asociada, un acuerdo comercial, use la utilidad de bucle invertido para crear un acuerdo reflejado y, a continuación, ejecute un proceso de ejemplo para comprobar el escenario de bucle invertido.</span><span class="sxs-lookup"><span data-stu-id="d953e-110">In this tutorial, you create a home organization, a partner organization, a trade agreement, use the Loopback utility to create a mirror agreement, and then run a sample process to verify the loop-back scenario.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d953e-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d953e-111">In This Section</span></span>  
  
-   [<span data-ttu-id="d953e-112">Preparación para el tutorial</span><span class="sxs-lookup"><span data-stu-id="d953e-112">Preparing for the Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/preparing-for-the-tutorial.md)  
  
-   [<span data-ttu-id="d953e-113">Paso 1: Crear la organización principal</span><span class="sxs-lookup"><span data-stu-id="d953e-113">Step 1: Create the Home Organization</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-1-create-the-home-organization.md)  
  
-   [<span data-ttu-id="d953e-114">Paso 2: Crear la organización asociada</span><span class="sxs-lookup"><span data-stu-id="d953e-114">Step 2: Create the Partner Organization</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-create-the-partner-organization.md)  
  
-   [<span data-ttu-id="d953e-115">Paso 3: Modificar el proceso de interfaz de socio (PIP)</span><span class="sxs-lookup"><span data-stu-id="d953e-115">Step 3: Edit the Partner Interface Process</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-edit-the-partner-interface-process.md)  
  
-   [<span data-ttu-id="d953e-116">Paso 4: Crear un acuerdo comercial</span><span class="sxs-lookup"><span data-stu-id="d953e-116">Step 4: Create a Trade Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-create-a-trade-agreement.md)  
  
-   [<span data-ttu-id="d953e-117">Paso 5: Crear un acuerdo reflejado</span><span class="sxs-lookup"><span data-stu-id="d953e-117">Step 5: Create a Mirror Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-5-create-a-mirror-agreement.md)  
  
-   [<span data-ttu-id="d953e-118">Paso 6: Iniciar las orquestaciones</span><span class="sxs-lookup"><span data-stu-id="d953e-118">Step 6: Start Orchestrations</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-6-start-orchestrations.md)  
  
-   [<span data-ttu-id="d953e-119">Paso 7: Crear un mensaje de LOB de ejemplo</span><span class="sxs-lookup"><span data-stu-id="d953e-119">Step 7: Create a Sample LOB Message</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-7-create-a-sample-lob-message.md)  
  
-   [<span data-ttu-id="d953e-120">Paso 8: Ver los mensajes en las bases de datos de BTARN</span><span class="sxs-lookup"><span data-stu-id="d953e-120">Step 8: View Messages in the BTARN Databases</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-8-view-messages-in-the-btarn-databases.md)