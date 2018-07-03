---
title: Directiva empresarial de BTARN de ejemplo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db932c17-8e8f-4f7a-b165-d1d7d749cdb6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e055d039e323fb985d9650f6f105bb3b44e9581
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974909"
---
# <a name="sample-btarn-business-policy"></a><span data-ttu-id="7961c-102">Directiva empresarial de BTARN de ejemplo</span><span class="sxs-lookup"><span data-stu-id="7961c-102">Sample BTARN Business Policy</span></span>
<span data-ttu-id="7961c-103">Este ejemplo es el código XML asociado con un Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] directiva de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="7961c-103">This sample is the XML code associated with a Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] business-rules policy.</span></span>  
  
 <span data-ttu-id="7961c-104">El archivo de ejemplo es samplebtarnpolicy.XML, en \< *unidad*\>: \Program archivos\\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\ PIPAutomation\3A4.</span><span class="sxs-lookup"><span data-stu-id="7961c-104">The sample file is samplebtarnpolicy.xml in \<*drive*\>:\Program Files\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK\PIPAutomation\3A4.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="7961c-105">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="7961c-105">Demonstrates</span></span>  
 <span data-ttu-id="7961c-106">Este código muestra una directiva de reglas de negocio con la siguiente regla:</span><span class="sxs-lookup"><span data-stu-id="7961c-106">This code shows a business-rule policy with the following rule:</span></span>  
  
 <span data-ttu-id="7961c-107">SI (AccountNumber en el mensaje del pedido de compra entrante 3A4 = "111111111") y (MonetaryAmount del pedido < 500), ENTONCES enviar automáticamente un mensaje de respuesta</span><span class="sxs-lookup"><span data-stu-id="7961c-107">IF (AccountNumber in the incoming 3A4 Purchase Order message = "111111111") and (MonetaryAmount of the Order < 500) THEN automatically send a response message</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7961c-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="7961c-108">See Also</span></span>  
 [<span data-ttu-id="7961c-109">Orquestación del respondedor privado 3A4 mediante una regla de negocio</span><span class="sxs-lookup"><span data-stu-id="7961c-109">3A4 Private Responder Orchestration Using a Business Rule</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)