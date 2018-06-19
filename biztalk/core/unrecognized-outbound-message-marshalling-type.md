---
title: Cálculo de referencias de tipo de mensaje saliente no reconocido | Documentos de Microsoft
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
ms.openlocfilehash: 3928bde0d81a4fe22b7c16af41c3a4b6d5c7121c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286660"
---
# <a name="unrecognized-outbound-message-marshalling-type"></a><span data-ttu-id="1aaa0-102">Tipo de serialización de mensaje saliente no reconocido</span><span class="sxs-lookup"><span data-stu-id="1aaa0-102">Unrecognized outbound message marshalling type</span></span>
## <a name="details"></a><span data-ttu-id="1aaa0-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="1aaa0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1aaa0-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="1aaa0-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="1aaa0-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="1aaa0-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="1aaa0-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="1aaa0-106">Event ID</span></span>|<span data-ttu-id="1aaa0-107">0</span><span class="sxs-lookup"><span data-stu-id="1aaa0-107">0</span></span>|  
|<span data-ttu-id="1aaa0-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="1aaa0-108">Event Source</span></span>|<span data-ttu-id="1aaa0-109">0</span><span class="sxs-lookup"><span data-stu-id="1aaa0-109">0</span></span>|  
|<span data-ttu-id="1aaa0-110">Componente</span><span class="sxs-lookup"><span data-stu-id="1aaa0-110">Component</span></span>|<span data-ttu-id="1aaa0-111">0</span><span class="sxs-lookup"><span data-stu-id="1aaa0-111">0</span></span>|  
|<span data-ttu-id="1aaa0-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="1aaa0-112">Symbolic Name</span></span>|<span data-ttu-id="1aaa0-113">0</span><span class="sxs-lookup"><span data-stu-id="1aaa0-113">0</span></span>|  
|<span data-ttu-id="1aaa0-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="1aaa0-114">Message Text</span></span>|<span data-ttu-id="1aaa0-115">Tipo de serialización de mensaje saliente no reconocido; se esperaba UseBodyElement o UseTemplate.</span><span class="sxs-lookup"><span data-stu-id="1aaa0-115">Unrecognized outbound message marshalling type; expected UseBodyElement or UseTemplate</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1aaa0-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="1aaa0-116">Explanation</span></span>  
 <span data-ttu-id="1aaa0-117">La propiedad WCF.OutboundBodyLocation se estableció en un valor distinto de UseBodyElement o UseTemplate, en un componente de canalización o una orquestación personalizados.</span><span class="sxs-lookup"><span data-stu-id="1aaa0-117">The WCF.OutboundBodyLocation property is set to a value different than UseBodyElement or UseTemplate, in a custom pipeline component or orchestration.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1aaa0-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="1aaa0-118">User Action</span></span>  
 <span data-ttu-id="1aaa0-119">Establezca la propiedad WCF.OutboundBodyLocation en un valor válido.</span><span class="sxs-lookup"><span data-stu-id="1aaa0-119">Set the WCF.OutboundBodyLocation property to a valid value.</span></span> <span data-ttu-id="1aaa0-120">Los valores válidos son "UseBodyElement" o "UseTemplate". Se trata de un cambio de código.</span><span class="sxs-lookup"><span data-stu-id="1aaa0-120">Valid values are "UseBodyElement" or "UseTemplate" This is a code change.</span></span>   
<span data-ttu-id="1aaa0-121">Para obtener más información acerca de los mensajes salientes, vea los siguientes recursos en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda:</span><span class="sxs-lookup"><span data-stu-id="1aaa0-121">For further information about outbound messaging, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="1aaa0-122">Configuración de puertos de envío dinámicos mediante propiedades de contexto de adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="1aaa0-122">Configuring Dynamic Send Ports Using WCF Adapters Context Properties</span></span>](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)  
  
-   [<span data-ttu-id="1aaa0-123">Configurar los adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="1aaa0-123">Configuring the WCF Adapters</span></span>](../core/configuring-the-wcf-adapters.md)