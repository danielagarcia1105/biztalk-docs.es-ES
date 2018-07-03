---
title: Tipo de serialización de mensaje saliente no reconocido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e675112b-12f3-47ff-95f7-ce1a05db120e
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cda3e7bd3d20e39bb59c2c1fbe14dfc964fd541a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023434"
---
# <a name="unrecognized-outbound-message-marshalling-type"></a><span data-ttu-id="29a5b-102">Tipo de serialización de mensaje saliente no reconocido</span><span class="sxs-lookup"><span data-stu-id="29a5b-102">Unrecognized outbound message marshalling type</span></span>
## <a name="details"></a><span data-ttu-id="29a5b-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="29a5b-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="29a5b-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="29a5b-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="29a5b-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="29a5b-105">Product Version</span></span> |               [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]               |
|    <span data-ttu-id="29a5b-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="29a5b-106">Event ID</span></span>     |                                           <span data-ttu-id="29a5b-107">0</span><span class="sxs-lookup"><span data-stu-id="29a5b-107">0</span></span>                                            |
|  <span data-ttu-id="29a5b-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="29a5b-108">Event Source</span></span>   |                                           <span data-ttu-id="29a5b-109">0</span><span class="sxs-lookup"><span data-stu-id="29a5b-109">0</span></span>                                            |
|    <span data-ttu-id="29a5b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="29a5b-110">Component</span></span>    |                                           <span data-ttu-id="29a5b-111">0</span><span class="sxs-lookup"><span data-stu-id="29a5b-111">0</span></span>                                            |
|  <span data-ttu-id="29a5b-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="29a5b-112">Symbolic Name</span></span>  |                                           <span data-ttu-id="29a5b-113">0</span><span class="sxs-lookup"><span data-stu-id="29a5b-113">0</span></span>                                            |
|  <span data-ttu-id="29a5b-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="29a5b-114">Message Text</span></span>   | <span data-ttu-id="29a5b-115">Tipo de serialización de mensaje saliente no reconocido; se esperaba UseBodyElement o UseTemplate.</span><span class="sxs-lookup"><span data-stu-id="29a5b-115">Unrecognized outbound message marshalling type; expected UseBodyElement or UseTemplate</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="29a5b-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="29a5b-116">Explanation</span></span>  
 <span data-ttu-id="29a5b-117">La propiedad WCF.OutboundBodyLocation se estableció en un valor distinto de UseBodyElement o UseTemplate, en un componente de canalización o una orquestación personalizados.</span><span class="sxs-lookup"><span data-stu-id="29a5b-117">The WCF.OutboundBodyLocation property is set to a value different than UseBodyElement or UseTemplate, in a custom pipeline component or orchestration.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="29a5b-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="29a5b-118">User Action</span></span>  
 <span data-ttu-id="29a5b-119">Establezca la propiedad WCF.OutboundBodyLocation en un valor válido.</span><span class="sxs-lookup"><span data-stu-id="29a5b-119">Set the WCF.OutboundBodyLocation property to a valid value.</span></span> <span data-ttu-id="29a5b-120">Los valores válidos son "UseBodyElement" o "UseTemplate". Se trata de un cambio de código.</span><span class="sxs-lookup"><span data-stu-id="29a5b-120">Valid values are "UseBodyElement" or "UseTemplate" This is a code change.</span></span>   
<span data-ttu-id="29a5b-121">Para obtener más información sobre la mensajería saliente, consulte los siguientes recursos en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda:</span><span class="sxs-lookup"><span data-stu-id="29a5b-121">For further information about outbound messaging, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="29a5b-122">Configuración de puertos de envío dinámico mediante el uso de propiedades de contexto de adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="29a5b-122">Configuring Dynamic Send Ports Using WCF Adapters Context Properties</span></span>](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)  
  
-   [<span data-ttu-id="29a5b-123">Configuración de adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="29a5b-123">Configuring the WCF Adapters</span></span>](../core/configuring-the-wcf-adapters.md)