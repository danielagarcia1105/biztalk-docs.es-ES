---
title: Directiva empresarial de BTARN de ejemplo | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: db932c17-8e8f-4f7a-b165-d1d7d749cdb6
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bfe0bd746894106fc7ac9ebeaae600fe7344ba18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sample-btarn-business-policy"></a><span data-ttu-id="aa02a-102">Directiva empresarial de BTARN de ejemplo</span><span class="sxs-lookup"><span data-stu-id="aa02a-102">Sample BTARN Business Policy</span></span>
<span data-ttu-id="aa02a-103">Este ejemplo es el código XML asociado con un [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] directiva de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="aa02a-103">This sample is the XML code associated with a [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] business-rules policy.</span></span>  
  
 <span data-ttu-id="aa02a-104">El archivo de ejemplo es samplebtarnpolicy.XML, en \< *unidad*>: \Program archivos\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<versión > Accelerator for RosettaNet\SDK\PIPAutomation\3A4.</span><span class="sxs-lookup"><span data-stu-id="aa02a-104">The sample file is samplebtarnpolicy.xml in \<*drive*>:\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<version> Accelerator for RosettaNet\SDK\PIPAutomation\3A4.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="aa02a-105">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="aa02a-105">Demonstrates</span></span>  
 <span data-ttu-id="aa02a-106">Este código muestra una directiva de reglas de negocio con la siguiente regla:</span><span class="sxs-lookup"><span data-stu-id="aa02a-106">This code shows a business-rule policy with the following rule:</span></span>  
  
 <span data-ttu-id="aa02a-107">SI (AccountNumber en el mensaje del pedido de compra entrante 3A4 = "111111111") y (MonetaryAmount del pedido < 500), ENTONCES enviar automáticamente un mensaje de respuesta</span><span class="sxs-lookup"><span data-stu-id="aa02a-107">IF (AccountNumber in the incoming 3A4 Purchase Order message = "111111111") and (MonetaryAmount of the Order < 500) THEN automatically send a response message</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa02a-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa02a-108">See Also</span></span>  
 [<span data-ttu-id="aa02a-109">Orquestación de Respondedor privada de 3A4 mediante una regla de negocios</span><span class="sxs-lookup"><span data-stu-id="aa02a-109">3A4 Private Responder Orchestration Using a Business Rule</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)