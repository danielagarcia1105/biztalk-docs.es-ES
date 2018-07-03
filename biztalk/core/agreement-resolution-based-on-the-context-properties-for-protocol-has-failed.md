---
title: Resolución del acuerdo según las propiedades de contexto de protocolo no ha podido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58fccd84-579c-4b5e-872b-33730d4079e8
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2cac1ea6e940385fceac541df96582f93eb058e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008173"
---
# <a name="agreement-resolution-based-on-the-context-properties-for-protocol-has-failed"></a><span data-ttu-id="e9d4c-102">Error en la resolución de acuerdo basada en las propiedades de contexto para el protocolo</span><span class="sxs-lookup"><span data-stu-id="e9d4c-102">Agreement Resolution based on the context properties for Protocol has failed</span></span>
## <a name="details"></a><span data-ttu-id="e9d4c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="e9d4c-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="e9d4c-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="e9d4c-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="e9d4c-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="e9d4c-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="e9d4c-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="e9d4c-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="e9d4c-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="e9d4c-107">Event Source</span></span>   | <span data-ttu-id="e9d4c-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9d4c-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="e9d4c-109">Componente</span><span class="sxs-lookup"><span data-stu-id="e9d4c-109">Component</span></span>    |                                       <span data-ttu-id="e9d4c-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="e9d4c-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="e9d4c-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e9d4c-111">Symbolic Name</span></span>  |                    <span data-ttu-id="e9d4c-112">AgreementResolutionContextPropertiesLookupFailed</span><span class="sxs-lookup"><span data-stu-id="e9d4c-112">AgreementResolutionContextPropertiesLookupFailed</span></span>                    |
|  <span data-ttu-id="e9d4c-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e9d4c-113">Message Text</span></span>   |   <span data-ttu-id="e9d4c-114">Resolución del acuerdo según las propiedades de contexto {0} ha producido un error de protocolo.</span><span class="sxs-lookup"><span data-stu-id="e9d4c-114">Agreement Resolution based on the context properties for {0} Protocol has failed.</span></span>    |
  
## <a name="explanation"></a><span data-ttu-id="e9d4c-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="e9d4c-115">Explanation</span></span>  
 <span data-ttu-id="e9d4c-116">Este evento de error,  indica que BizTalk Server no se pudo resolver en un acuerdo según las propiedades de contexto que proporciona el cliente.</span><span class="sxs-lookup"><span data-stu-id="e9d4c-116">This Error/Warning/Information event indicates BizTalk Server was not able to resolve to an Agreement based on the context properties that are provided by the customer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e9d4c-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e9d4c-117">User Action</span></span>  
 <span data-ttu-id="e9d4c-118">Para resolver este error, proporcione las propiedades de contexto como parte del mensaje de BizTalk, de modo que la resolución del acuerdo pueda tener lugar.</span><span class="sxs-lookup"><span data-stu-id="e9d4c-118">To resolve this error, please provide the context properties as part of the BizTalk message such that Agreement Resolution can happen.</span></span>