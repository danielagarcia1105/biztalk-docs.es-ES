---
title: "Probar la solución | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- testing solutions
- private process tutorial, testing solutions
ms.assetid: 90faf959-bac6-4695-8cb7-ecabe52baf1a
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7af2cab529344f499ff006a6cd99401ae63c4668
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="testing-the-solution"></a><span data-ttu-id="65454-102">Probar la solución</span><span class="sxs-lookup"><span data-stu-id="65454-102">Testing the Solution</span></span>
<span data-ttu-id="65454-103">En esta sección, probará la solución completa.</span><span class="sxs-lookup"><span data-stu-id="65454-103">In this section, you test your complete solution.</span></span> <span data-ttu-id="65454-104">Utilice la herramienta de LOBWebApplication creada en la solución de Fabrikam para enviar solicitudes PIP de 3A2 a la aplicación de LOB de Contoso.</span><span class="sxs-lookup"><span data-stu-id="65454-104">You use the LOBWebApplication tool created in the Fabrikam solution to submit 3A2 PIP requests to the Contoso LOB application.</span></span> <span data-ttu-id="65454-105">La orquestación de Contoso privada que ha creado, a continuación, envía una solicitud de precio y disponibilidad de según 3A2 de Contoso al sistema ERP mediante el adaptador SQL para el servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="65454-105">The Contoso private orchestration that you created then submits a Contoso based 3A2 Price and Availability request to the ERP system using the SQL adapter for BizTalk Server.</span></span> <span data-ttu-id="65454-106">Cuando se recibe la respuesta del sistema ERP, la orquestación llama el motor de reglas de negocios para exigir la emergencia debe directiva empresarial que ha creado.</span><span class="sxs-lookup"><span data-stu-id="65454-106">When the response is received from the ERP system, the orchestration calls the Business Rule Engine to enforce the emergency needs business policy that you created.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="65454-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="65454-107">In This Section</span></span>  
  
-   [<span data-ttu-id="65454-108">Creación de una solicitud de precio y disponibilidad con el ejemplo de Fabrikam</span><span class="sxs-lookup"><span data-stu-id="65454-108">Creating a Price and Availability Request with the Fabrikam Sample</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-a-price-and-availability-request-with-the-fabrikam-sample.md)