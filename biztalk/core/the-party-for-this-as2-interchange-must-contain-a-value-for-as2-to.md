---
title: La entidad de este intercambio AS2 debe contener un valor para AS2-para | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 029eae5d-4c13-402d-90c5-8e9ef3814a1f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 333657b16b0e4a0b9bbbb30c73641f7db8466b87
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006701"
---
# <a name="the-party-for-this-as2-interchange-must-contain-a-value-for-as2-to"></a><span data-ttu-id="9a10e-102">La entidad de este intercambio AS2 debe contener un valor para AS2-To</span><span class="sxs-lookup"><span data-stu-id="9a10e-102">The party for this AS2 interchange must contain a value for AS2-To</span></span>
## <a name="details"></a><span data-ttu-id="9a10e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="9a10e-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="9a10e-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="9a10e-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="9a10e-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="9a10e-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="9a10e-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="9a10e-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="9a10e-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="9a10e-107">Event Source</span></span>   | <span data-ttu-id="9a10e-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a10e-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="9a10e-109">Componente</span><span class="sxs-lookup"><span data-stu-id="9a10e-109">Component</span></span>    |                                       <span data-ttu-id="9a10e-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="9a10e-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="9a10e-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="9a10e-111">Symbolic Name</span></span>  |                               <span data-ttu-id="9a10e-112">InvalidAgreementAS2ToName</span><span class="sxs-lookup"><span data-stu-id="9a10e-112">InvalidAgreementAS2ToName</span></span>                                |
|  <span data-ttu-id="9a10e-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="9a10e-113">Message Text</span></span>   |          <span data-ttu-id="9a10e-114">La entidad de este intercambio AS2 debe contener un valor para AS2-To.</span><span class="sxs-lookup"><span data-stu-id="9a10e-114">The party for this AS2 interchange must contain a value for AS2-To.</span></span>           |
  
## <a name="explanation"></a><span data-ttu-id="9a10e-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="9a10e-115">Explanation</span></span>  
 <span data-ttu-id="9a10e-116">Este evento de error, advertencia o información indica que la canalización de envío no pudo procesar el mensaje AS2 saliente porque no se ha configurado la propiedad AS2-To para la entidad resuelta como receptora del mensaje.</span><span class="sxs-lookup"><span data-stu-id="9a10e-116">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing AS2 message because the AS2-To property was not set for the resolved party as message receiver.</span></span> <span data-ttu-id="9a10e-117">Esto indica que la entidad para el mensaje AS2 saliente se ha resuelto al hacer coincidir el puerto de envío asociado con la entidad con el puerto de envío que suscribió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="9a10e-117">This indicates that the party for the outgoing AS2 message was resolved by matching the send port associated with the party with the send port that subscribed to the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9a10e-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="9a10e-118">User Action</span></span>  
 <span data-ttu-id="9a10e-119">Para resolver este error, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9a10e-119">To resolve this error, do as follows:</span></span>  
  
1.  <span data-ttu-id="9a10e-120">Abra la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="9a10e-120">Open the BizTalk Server Administration Console.</span></span>  
  
2.  <span data-ttu-id="9a10e-121">Vaya al nodo Entidades y abra el cuadro de diálogo Propiedades de AS2 para la entidad resuelta para el mensaje.</span><span class="sxs-lookup"><span data-stu-id="9a10e-121">Move to the Parties node, and open the AS2 Properties dialog box for the party resolved for the message.</span></span>  
  
3.  <span data-ttu-id="9a10e-122">Haga clic en el nodo Entidad como receptora del mensaje AS2</span><span class="sxs-lookup"><span data-stu-id="9a10e-122">Click the Party as AS2 Message Receiver node.</span></span>  
  
4.  <span data-ttu-id="9a10e-123">Escriba un valor para la propiedad AS2-To.</span><span class="sxs-lookup"><span data-stu-id="9a10e-123">Enter a value for the AS2-To property.</span></span>