---
title: Ubicación de recepción para que no se encontró una dirección | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 637f3925-06ff-47b2-99db-f85e829ee318
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1242ffc77976fb2ffcc469752d13a6f6366d7a1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268772"
---
# <a name="receive-location-for-address-not-found"></a><span data-ttu-id="79a43-102">No se encontró la ubicación de recepción para la dirección</span><span class="sxs-lookup"><span data-stu-id="79a43-102">Receive location for address not found</span></span>
## <a name="details"></a><span data-ttu-id="79a43-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="79a43-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="79a43-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="79a43-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="79a43-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="79a43-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="79a43-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="79a43-106">Event ID</span></span>|<span data-ttu-id="79a43-107">0</span><span class="sxs-lookup"><span data-stu-id="79a43-107">0</span></span>|  
|<span data-ttu-id="79a43-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="79a43-108">Event Source</span></span>|<span data-ttu-id="79a43-109">0</span><span class="sxs-lookup"><span data-stu-id="79a43-109">0</span></span>|  
|<span data-ttu-id="79a43-110">Componente</span><span class="sxs-lookup"><span data-stu-id="79a43-110">Component</span></span>|<span data-ttu-id="79a43-111">0</span><span class="sxs-lookup"><span data-stu-id="79a43-111">0</span></span>|  
|<span data-ttu-id="79a43-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="79a43-112">Symbolic Name</span></span>|<span data-ttu-id="79a43-113">0</span><span class="sxs-lookup"><span data-stu-id="79a43-113">0</span></span>|  
|<span data-ttu-id="79a43-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="79a43-114">Message Text</span></span>|<span data-ttu-id="79a43-115">No se encontró la ubicación de recepción de dirección "{0}".</span><span class="sxs-lookup"><span data-stu-id="79a43-115">Receive location for address "{0}" not found.</span></span> <span data-ttu-id="79a43-116">(La ubicación de recepción de BizTalk puede estar deshabilitada.)</span><span class="sxs-lookup"><span data-stu-id="79a43-116">(The BizTalk receive location may be disabled.)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="79a43-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="79a43-117">Explanation</span></span>  
 <span data-ttu-id="79a43-118">Este error indica que una ubicación de recepción WCF aislada publicada no encontró la ubicación de recepción correspondiente.</span><span class="sxs-lookup"><span data-stu-id="79a43-118">This error indicates that a published isolated WCF receive location could not find the corresponding receive location.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="79a43-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="79a43-119">User Action</span></span>  
 <span data-ttu-id="79a43-120">Para resolver este error, realice lo siguiente: en la consola de administración de BizTalk, asegúrese de que la ubicación de recepción especificada por el atributo receiveLocationName en el archivo Web.config que el Asistente de publicación de WCF de BizTalk genera existe y se ha iniciado.</span><span class="sxs-lookup"><span data-stu-id="79a43-120">To resolve this error, do the following: In the BizTalk Administration console, make sure that the receive location specified by the receiveLocationName attribute in the Web.config file that the BizTalk WCF Publishing Wizard generated exists and is started.</span></span>  
  
 <span data-ttu-id="79a43-121">Para obtener más información sobre la creación de ubicaciones de recepción, vea los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="79a43-121">For additional information on creating receive locations, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="79a43-122">Publicar servicios WCF con WCF aislado adaptadores de recepción</span><span class="sxs-lookup"><span data-stu-id="79a43-122">Publishing WCF Services with the Isolated WCF Receive Adapters</span></span>](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="79a43-123">Cómo configurar un WCF-BasicHttp ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="79a43-123">How to Configure a WCF-BasicHttp Receive Location</span></span>](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [<span data-ttu-id="79a43-124">Cómo configurar un WCF-WSHttp ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="79a43-124">How to Configure a WCF-WSHttp Receive Location</span></span>](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [<span data-ttu-id="79a43-125">Cómo configurar un WCF-CustomIsolated ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="79a43-125">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="79a43-126">Tutorial: Publicar servicios WCF con el adaptador WCF-BasicHttp</span><span class="sxs-lookup"><span data-stu-id="79a43-126">Walkthrough: Publishing WCF Services with the WCF-BasicHttp Adapter</span></span>](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)