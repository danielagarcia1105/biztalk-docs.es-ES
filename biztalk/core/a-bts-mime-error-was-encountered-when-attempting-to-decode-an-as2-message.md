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
ms.openlocfilehash: 096696f4420150cdd53f8fe561460d243c1bb018
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="a-bts-mime-error-was-encountered-when-attempting-to-decode-an-as2-message"></a><span data-ttu-id="9dc3e-102">Error de BTS MIME al intentar descodificar un mensaje AS2</span><span class="sxs-lookup"><span data-stu-id="9dc3e-102">A BTS MIME error was encountered when attempting to decode an AS2 message</span></span>
## <a name="details"></a><span data-ttu-id="9dc3e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="9dc3e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9dc3e-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="9dc3e-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="9dc3e-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="9dc3e-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="9dc3e-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="9dc3e-106">Event ID</span></span>|-|  
|<span data-ttu-id="9dc3e-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="9dc3e-107">Event Source</span></span>|<span data-ttu-id="9dc3e-108">EDI de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="9dc3e-108">BizTalk Server EDI</span></span>|  
|<span data-ttu-id="9dc3e-109">Componente</span><span class="sxs-lookup"><span data-stu-id="9dc3e-109">Component</span></span>|<span data-ttu-id="9dc3e-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="9dc3e-110">AS2 Engine</span></span>|  
|<span data-ttu-id="9dc3e-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="9dc3e-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="9dc3e-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="9dc3e-112">Message Text</span></span>|<span data-ttu-id="9dc3e-113">Error de BTS MIME al intentar descodificar un mensaje AS2.</span><span class="sxs-lookup"><span data-stu-id="9dc3e-113">A BTS MIME error was encountered when attempting to decode an AS2 message.</span></span>  <span data-ttu-id="9dc3e-114">AS2-de: {0}, AS2-a: {1}, MessageId: {2}, Error: {3}</span><span class="sxs-lookup"><span data-stu-id="9dc3e-114">AS2-From: {0}, AS2-To: {1}, MessageId: {2}, Error: {3}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9dc3e-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="9dc3e-115">Explanation</span></span>  
 <span data-ttu-id="9dc3e-116">Este error aparece al usar el componente MIME de BizTalk para gestionar parte del procesamiento de MIME.</span><span class="sxs-lookup"><span data-stu-id="9dc3e-116">This error is encountered when using the BizTalk MIME component to handle part of the MIME processing.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9dc3e-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="9dc3e-117">User Action</span></span>  
 <span data-ttu-id="9dc3e-118">El mensaje de error completo proporciona la información sobre el problema detectado por el componente MIME.</span><span class="sxs-lookup"><span data-stu-id="9dc3e-118">The full error message provides the information about the problem encountered by the MIME component.</span></span> <span data-ttu-id="9dc3e-119">Consulte la información de error MIME de BTS para diagnosticar el problema (Esto es porque los componentes de AS2 usan los componentes de MIME de BizTalk para parte del procesamiento de MIME).</span><span class="sxs-lookup"><span data-stu-id="9dc3e-119">Refer to the BTS MIME error information for diagnosis of the problem (this is because the AS2 components use the BizTalk MIME components for part of the MIME processing).</span></span>