---
title: No se pudo registrar el receptor aislado de dirección | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 313b436a-d7c5-4b46-bfe3-bbad0d8efe42
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e33aa3e48cd92b3d190289c1d65bf3a3bb7c7907
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986621"
---
# <a name="failed-to-register-isolated-receiver-for-address"></a><span data-ttu-id="47d1d-102">No se pudo registrar el receptor aislado de la dirección</span><span class="sxs-lookup"><span data-stu-id="47d1d-102">Failed to register isolated receiver for address</span></span>
## <a name="details"></a><span data-ttu-id="47d1d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="47d1d-103">Details</span></span>  
  
|                 |                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="47d1d-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="47d1d-104">Product Name</span></span>   |           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]            |
| <span data-ttu-id="47d1d-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="47d1d-105">Product Version</span></span> |                       [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                        |
|    <span data-ttu-id="47d1d-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="47d1d-106">Event ID</span></span>     |                                                    <span data-ttu-id="47d1d-107">0</span><span class="sxs-lookup"><span data-stu-id="47d1d-107">0</span></span>                                                    |
|  <span data-ttu-id="47d1d-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="47d1d-108">Event Source</span></span>   |                                                    <span data-ttu-id="47d1d-109">0</span><span class="sxs-lookup"><span data-stu-id="47d1d-109">0</span></span>                                                    |
|    <span data-ttu-id="47d1d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="47d1d-110">Component</span></span>    |                                                    <span data-ttu-id="47d1d-111">0</span><span class="sxs-lookup"><span data-stu-id="47d1d-111">0</span></span>                                                    |
|  <span data-ttu-id="47d1d-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="47d1d-112">Symbolic Name</span></span>  |                                                    <span data-ttu-id="47d1d-113">0</span><span class="sxs-lookup"><span data-stu-id="47d1d-113">0</span></span>                                                    |
|  <span data-ttu-id="47d1d-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="47d1d-114">Message Text</span></span>   | <span data-ttu-id="47d1d-115">No se pudo registrar el receptor aislado de la dirección "{0}"; ubicación de recepción no existe o está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="47d1d-115">Failed to register isolated receiver for address "{0}"; receive location does not exist or is disabled.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="47d1d-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="47d1d-116">Explanation</span></span>  
 <span data-ttu-id="47d1d-117">Este error indica que una ubicación de recepción WCF aislada publicada no encontró la ubicación de recepción correspondiente.</span><span class="sxs-lookup"><span data-stu-id="47d1d-117">This error indicates that a published isolated WCF receive location could not find the corresponding receive location.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="47d1d-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="47d1d-118">User Action</span></span>  
 <span data-ttu-id="47d1d-119">Para resolver este error, haga lo siguiente: en la consola de administración de BizTalk, asegúrese de que la ubicación de recepción especificado por el atributo receiveLocationName en el archivo Web.config que el Asistente WCF de BizTalk Services publicación genera existe y es se inició.</span><span class="sxs-lookup"><span data-stu-id="47d1d-119">To resolve this error, do the following: In the BizTalk Administration console, make sure that the receive location specified by the receiveLocationName attribute in the Web.config file that the BizTalk WCF Services Publishing Wizard generated exists and is started.</span></span>  
  
 <span data-ttu-id="47d1d-120">Para obtener más información sobre la creación de ubicaciones de recepción, vea los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="47d1d-120">For additional information on creating receive locations, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="47d1d-121">Publicación de servicios WCF con los adaptadores de recepción WCF aislados</span><span class="sxs-lookup"><span data-stu-id="47d1d-121">Publishing WCF Services with the Isolated WCF Receive Adapters</span></span>](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="47d1d-122">Cómo configurar ubicación de recepción de un WCF-BasicHttp</span><span class="sxs-lookup"><span data-stu-id="47d1d-122">How to Configure a WCF-BasicHttp Receive Location</span></span>](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [<span data-ttu-id="47d1d-123">Cómo configurar ubicación de recepción de un WCF-WSHttp</span><span class="sxs-lookup"><span data-stu-id="47d1d-123">How to Configure a WCF-WSHttp Receive Location</span></span>](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [<span data-ttu-id="47d1d-124">Cómo configurar ubicación de recepción de un WCF-CustomIsolated</span><span class="sxs-lookup"><span data-stu-id="47d1d-124">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="47d1d-125">Tutorial: Publicación de servicios WCF con el adaptador WCF-BasicHttp</span><span class="sxs-lookup"><span data-stu-id="47d1d-125">Walkthrough: Publishing WCF Services with the WCF-BasicHttp Adapter</span></span>](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)