---
title: "Se encontró un error de BTS MIME al intentar descodificar un mensaje AS2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 65cb5ece-78e4-4b83-b126-4d8c588b2c61
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 660a9e3a6ca5834448dd64815b031e00a0b2942a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="a-bts-mime-error-was-encountered-when-attempting-to-decode-an-as2-message"></a><span data-ttu-id="f03a3-102">Error de BTS MIME al intentar descodificar un mensaje AS2</span><span class="sxs-lookup"><span data-stu-id="f03a3-102">A BTS MIME error was encountered when attempting to decode an AS2 message</span></span>
## <a name="details"></a><span data-ttu-id="f03a3-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="f03a3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f03a3-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="f03a3-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="f03a3-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="f03a3-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="f03a3-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="f03a3-106">Event ID</span></span>|-|  
|<span data-ttu-id="f03a3-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="f03a3-107">Event Source</span></span>|<span data-ttu-id="f03a3-108">EDI de [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f03a3-108">[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] EDI</span></span>|  
|<span data-ttu-id="f03a3-109">Componente</span><span class="sxs-lookup"><span data-stu-id="f03a3-109">Component</span></span>|<span data-ttu-id="f03a3-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="f03a3-110">AS2 Engine</span></span>|  
|<span data-ttu-id="f03a3-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="f03a3-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="f03a3-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="f03a3-112">Message Text</span></span>|<span data-ttu-id="f03a3-113">Error de BTS MIME al intentar descodificar un mensaje AS2.</span><span class="sxs-lookup"><span data-stu-id="f03a3-113">A BTS MIME error was encountered when attempting to decode an AS2 message.</span></span>  <span data-ttu-id="f03a3-114">AS2-de: {0}, AS2-a: {1}, MessageId: {2}, Error: {3}</span><span class="sxs-lookup"><span data-stu-id="f03a3-114">AS2-From: {0}, AS2-To: {1}, MessageId: {2}, Error: {3}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f03a3-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="f03a3-115">Explanation</span></span>  
 <span data-ttu-id="f03a3-116">Este error aparece al usar el componente MIME de BizTalk para gestionar parte del procesamiento de MIME.</span><span class="sxs-lookup"><span data-stu-id="f03a3-116">This error is encountered when using the BizTalk MIME component to handle part of the MIME processing.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f03a3-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="f03a3-117">User Action</span></span>  
 <span data-ttu-id="f03a3-118">El mensaje de error completo proporciona la información sobre el problema detectado por el componente MIME.</span><span class="sxs-lookup"><span data-stu-id="f03a3-118">The full error message provides the information about the problem encountered by the MIME component.</span></span> <span data-ttu-id="f03a3-119">Consulte la información de error MIME de BTS para diagnosticar el problema (Esto es porque los componentes de AS2 usan los componentes de MIME de BizTalk para parte del procesamiento de MIME).</span><span class="sxs-lookup"><span data-stu-id="f03a3-119">Refer to the BTS MIME error information for diagnosis of the problem (this is because the AS2 components use the BizTalk MIME components for part of the MIME processing).</span></span>