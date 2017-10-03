---
title: "Respuesta FIN conciliación solucionar problemas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FIN Response Reconciliation, troubleshooting
- troubleshooting, FIN Response Reconciliation
ms.assetid: f62326aa-9a4e-4941-a9bb-20bde980f99e
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a92812086f191d5777b387d9861b32a3147c1e96
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="fin-response-reconciliation-troubleshooting"></a><span data-ttu-id="eb6b1-102">Respuesta FIN conciliación solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="eb6b1-102">FIN Response Reconciliation Troubleshooting</span></span>
## <a name="the-frr-bam-view-does-not-show-the-message-type-of-a-message"></a><span data-ttu-id="eb6b1-103">La vista de BAM FRR no muestra el tipo de mensaje de un mensaje</span><span class="sxs-lookup"><span data-stu-id="eb6b1-103">The FRR BAM view does not show the message type of a message</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="eb6b1-104">Síntoma</span><span class="sxs-lookup"><span data-stu-id="eb6b1-104">Symptom</span></span>  
 <span data-ttu-id="eb6b1-105">La vista FRR BAM en el sitio MRSR no muestra el tipo de mensaje para uno o más mensajes.</span><span class="sxs-lookup"><span data-stu-id="eb6b1-105">The FRR BAM view in MRSR site does not show the message type for one or more messages.</span></span> <span data-ttu-id="eb6b1-106">Todos los demás datos para el mensaje o los mensajes se muestran y se muestra el tipo de mensaje para instancias de todos los demás tipos de mensaje.</span><span class="sxs-lookup"><span data-stu-id="eb6b1-106">All other data for the message or messages is shown, and the message type is shown for instances of all other message types.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="eb6b1-107">Causa posible</span><span class="sxs-lookup"><span data-stu-id="eb6b1-107">Possible Cause</span></span>  
 <span data-ttu-id="eb6b1-108">La actividad FRRMessageOut no registra el tipo de mensaje para los mensajes de F21 (confirmaciones/NAKs).</span><span class="sxs-lookup"><span data-stu-id="eb6b1-108">The FRRMessageOut activity does not record the message type for F21 messages (ACKs/NAKs).</span></span>  
  
### <a name="solution"></a><span data-ttu-id="eb6b1-109">Solución</span><span class="sxs-lookup"><span data-stu-id="eb6b1-109">Solution</span></span>  
 <span data-ttu-id="eb6b1-110">Si se produce este problema, interpretar los mensajes que no tiene un tipo de mensaje que aparece en la vista FRR BAM en el sitio MRSR como un mensaje F21.</span><span class="sxs-lookup"><span data-stu-id="eb6b1-110">If you encounter this problem, interpret any message that does not have a message type listed in the FRR BAM view in MRSR site as an F21 message.</span></span>  
  
## <a name="deploying-system-level-schemas-in-a-project-generates-an-error"></a><span data-ttu-id="eb6b1-111">Esquemas de nivel de sistema en un proyecto de implementación genera un error</span><span class="sxs-lookup"><span data-stu-id="eb6b1-111">Deploying system-level schemas in a project generates an error</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="eb6b1-112">Síntoma</span><span class="sxs-lookup"><span data-stu-id="eb6b1-112">Symptom</span></span>  
 <span data-ttu-id="eb6b1-113">Cuando intenta implementar los esquemas de nivel de sistema de FrrSchemas.dll en un proyecto, recibirá un error.</span><span class="sxs-lookup"><span data-stu-id="eb6b1-113">When you attempt to deploy the system-level schemas in FrrSchemas.dll in a project, you receive an error.</span></span> <span data-ttu-id="eb6b1-114">Para obtener una lista de estos esquemas, vea [tipos de respuesta de FIN](../../adapters-and-accelerators/accelerator-swift/fin-response-types.md).</span><span class="sxs-lookup"><span data-stu-id="eb6b1-114">For a list of these schemas, see [FIN Response Types](../../adapters-and-accelerators/accelerator-swift/fin-response-types.md).</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="eb6b1-115">Causa posible</span><span class="sxs-lookup"><span data-stu-id="eb6b1-115">Possible Cause</span></span>  
 <span data-ttu-id="eb6b1-116">Los esquemas de nivel de sistema de FrrSchemas.dll se hayan implementado en FrrSchemas.dll.</span><span class="sxs-lookup"><span data-stu-id="eb6b1-116">The system-level schemas in FrrSchemas.dll are already deployed in FrrSchemas.dll.</span></span> <span data-ttu-id="eb6b1-117">Intentando implementarlos nuevo produce un error.</span><span class="sxs-lookup"><span data-stu-id="eb6b1-117">Trying to deploy them again results in an error.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="eb6b1-118">Solución</span><span class="sxs-lookup"><span data-stu-id="eb6b1-118">Solution</span></span>  
 <span data-ttu-id="eb6b1-119">No hay ninguna necesidad de implementar los esquemas de nivel de sistema de FrrSchemas.dll.</span><span class="sxs-lookup"><span data-stu-id="eb6b1-119">There is no need to deploy the system-level schemas in FrrSchemas.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb6b1-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb6b1-120">See Also</span></span>  
 [<span data-ttu-id="eb6b1-121">Solución de problemas: Problemas y soluciones</span><span class="sxs-lookup"><span data-stu-id="eb6b1-121">Troubleshooting: Issues and Resolutions</span></span>](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)