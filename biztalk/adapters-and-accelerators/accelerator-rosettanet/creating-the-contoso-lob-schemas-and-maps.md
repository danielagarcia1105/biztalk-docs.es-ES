---
title: Crear los esquemas LOB de Contoso y asignaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, LOB
- LOBs, schemas
- private process tutorial, creating LOB schemas
- private process tutorial, creating maps
- maps
ms.assetid: fda8852a-51d8-4987-a187-834883a06d9b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f204efd00858f3f4204848f4fb4a0dcef5233b3c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-the-contoso-lob-schemas-and-maps"></a><span data-ttu-id="ed416-102">Creando los esquemas y asignaciones de LOB de Contoso</span><span class="sxs-lookup"><span data-stu-id="ed416-102">Creating the Contoso LOB Schemas and Maps</span></span>
<span data-ttu-id="ed416-103">En esta sección, creará los esquemas de línea de negocio (LOB) que la organización Contoso usa en su sistema ERP.</span><span class="sxs-lookup"><span data-stu-id="ed416-103">In this section, you create the line-of-business (LOB) schemas that the Contoso organization uses in their ERP system.</span></span> <span data-ttu-id="ed416-104">Usa el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] herramienta asignador para crear transformaciones de datos entre los mensajes internos de Contoso y los tipos de mensajes de RosettaNet entrantes y salientes.</span><span class="sxs-lookup"><span data-stu-id="ed416-104">You use the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Mapper tool to create data transformations between the internal Contoso messages and the inbound and outbound RosettaNet message types.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ed416-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ed416-105">In This Section</span></span>  
  
-   [<span data-ttu-id="ed416-106">Paso 1: Crear una nueva solución de BizTalk para la solicitud de disponibilidad y el precio de Contoso</span><span class="sxs-lookup"><span data-stu-id="ed416-106">Step 1: Creating a New BizTalk Solution for the Contoso Price and Availability Request</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-1-create-new-biztalk-solution-for-contoso-price-and-availability-request.md)  
  
-   [<span data-ttu-id="ed416-107">Paso 2: Crear los esquemas de aplicación de LOB de Contoso para el precio y el proyecto de disponibilidad mediante el Editor de BizTalk</span><span class="sxs-lookup"><span data-stu-id="ed416-107">Step 2: Creating the Contoso LOB Application Schemas for the Price and Availability Project Using BizTalk Editor</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-create-contoso-lob-application-schema-for-price-and-availability.md)  
  
-   [<span data-ttu-id="ed416-108">Paso 3: Crear las asignaciones de aplicación de LOB de Contoso para el precio y el proyecto de disponibilidad mediante el asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="ed416-108">Step 3: Creating the Contoso LOB Application Maps for the Price and Availability Project Using BizTalk Mapper</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-create-contoso-lob-application-map-for-price-and-availability-in-mapper.md)