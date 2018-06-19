---
title: Solución de problemas de procesamiento por lotes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, troubleshooting
- troubleshooting, batching
ms.assetid: f47e1a16-47fd-4bd8-8dad-fcdba31a833e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94c8413a8022529e6ace56c50d5e6d75267a72e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206308"
---
# <a name="troubleshooting-batching"></a><span data-ttu-id="65c45-102">Solución de problemas de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="65c45-102">Troubleshooting Batching</span></span>
<span data-ttu-id="65c45-103">Soluciona problemas relacionados con [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="65c45-103">Addresses issues related to [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] batching.</span></span>  
  
## <a name="error-activating-batch"></a><span data-ttu-id="65c45-104">Lote de activación de error</span><span class="sxs-lookup"><span data-stu-id="65c45-104">Error activating batch</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="65c45-105">Síntoma</span><span class="sxs-lookup"><span data-stu-id="65c45-105">Symptom</span></span>  
 <span data-ttu-id="65c45-106">No se puede activar un lote.</span><span class="sxs-lookup"><span data-stu-id="65c45-106">Unable to activate a batch.</span></span> <span data-ttu-id="65c45-107">Obtendrá un error general de red.</span><span class="sxs-lookup"><span data-stu-id="65c45-107">You get a general network error.</span></span>  
  
<span data-ttu-id="65c45-108">**Causa posible** : [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] se ha reiniciado, pero [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] no era el Explorador de configuración.</span><span class="sxs-lookup"><span data-stu-id="65c45-108">**Possible Cause** : [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] was restarted, but [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer was not.</span></span>  
  
<span data-ttu-id="65c45-109">**Resolución** : reiniciar [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración.</span><span class="sxs-lookup"><span data-stu-id="65c45-109">**Resolution** : Restart [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span>  
  
## <a name="messages-are-not-batched-when-the-target-namespace-is-not-the-default"></a><span data-ttu-id="65c45-110">No se procesan por lotes mensajes cuando el espacio de nombres de destino no es el valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="65c45-110">Messages are not batched when the target namespace is not the default</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="65c45-111">Síntoma</span><span class="sxs-lookup"><span data-stu-id="65c45-111">Symptom</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="65c45-112">no se está procesamiento por lotes de mensajes.</span><span class="sxs-lookup"><span data-stu-id="65c45-112"> is not batching messages.</span></span>  
  
<span data-ttu-id="65c45-113">**Causa posible** : entidades de origen y destino no están en el mismo espacio de nombres de esquema.</span><span class="sxs-lookup"><span data-stu-id="65c45-113">**Possible Cause** : Source and destination parties are not in the same schema namespace.</span></span>  
  
<span data-ttu-id="65c45-114">**Resolución** : entidades de origen y de destino deben usar el mismo espacio de nombres de esquema si se requiere validación.</span><span class="sxs-lookup"><span data-stu-id="65c45-114">**Resolution** : Source and destination parties must use the same schema namespace if validation is required.</span></span> <span data-ttu-id="65c45-115">Asegúrese de que las entidades de origen y de destino están utilizando el mismo espacio de nombres de esquema.</span><span class="sxs-lookup"><span data-stu-id="65c45-115">Ensure the source and destination parties are using the same schema namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65c45-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="65c45-116">See Also</span></span>  
 [<span data-ttu-id="65c45-117">Solución de problemas y problemas conocidos de HL7</span><span class="sxs-lookup"><span data-stu-id="65c45-117">Troubleshooting and known issues in HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)