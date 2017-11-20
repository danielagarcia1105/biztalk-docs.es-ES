---
title: "Ubicación de recepción para que no se encontraron metadatos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3c397fb5-f400-4cff-85b9-5bf0d2069557
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3eb45272f7d3ef4491b59d5b019eb4499bcf5dff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receive-location-for-metadata-not-found"></a><span data-ttu-id="30e23-102">No se encontró la ubicación de recepción para los metadatos</span><span class="sxs-lookup"><span data-stu-id="30e23-102">Receive location for metadata not found</span></span>
## <a name="details"></a><span data-ttu-id="30e23-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="30e23-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="30e23-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="30e23-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="30e23-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="30e23-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="30e23-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="30e23-106">Event ID</span></span>|<span data-ttu-id="30e23-107">0</span><span class="sxs-lookup"><span data-stu-id="30e23-107">0</span></span>|  
|<span data-ttu-id="30e23-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="30e23-108">Event Source</span></span>|<span data-ttu-id="30e23-109">0</span><span class="sxs-lookup"><span data-stu-id="30e23-109">0</span></span>|  
|<span data-ttu-id="30e23-110">Componente</span><span class="sxs-lookup"><span data-stu-id="30e23-110">Component</span></span>|<span data-ttu-id="30e23-111">0</span><span class="sxs-lookup"><span data-stu-id="30e23-111">0</span></span>|  
|<span data-ttu-id="30e23-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="30e23-112">Symbolic Name</span></span>|<span data-ttu-id="30e23-113">0</span><span class="sxs-lookup"><span data-stu-id="30e23-113">0</span></span>|  
|<span data-ttu-id="30e23-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="30e23-114">Message Text</span></span>|<span data-ttu-id="30e23-115">No se encontró la ubicación de recepción "{0}" para los metadatos.</span><span class="sxs-lookup"><span data-stu-id="30e23-115">Receive location "{0}" for metadata not found.</span></span> <span data-ttu-id="30e23-116">(Compruebe la asignación de la ubicación de recepción en Web.config y asegúrese de que la ubicación de recepción existe.)</span><span class="sxs-lookup"><span data-stu-id="30e23-116">(Check receive location mapping in Web.config and verify the receive location exists.)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="30e23-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="30e23-117">Explanation</span></span>  
 <span data-ttu-id="30e23-118">Este error indica que una ubicación de recepción WCF aislada publicada no encontró la ubicación de recepción correspondiente para metadatos.</span><span class="sxs-lookup"><span data-stu-id="30e23-118">This error indicates that a published isolated WCF receive location could not find the corresponding receive location for metadata.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="30e23-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="30e23-119">User Action</span></span>  
 <span data-ttu-id="30e23-120">Para resolver este error, realice lo siguiente: en la consola de administración de BizTalk, asegúrese de que la ubicación de recepción especificada por el atributo receiveLocationName en el archivo Web.config que el Asistente de publicación de WCF de BizTalk genera existe y se ha iniciado.</span><span class="sxs-lookup"><span data-stu-id="30e23-120">To resolve this error, do the following: In the BizTalk Administration console, make sure that the receive location specified by the receiveLocationName attribute in the Web.config file that the BizTalk WCF Publishing Wizard generated exists and is started.</span></span>  
  
 <span data-ttu-id="30e23-121">Para obtener más información sobre las ubicaciones de recepción, vea los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="30e23-121">For additional information on receive locations, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="30e23-122">Publicar servicios WCF</span><span class="sxs-lookup"><span data-stu-id="30e23-122">Publishing WCF Services</span></span>](../core/publishing-wcf-services.md)  
  
-   [<span data-ttu-id="30e23-123">Cómo configurar un WCF-BasicHttp ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="30e23-123">How to Configure a WCF-BasicHttp Receive Location</span></span>](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [<span data-ttu-id="30e23-124">Cómo configurar un WCF-WSHttp ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="30e23-124">How to Configure a WCF-WSHttp Receive Location</span></span>](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [<span data-ttu-id="30e23-125">Cómo configurar un WCF-CustomIsolated ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="30e23-125">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="30e23-126">Tutorial: Publicar servicios WCF con el adaptador WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="30e23-126">Walkthrough: Publishing WCF Services with the WCF-NetMsmq Adapter</span></span>](../core/walkthrough-publishing-wcf-services-with-the-wcf-netmsmq-adapter.md)