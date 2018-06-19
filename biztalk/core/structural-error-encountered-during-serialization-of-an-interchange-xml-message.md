---
title: Error estructural detectado durante la serialización de un mensaje XML de intercambio | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 97939bfd-d1ee-455a-9952-4f25db020e7c
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44b56cce9fdd3704f7e6ddc2ba5b5bebb62d36e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278596"
---
# <a name="structural-error-encountered-during-serialization-of-an-interchange-xml-message"></a><span data-ttu-id="ddcba-102">Error estructural detectado durante la serialización de un mensaje XML de intercambio</span><span class="sxs-lookup"><span data-stu-id="ddcba-102">Structural error encountered during serialization of an interchange XML message</span></span>
## <a name="details"></a><span data-ttu-id="ddcba-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ddcba-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ddcba-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ddcba-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="ddcba-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ddcba-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="ddcba-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ddcba-106">Event ID</span></span>|-|  
|<span data-ttu-id="ddcba-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ddcba-107">Event Source</span></span>|<span data-ttu-id="ddcba-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddcba-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="ddcba-109">Componente</span><span class="sxs-lookup"><span data-stu-id="ddcba-109">Component</span></span>|<span data-ttu-id="ddcba-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="ddcba-110">EDI Engine</span></span>|  
|<span data-ttu-id="ddcba-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ddcba-111">Symbolic Name</span></span>|<span data-ttu-id="ddcba-112">InvalidXmlNodeFound</span><span class="sxs-lookup"><span data-stu-id="ddcba-112">InvalidXmlNodeFound</span></span>|  
|<span data-ttu-id="ddcba-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ddcba-113">Message Text</span></span>|<span data-ttu-id="ddcba-114">Error estructural detectado durante la serialización de un mensaje Xml de intercambio.</span><span class="sxs-lookup"><span data-stu-id="ddcba-114">Structural error encountered during serialization of an Interchange Xml message</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ddcba-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="ddcba-115">Explanation</span></span>  
 <span data-ttu-id="ddcba-116">Este error indica que se encontró un error estructural durante la serialización de un mensaje XML de intercambio.</span><span class="sxs-lookup"><span data-stu-id="ddcba-116">This error indicates that a structural error was encountered during serialization of an interchange XML message.</span></span> <span data-ttu-id="ddcba-117">BTS buscaba un StartElement o EndElement XML, pero encontró un tipo de nodo XML diferente.</span><span class="sxs-lookup"><span data-stu-id="ddcba-117">BTS was looking for an XML StartElement or EndElement but instead a different XML node type was encountered.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ddcba-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ddcba-118">User Action</span></span>  
 <span data-ttu-id="ddcba-119">Para resolver este error, asegúrese de que la estructura del mensaje es correcta y vuelva a intentarlo:</span><span class="sxs-lookup"><span data-stu-id="ddcba-119">To resolve this error, make sure the message structure is correct, and try again:</span></span>  
  
1.  <span data-ttu-id="ddcba-120">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="ddcba-120">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="ddcba-121">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]y haga clic en **grupo de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="ddcba-121">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and click **BizTalk Group**.</span></span>  
  
3.  <span data-ttu-id="ddcba-122">En el panel derecho, haga clic en el **concentrador de grupo** ficha.</span><span class="sxs-lookup"><span data-stu-id="ddcba-122">In the right pane, click the **Group Hub** tab.</span></span>  
  
4.  <span data-ttu-id="ddcba-123">Haga clic en **instancias de servicio suspendidas**.</span><span class="sxs-lookup"><span data-stu-id="ddcba-123">Click **Suspended Service instances**.</span></span>  
  
5.  <span data-ttu-id="ddcba-124">Haga doble clic en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="ddcba-124">Double-click the message.</span></span>  
  
6.  <span data-ttu-id="ddcba-125">En el **detalles del servicio** ventana, haga clic en el **mensajes** ficha.</span><span class="sxs-lookup"><span data-stu-id="ddcba-125">In the **Service Details** window, click the **Messages** tab.</span></span>  
  
7.  <span data-ttu-id="ddcba-126">Haga doble clic de nuevo en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="ddcba-126">Double-click the message again.</span></span>  
  
8.  <span data-ttu-id="ddcba-127">En el panel izquierdo, haga clic en **partes de mensaje / cuerpo**.</span><span class="sxs-lookup"><span data-stu-id="ddcba-127">In the left pane, click **Message Parts / Body**.</span></span>  
  
9. <span data-ttu-id="ddcba-128">Determine si la estructura del mensaje es correcta.</span><span class="sxs-lookup"><span data-stu-id="ddcba-128">Determine if the message structure is correct.</span></span>