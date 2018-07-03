---
title: Crear error en el comando ubicaciones de recepción | Microsoft Docs
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
ms.openlocfilehash: 95b50fcb051b77b4d6516145a2c7fabfc52c2e7f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976253"
---
# <a name="create-receive-locations-command-failed"></a><span data-ttu-id="1bc22-102">Error en el comando de creación de ubicaciones de recepción</span><span class="sxs-lookup"><span data-stu-id="1bc22-102">Create receive locations command failed</span></span>
## <a name="details"></a><span data-ttu-id="1bc22-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="1bc22-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="1bc22-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="1bc22-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="1bc22-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="1bc22-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="1bc22-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="1bc22-106">Event ID</span></span>     |                                         <span data-ttu-id="1bc22-107">0</span><span class="sxs-lookup"><span data-stu-id="1bc22-107">0</span></span>                                          |
|  <span data-ttu-id="1bc22-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="1bc22-108">Event Source</span></span>   |                                         <span data-ttu-id="1bc22-109">0</span><span class="sxs-lookup"><span data-stu-id="1bc22-109">0</span></span>                                          |
|    <span data-ttu-id="1bc22-110">Componente</span><span class="sxs-lookup"><span data-stu-id="1bc22-110">Component</span></span>    |                                         <span data-ttu-id="1bc22-111">0</span><span class="sxs-lookup"><span data-stu-id="1bc22-111">0</span></span>                                          |
|  <span data-ttu-id="1bc22-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="1bc22-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="1bc22-113">0</span><span class="sxs-lookup"><span data-stu-id="1bc22-113">0</span></span>                                          |
|  <span data-ttu-id="1bc22-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="1bc22-114">Message Text</span></span>   |  <span data-ttu-id="1bc22-115">Crear error en el comando ubicaciones de recepción: FileName ={0} argumentos ={1} ExitCode ={2}</span><span class="sxs-lookup"><span data-stu-id="1bc22-115">Create receive locations command failed: FileName={0} Arguments={1} ExitCode={2}</span></span>  |
  
## <a name="explanation"></a><span data-ttu-id="1bc22-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="1bc22-116">Explanation</span></span>  
 <span data-ttu-id="1bc22-117">El Asistente para publicación no pudo crear una ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="1bc22-117">The publishing wizard failed to create a receive location.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1bc22-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="1bc22-118">User Action</span></span>  
 <span data-ttu-id="1bc22-119">Para resolver este error, haga lo siguiente: en la consola de administración de BizTalk, asegúrese de que la ubicación de recepción especificado por el atributo receiveLocationName en el archivo Web.config que el Asistente de publicación de WCF de BizTalk genera existe y se ha iniciado.</span><span class="sxs-lookup"><span data-stu-id="1bc22-119">To resolve this error, do the following: In the BizTalk Administration console, make sure that the receive location specified by the receiveLocationName attribute in the Web.config file that the BizTalk WCF Publishing Wizard generated exists and is started.</span></span>  
  
 <span data-ttu-id="1bc22-120">Para obtener más información sobre la creación de ubicaciones de recepción, vea los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="1bc22-120">For additional information on creating receive locations, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="1bc22-121">Publicación de servicios WCF con los adaptadores de recepción WCF aislados</span><span class="sxs-lookup"><span data-stu-id="1bc22-121">Publishing WCF Services with the Isolated WCF Receive Adapters</span></span>](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="1bc22-122">Cómo configurar ubicación de recepción de un WCF-BasicHttp</span><span class="sxs-lookup"><span data-stu-id="1bc22-122">How to Configure a WCF-BasicHttp Receive Location</span></span>](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [<span data-ttu-id="1bc22-123">Cómo configurar ubicación de recepción de un WCF-WSHttp</span><span class="sxs-lookup"><span data-stu-id="1bc22-123">How to Configure a WCF-WSHttp Receive Location</span></span>](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [<span data-ttu-id="1bc22-124">Cómo configurar ubicación de recepción de un WCF-CustomIsolated</span><span class="sxs-lookup"><span data-stu-id="1bc22-124">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="1bc22-125">Tutorial: Publicación de servicios WCF con el adaptador WCF-BasicHttp</span><span class="sxs-lookup"><span data-stu-id="1bc22-125">Walkthrough: Publishing WCF Services with the WCF-BasicHttp Adapter</span></span>](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)