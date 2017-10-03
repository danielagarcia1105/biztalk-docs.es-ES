---
title: No se puede obtener acceso al Acuerdo mediante la identidad del receptor | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 470325f4-abc4-40bb-9109-9ffc73b496df
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f41b126ca0ebb96716f21381d2e1681ea59bd414
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="unable-to-access-agreement-using-receiver-identity"></a><span data-ttu-id="506e4-102">No se puede obtener acceso al acuerdo mediante la identidad del receptor</span><span class="sxs-lookup"><span data-stu-id="506e4-102">Unable to access agreement using receiver identity</span></span>
## <a name="details"></a><span data-ttu-id="506e4-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="506e4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="506e4-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="506e4-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="506e4-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="506e4-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="506e4-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="506e4-106">Event ID</span></span>|-|  
|<span data-ttu-id="506e4-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="506e4-107">Event Source</span></span>|<span data-ttu-id="506e4-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="506e4-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="506e4-109">Componente</span><span class="sxs-lookup"><span data-stu-id="506e4-109">Component</span></span>|<span data-ttu-id="506e4-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="506e4-110">AS2 Engine</span></span>|  
|<span data-ttu-id="506e4-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="506e4-111">Symbolic Name</span></span>|<span data-ttu-id="506e4-112">UnableToLocateAS2PartyByPartyNameError</span><span class="sxs-lookup"><span data-stu-id="506e4-112">UnableToLocateAS2PartyByPartyNameError</span></span>|  
|<span data-ttu-id="506e4-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="506e4-113">Message Text</span></span>|<span data-ttu-id="506e4-114">No se puede obtener acceso al Acuerdo mediante la identidad del receptor: {0}</span><span class="sxs-lookup"><span data-stu-id="506e4-114">Unable to access agreement using receiver identity: {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="506e4-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="506e4-115">Explanation</span></span>  
 <span data-ttu-id="506e4-116">Este error indica que la canalización de envío no pudo determinar la entidad para un mensaje AS2 saliente porque no pudo hacer coincidir la propiedad de contexto AS2To del mensaje saliente o la propiedad AS2To de la propiedad de contexto Http.UserHttpheaders con el nombre de la entidad en la propiedad AS2-To de la página Entidad como receptora del mensaje AS2 del cuadro de diálogo Propiedades de AS2.</span><span class="sxs-lookup"><span data-stu-id="506e4-116">This error indicates that the send pipeline could not determine the party for an outgoing AS2 message because it could not match the AS2To context property of the outbound message or the AS2To property in the Http.UserHttpHeaders context property with the name of the party in the AS2-To property in the Party as AS2 Message Receiver page of the AS2 Properties dialog box.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="506e4-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="506e4-117">User Action</span></span>  
 <span data-ttu-id="506e4-118">Para resolver este error, configure la propiedad AS2-To de la página Entidad como receptora del mensaje AS2 del cuadro de diálogo Propiedades de AS2 en el nombre de entidad adecuado asociado con el mensaje AS2 que tiene un error.</span><span class="sxs-lookup"><span data-stu-id="506e4-118">To resolve this error, set the AS2-To property in the Party as AS2 Message Receiver page of the AS2 Properties dialog box to the appropriate party name associated with the AS2 message that is in error.</span></span>