---
title: "Resolución de acuerdo basada en las propiedades de contexto de protocolo no ha podido | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58fccd84-579c-4b5e-872b-33730d4079e8
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76d74ad7aa4a73f4a0befcef32bc8051195cb080
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="agreement-resolution-based-on-the-context-properties-for-protocol-has-failed"></a><span data-ttu-id="c7c59-102">Error en la resolución de acuerdo basada en las propiedades de contexto para el protocolo</span><span class="sxs-lookup"><span data-stu-id="c7c59-102">Agreement Resolution based on the context properties for Protocol has failed</span></span>
## <a name="details"></a><span data-ttu-id="c7c59-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="c7c59-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c7c59-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="c7c59-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="c7c59-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="c7c59-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="c7c59-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="c7c59-106">Event ID</span></span>|-|  
|<span data-ttu-id="c7c59-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="c7c59-107">Event Source</span></span>|<span data-ttu-id="c7c59-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7c59-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="c7c59-109">Componente</span><span class="sxs-lookup"><span data-stu-id="c7c59-109">Component</span></span>|<span data-ttu-id="c7c59-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="c7c59-110">EDI Engine</span></span>|  
|<span data-ttu-id="c7c59-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="c7c59-111">Symbolic Name</span></span>|<span data-ttu-id="c7c59-112">AgreementResolutionContextPropertiesLookupFailed</span><span class="sxs-lookup"><span data-stu-id="c7c59-112">AgreementResolutionContextPropertiesLookupFailed</span></span>|  
|<span data-ttu-id="c7c59-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="c7c59-113">Message Text</span></span>|<span data-ttu-id="c7c59-114">Resolución del acuerdo se basa en las propiedades de contexto para {0} protocolo ha fallado.</span><span class="sxs-lookup"><span data-stu-id="c7c59-114">Agreement Resolution based on the context properties for {0} Protocol has failed.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c7c59-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="c7c59-115">Explanation</span></span>  
 <span data-ttu-id="c7c59-116">Este evento de error,  indica que BizTalk Server no se pudo resolver en un acuerdo según las propiedades de contexto que proporciona el cliente.</span><span class="sxs-lookup"><span data-stu-id="c7c59-116">This Error/Warning/Information event indicates BizTalk Server was not able to resolve to an Agreement based on the context properties that are provided by the customer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c7c59-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="c7c59-117">User Action</span></span>  
 <span data-ttu-id="c7c59-118">Para resolver este error, proporcione las propiedades de contexto como parte del mensaje de BizTalk, de modo que la resolución del acuerdo pueda tener lugar.</span><span class="sxs-lookup"><span data-stu-id="c7c59-118">To resolve this error, please provide the context properties as part of the BizTalk message such that Agreement Resolution can happen.</span></span>