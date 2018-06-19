---
title: Crear error del comando de ubicaciones de recepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f73ff211-af7f-40be-ad7e-7bde7bf75a2d
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a6ad1c7992bb696eb05223e9830a7114d8a0fd5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238036"
---
# <a name="create-receive-locations-command-failed"></a><span data-ttu-id="d76e5-102">Error en el comando de creación de ubicaciones de recepción</span><span class="sxs-lookup"><span data-stu-id="d76e5-102">Create receive locations command failed</span></span>
## <a name="details"></a><span data-ttu-id="d76e5-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="d76e5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d76e5-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="d76e5-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="d76e5-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="d76e5-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="d76e5-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="d76e5-106">Event ID</span></span>|<span data-ttu-id="d76e5-107">0</span><span class="sxs-lookup"><span data-stu-id="d76e5-107">0</span></span>|  
|<span data-ttu-id="d76e5-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="d76e5-108">Event Source</span></span>|<span data-ttu-id="d76e5-109">0</span><span class="sxs-lookup"><span data-stu-id="d76e5-109">0</span></span>|  
|<span data-ttu-id="d76e5-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d76e5-110">Component</span></span>|<span data-ttu-id="d76e5-111">0</span><span class="sxs-lookup"><span data-stu-id="d76e5-111">0</span></span>|  
|<span data-ttu-id="d76e5-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d76e5-112">Symbolic Name</span></span>|<span data-ttu-id="d76e5-113">0</span><span class="sxs-lookup"><span data-stu-id="d76e5-113">0</span></span>|  
|<span data-ttu-id="d76e5-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d76e5-114">Message Text</span></span>|<span data-ttu-id="d76e5-115">Crear error del comando de ubicaciones de recepción: FileName = {0} argumentos = \ {1\\} ExitCode = \ {2\}</span><span class="sxs-lookup"><span data-stu-id="d76e5-115">Create receive locations command failed: FileName={0} Arguments={1} ExitCode={2}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d76e5-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="d76e5-116">Explanation</span></span>  
 <span data-ttu-id="d76e5-117">El Asistente para publicación no pudo crear una ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="d76e5-117">The publishing wizard failed to create a receive location.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d76e5-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d76e5-118">User Action</span></span>  
 <span data-ttu-id="d76e5-119">Para resolver este error, realice lo siguiente: en la consola de administración de BizTalk, asegúrese de que la ubicación de recepción especificada por el atributo receiveLocationName en el archivo Web.config que el Asistente de publicación de WCF de BizTalk genera existe y se ha iniciado.</span><span class="sxs-lookup"><span data-stu-id="d76e5-119">To resolve this error, do the following: In the BizTalk Administration console, make sure that the receive location specified by the receiveLocationName attribute in the Web.config file that the BizTalk WCF Publishing Wizard generated exists and is started.</span></span>  
  
 <span data-ttu-id="d76e5-120">Para obtener más información sobre la creación de ubicaciones de recepción, vea los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="d76e5-120">For additional information on creating receive locations, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="d76e5-121">Publicar servicios WCF con WCF aislado adaptadores de recepción</span><span class="sxs-lookup"><span data-stu-id="d76e5-121">Publishing WCF Services with the Isolated WCF Receive Adapters</span></span>](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="d76e5-122">Cómo configurar un WCF-BasicHttp ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="d76e5-122">How to Configure a WCF-BasicHttp Receive Location</span></span>](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [<span data-ttu-id="d76e5-123">Cómo configurar un WCF-WSHttp ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="d76e5-123">How to Configure a WCF-WSHttp Receive Location</span></span>](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [<span data-ttu-id="d76e5-124">Cómo configurar un WCF-CustomIsolated ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="d76e5-124">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="d76e5-125">Tutorial: Publicar servicios WCF con el adaptador WCF-BasicHttp</span><span class="sxs-lookup"><span data-stu-id="d76e5-125">Walkthrough: Publishing WCF Services with the WCF-BasicHttp Adapter</span></span>](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)