---
title: Ubicación de recepción para que no se encontraron metadatos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c397fb5-f400-4cff-85b9-5bf0d2069557
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4ae137cc48d5df142c2917b0d40fd2bc95e36dd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011597"
---
# <a name="receive-location-for-metadata-not-found"></a><span data-ttu-id="cea51-102">No se encontró la ubicación de recepción para los metadatos</span><span class="sxs-lookup"><span data-stu-id="cea51-102">Receive location for metadata not found</span></span>
## <a name="details"></a><span data-ttu-id="cea51-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="cea51-103">Details</span></span>  
  
|                 |                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="cea51-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="cea51-104">Product Name</span></span>   |                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                           |
| <span data-ttu-id="cea51-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="cea51-105">Product Version</span></span> |                                      [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                       |
|    <span data-ttu-id="cea51-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="cea51-106">Event ID</span></span>     |                                                                   <span data-ttu-id="cea51-107">0</span><span class="sxs-lookup"><span data-stu-id="cea51-107">0</span></span>                                                                   |
|  <span data-ttu-id="cea51-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="cea51-108">Event Source</span></span>   |                                                                   <span data-ttu-id="cea51-109">0</span><span class="sxs-lookup"><span data-stu-id="cea51-109">0</span></span>                                                                   |
|    <span data-ttu-id="cea51-110">Componente</span><span class="sxs-lookup"><span data-stu-id="cea51-110">Component</span></span>    |                                                                   <span data-ttu-id="cea51-111">0</span><span class="sxs-lookup"><span data-stu-id="cea51-111">0</span></span>                                                                   |
|  <span data-ttu-id="cea51-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="cea51-112">Symbolic Name</span></span>  |                                                                   <span data-ttu-id="cea51-113">0</span><span class="sxs-lookup"><span data-stu-id="cea51-113">0</span></span>                                                                   |
|  <span data-ttu-id="cea51-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="cea51-114">Message Text</span></span>   | <span data-ttu-id="cea51-115">Ubicación de recepción "{0}" para no se encontraron metadatos.</span><span class="sxs-lookup"><span data-stu-id="cea51-115">Receive location "{0}" for metadata not found.</span></span> <span data-ttu-id="cea51-116">(Compruebe la asignación de la ubicación de recepción en Web.config y asegúrese de que la ubicación de recepción existe.)</span><span class="sxs-lookup"><span data-stu-id="cea51-116">(Check receive location mapping in Web.config and verify the receive location exists.)</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="cea51-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="cea51-117">Explanation</span></span>  
 <span data-ttu-id="cea51-118">Este error indica que una ubicación de recepción WCF aislada publicada no encontró la ubicación de recepción correspondiente para metadatos.</span><span class="sxs-lookup"><span data-stu-id="cea51-118">This error indicates that a published isolated WCF receive location could not find the corresponding receive location for metadata.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cea51-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="cea51-119">User Action</span></span>  
 <span data-ttu-id="cea51-120">Para resolver este error, haga lo siguiente: en la consola de administración de BizTalk, asegúrese de que la ubicación de recepción especificado por el atributo receiveLocationName en el archivo Web.config que el Asistente de publicación de WCF de BizTalk genera existe y se ha iniciado.</span><span class="sxs-lookup"><span data-stu-id="cea51-120">To resolve this error, do the following: In the BizTalk Administration console, make sure that the receive location specified by the receiveLocationName attribute in the Web.config file that the BizTalk WCF Publishing Wizard generated exists and is started.</span></span>  
  
 <span data-ttu-id="cea51-121">Para obtener más información sobre las ubicaciones de recepción, vea los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="cea51-121">For additional information on receive locations, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="cea51-122">Publicación de servicios WCF</span><span class="sxs-lookup"><span data-stu-id="cea51-122">Publishing WCF Services</span></span>](../core/publishing-wcf-services.md)  
  
-   [<span data-ttu-id="cea51-123">Cómo configurar ubicación de recepción de un WCF-BasicHttp</span><span class="sxs-lookup"><span data-stu-id="cea51-123">How to Configure a WCF-BasicHttp Receive Location</span></span>](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [<span data-ttu-id="cea51-124">Cómo configurar ubicación de recepción de un WCF-WSHttp</span><span class="sxs-lookup"><span data-stu-id="cea51-124">How to Configure a WCF-WSHttp Receive Location</span></span>](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [<span data-ttu-id="cea51-125">Cómo configurar ubicación de recepción de un WCF-CustomIsolated</span><span class="sxs-lookup"><span data-stu-id="cea51-125">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="cea51-126">Tutorial: Publicación de servicios WCF con el adaptador WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="cea51-126">Walkthrough: Publishing WCF Services with the WCF-NetMsmq Adapter</span></span>](../core/walkthrough-publishing-wcf-services-with-the-wcf-netmsmq-adapter.md)