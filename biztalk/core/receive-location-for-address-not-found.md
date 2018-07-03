---
title: Ubicación de recepción para que no se encontró la dirección | Microsoft Docs
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
ms.openlocfilehash: 55b3744f6590ee706bcc3df4124f964306634ca5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994949"
---
# <a name="receive-location-for-address-not-found"></a><span data-ttu-id="67de2-102">No se encontró la ubicación de recepción para la dirección</span><span class="sxs-lookup"><span data-stu-id="67de2-102">Receive location for address not found</span></span>
## <a name="details"></a><span data-ttu-id="67de2-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="67de2-103">Details</span></span>  
  
|                 |                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------|
|  <span data-ttu-id="67de2-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="67de2-104">Product Name</span></span>   |      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]       |
| <span data-ttu-id="67de2-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="67de2-105">Product Version</span></span> |                  [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                   |
|    <span data-ttu-id="67de2-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="67de2-106">Event ID</span></span>     |                                               <span data-ttu-id="67de2-107">0</span><span class="sxs-lookup"><span data-stu-id="67de2-107">0</span></span>                                               |
|  <span data-ttu-id="67de2-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="67de2-108">Event Source</span></span>   |                                               <span data-ttu-id="67de2-109">0</span><span class="sxs-lookup"><span data-stu-id="67de2-109">0</span></span>                                               |
|    <span data-ttu-id="67de2-110">Componente</span><span class="sxs-lookup"><span data-stu-id="67de2-110">Component</span></span>    |                                               <span data-ttu-id="67de2-111">0</span><span class="sxs-lookup"><span data-stu-id="67de2-111">0</span></span>                                               |
|  <span data-ttu-id="67de2-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="67de2-112">Symbolic Name</span></span>  |                                               <span data-ttu-id="67de2-113">0</span><span class="sxs-lookup"><span data-stu-id="67de2-113">0</span></span>                                               |
|  <span data-ttu-id="67de2-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="67de2-114">Message Text</span></span>   | <span data-ttu-id="67de2-115">Ubicación de recepción para la dirección "{0}" no se encuentra.</span><span class="sxs-lookup"><span data-stu-id="67de2-115">Receive location for address "{0}" not found.</span></span> <span data-ttu-id="67de2-116">(La ubicación de recepción de BizTalk puede estar deshabilitada.)</span><span class="sxs-lookup"><span data-stu-id="67de2-116">(The BizTalk receive location may be disabled.)</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="67de2-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="67de2-117">Explanation</span></span>  
 <span data-ttu-id="67de2-118">Este error indica que una ubicación de recepción WCF aislada publicada no encontró la ubicación de recepción correspondiente.</span><span class="sxs-lookup"><span data-stu-id="67de2-118">This error indicates that a published isolated WCF receive location could not find the corresponding receive location.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="67de2-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="67de2-119">User Action</span></span>  
 <span data-ttu-id="67de2-120">Para resolver este error, haga lo siguiente: en la consola de administración de BizTalk, asegúrese de que la ubicación de recepción especificado por el atributo receiveLocationName en el archivo Web.config que el Asistente de publicación de WCF de BizTalk genera existe y se ha iniciado.</span><span class="sxs-lookup"><span data-stu-id="67de2-120">To resolve this error, do the following: In the BizTalk Administration console, make sure that the receive location specified by the receiveLocationName attribute in the Web.config file that the BizTalk WCF Publishing Wizard generated exists and is started.</span></span>  
  
 <span data-ttu-id="67de2-121">Para obtener más información sobre la creación de ubicaciones de recepción, vea los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="67de2-121">For additional information on creating receive locations, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="67de2-122">Publicación de servicios WCF con los adaptadores de recepción WCF aislados</span><span class="sxs-lookup"><span data-stu-id="67de2-122">Publishing WCF Services with the Isolated WCF Receive Adapters</span></span>](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="67de2-123">Cómo configurar ubicación de recepción de un WCF-BasicHttp</span><span class="sxs-lookup"><span data-stu-id="67de2-123">How to Configure a WCF-BasicHttp Receive Location</span></span>](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [<span data-ttu-id="67de2-124">Cómo configurar ubicación de recepción de un WCF-WSHttp</span><span class="sxs-lookup"><span data-stu-id="67de2-124">How to Configure a WCF-WSHttp Receive Location</span></span>](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [<span data-ttu-id="67de2-125">Cómo configurar ubicación de recepción de un WCF-CustomIsolated</span><span class="sxs-lookup"><span data-stu-id="67de2-125">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="67de2-126">Tutorial: Publicación de servicios WCF con el adaptador WCF-BasicHttp</span><span class="sxs-lookup"><span data-stu-id="67de2-126">Walkthrough: Publishing WCF Services with the WCF-BasicHttp Adapter</span></span>](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)