---
title: No se puede obtener acceso al Acuerdo mediante la identidad del receptor | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 470325f4-abc4-40bb-9109-9ffc73b496df
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 630ce4850c2bb11f9b5a18db03204ef2c1e24cae
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003733"
---
# <a name="unable-to-access-agreement-using-receiver-identity"></a><span data-ttu-id="d592e-102">No se puede obtener acceso al acuerdo mediante la identidad del receptor</span><span class="sxs-lookup"><span data-stu-id="d592e-102">Unable to access agreement using receiver identity</span></span>
## <a name="details"></a><span data-ttu-id="d592e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="d592e-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="d592e-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="d592e-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="d592e-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="d592e-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="d592e-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="d592e-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="d592e-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="d592e-107">Event Source</span></span>   | <span data-ttu-id="d592e-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d592e-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="d592e-109">Componente</span><span class="sxs-lookup"><span data-stu-id="d592e-109">Component</span></span>    |                                       <span data-ttu-id="d592e-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="d592e-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="d592e-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d592e-111">Symbolic Name</span></span>  |                         <span data-ttu-id="d592e-112">UnableToLocateAS2PartyByPartyNameError</span><span class="sxs-lookup"><span data-stu-id="d592e-112">UnableToLocateAS2PartyByPartyNameError</span></span>                         |
|  <span data-ttu-id="d592e-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d592e-113">Message Text</span></span>   |                <span data-ttu-id="d592e-114">No se puede obtener acceso al Acuerdo mediante la identidad del receptor: {0}</span><span class="sxs-lookup"><span data-stu-id="d592e-114">Unable to access agreement using receiver identity: {0}</span></span>                 |
  
## <a name="explanation"></a><span data-ttu-id="d592e-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="d592e-115">Explanation</span></span>  
 <span data-ttu-id="d592e-116">Este error indica que la canalización de envío no pudo determinar la entidad para un mensaje AS2 saliente porque no pudo hacer coincidir la propiedad de contexto AS2To del mensaje saliente o la propiedad AS2To de la propiedad de contexto Http.UserHttpheaders con el nombre de la entidad en la propiedad AS2-To de la página Entidad como receptora del mensaje AS2 del cuadro de diálogo Propiedades de AS2.</span><span class="sxs-lookup"><span data-stu-id="d592e-116">This error indicates that the send pipeline could not determine the party for an outgoing AS2 message because it could not match the AS2To context property of the outbound message or the AS2To property in the Http.UserHttpHeaders context property with the name of the party in the AS2-To property in the Party as AS2 Message Receiver page of the AS2 Properties dialog box.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d592e-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d592e-117">User Action</span></span>  
 <span data-ttu-id="d592e-118">Para resolver este error, configure la propiedad AS2-To de la página Entidad como receptora del mensaje AS2 del cuadro de diálogo Propiedades de AS2 en el nombre de entidad adecuado asociado con el mensaje AS2 que tiene un error.</span><span class="sxs-lookup"><span data-stu-id="d592e-118">To resolve this error, set the AS2-To property in the Party as AS2 Message Receiver page of the AS2 Properties dialog box to the appropriate party name associated with the AS2 message that is in error.</span></span>