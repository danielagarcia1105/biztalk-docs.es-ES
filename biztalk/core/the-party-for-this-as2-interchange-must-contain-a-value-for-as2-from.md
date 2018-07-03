---
title: La entidad de este intercambio AS2 debe contener un valor para AS2-desde | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d338759-5646-4dc2-8319-a42aaa8c3d9c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 637224e0519a181c71b12e390c39c821ad354ac6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009253"
---
# <a name="the-party-for-this-as2-interchange-must-contain-a-value-for-as2-from"></a><span data-ttu-id="3c579-102">La entidad de este intercambio AS2 debe contener un valor AS2-From</span><span class="sxs-lookup"><span data-stu-id="3c579-102">The party for this AS2 interchange must contain a value for AS2-From</span></span>
## <a name="details"></a><span data-ttu-id="3c579-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="3c579-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="3c579-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="3c579-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="3c579-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="3c579-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="3c579-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="3c579-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="3c579-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="3c579-107">Event Source</span></span>   | <span data-ttu-id="3c579-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c579-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="3c579-109">Componente</span><span class="sxs-lookup"><span data-stu-id="3c579-109">Component</span></span>    |                                       <span data-ttu-id="3c579-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="3c579-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="3c579-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3c579-111">Symbolic Name</span></span>  |                              <span data-ttu-id="3c579-112">InvalidAgreementAS2FromName</span><span class="sxs-lookup"><span data-stu-id="3c579-112">InvalidAgreementAS2FromName</span></span>                               |
|  <span data-ttu-id="3c579-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3c579-113">Message Text</span></span>   |         <span data-ttu-id="3c579-114">La entidad de este intercambio AS2 debe contener un valor AS2-From.</span><span class="sxs-lookup"><span data-stu-id="3c579-114">The party for this AS2 interchange must contain a value for AS2-From.</span></span>          |
  
## <a name="explanation"></a><span data-ttu-id="3c579-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="3c579-115">Explanation</span></span>  
 <span data-ttu-id="3c579-116">Este evento de error,  indica que la canalización de envío no pudo enviar el mensaje AS2 porque no se ha configurado la propiedad AS2-From para la entidad resuelta como receptora del mensaje.</span><span class="sxs-lookup"><span data-stu-id="3c579-116">This Error/Warning/Information event indicates that the send pipeline could not send the AS2 message because the AS2-From property was not set for the resolved party as message receiver.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3c579-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3c579-117">User Action</span></span>  
 <span data-ttu-id="3c579-118">Para resolver este error, abra la consola de administración de BizTalk Server, vaya al nodo Entidades, abra el cuadro de diálogo Propiedades de AS2 de la entidad resuelta para el mensaje, haga clic en el nodo Entidad como receptora del mensaje AS2 y especifique un valor para la propiedad AS2-From.</span><span class="sxs-lookup"><span data-stu-id="3c579-118">To resolve this error, open the BizTalk Server Administration Console, move to the Parties node, open the AS2 Properties dialog box for the party resolved for the message, click the Party as AS2 Message Receiver node, and then enter a value for the AS2-From property.</span></span>