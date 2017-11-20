---
title: "Administración-ExplorerOM (carpeta de ejemplos de BizTalk Server) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, administering
- administering, examples
ms.assetid: f6553138-9ab3-4368-84bf-9813e909e372
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b8b33db0460a5e44ecfcd732535022bb28940d3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="admin-explorerom-biztalk-server-samples-folder"></a><span data-ttu-id="765ee-102">Administración-ExplorerOM (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="765ee-102">Admin-ExplorerOM (BizTalk Server Samples Folder)</span></span>
<span data-ttu-id="765ee-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] incluye varios ejemplos en la carpeta Admin\ExplorerOM en su kit de desarrollo de software (SDK).</span><span class="sxs-lookup"><span data-stu-id="765ee-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] includes samples in the Admin\ExplorerOM folder in its software development kit (SDK).</span></span> <span data-ttu-id="765ee-104">En esta sección se proporciona información detallada acerca de la funcionalidad que muestra cada ejemplo de administración del modelo de objetos del Explorador de BizTalk, instrucciones para la generación y ejecución del ejemplo, así como los resultados que se pueden esperar.</span><span class="sxs-lookup"><span data-stu-id="765ee-104">This section provides detailed information about the functionality demonstrated by each BizTalk Explorer object model administration sample, instructions for building and running the sample, and the results you can expect.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="765ee-105">Las secuencias de comandos de implementación se deben quitar después de la implementación si no son necesarias.</span><span class="sxs-lookup"><span data-stu-id="765ee-105">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="765ee-106">La lista de control de acceso (ACL) debe proteger y supervisar detalladamente las secuencias de comandos de administración y otras secuencias de comandos que deben permanecer.</span><span class="sxs-lookup"><span data-stu-id="765ee-106">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="765ee-107">Microsoft.BizTalk.ExplorerOM.dll es compatible con procesos de 32 bits y de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="765ee-107">Microsoft.BizTalk.ExplorerOM.dll supports both 32 bit and 64 bit processes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="765ee-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="765ee-108">In This Section</span></span>  
  
-   <span data-ttu-id="765ee-109">[ApplicationManager (ejemplo de BizTalk Server)](../core/applicationmanager-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="765ee-109">[ApplicationManager (BizTalk Server Sample)](../core/applicationmanager-biztalk-server-sample.md).</span></span> <span data-ttu-id="765ee-110">Muestra cómo iniciar o detener una aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="765ee-110">Demonstrates how to start or stop a BizTalk application.</span></span>  
  
-   <span data-ttu-id="765ee-111">[BrowsingArtifacts (ejemplo de BizTalk Server)](../core/browsingartifacts-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="765ee-111">[BrowsingArtifacts (BizTalk Server Sample)](../core/browsingartifacts-biztalk-server-sample.md).</span></span> <span data-ttu-id="765ee-112">Muestra cómo enumerar los artefactos y los atributos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="765ee-112">Demonstrates how to enumerate BizTalk artifacts and attributes.</span></span>  
  
-   <span data-ttu-id="765ee-113">[CBR (ejemplo de BizTalk Server)](../core/cbr-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="765ee-113">[CBR (BizTalk Server Sample)](../core/cbr-biztalk-server-sample.md).</span></span> <span data-ttu-id="765ee-114">Muestra cómo agregar y configurar nuevos puertos de envío para el enrutamiento basado en contenido de los mensajes de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="765ee-114">Demonstrates adding and configuring new send ports for content based routing of BizTalk messages.</span></span>  
  
-   <span data-ttu-id="765ee-115">[DeleteParty (ejemplo de BizTalk Server)](../core/deleteparty-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="765ee-115">[DeleteParty (BizTalk Server Sample)](../core/deleteparty-biztalk-server-sample.md).</span></span> <span data-ttu-id="765ee-116">Muestra cómo eliminar una entidad especificada.</span><span class="sxs-lookup"><span data-stu-id="765ee-116">Demonstrates how to delete a specified party.</span></span>  
  
-   <span data-ttu-id="765ee-117">[OrchestrationBinding (ejemplo de BizTalk Server)](../core/orchestrationbinding-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="765ee-117">[OrchestrationBinding (BizTalk Server Sample)](../core/orchestrationbinding-biztalk-server-sample.md).</span></span> <span data-ttu-id="765ee-118">Muestra la configuración y administración de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="765ee-118">Demonstrates configuring and managing orchestrations.</span></span>  
  
-   <span data-ttu-id="765ee-119">[PartnerManagement (ejemplo de BizTalk Server)](../core/partnermanagement-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="765ee-119">[PartnerManagement (BizTalk Server Sample)](../core/partnermanagement-biztalk-server-sample.md).</span></span> <span data-ttu-id="765ee-120">Muestra cómo crear y eliminar entidades.</span><span class="sxs-lookup"><span data-stu-id="765ee-120">Demonstrates creating and deleting parties.</span></span> <span data-ttu-id="765ee-121">También muestra cómo dar de alta y de baja las entidades con funciones.</span><span class="sxs-lookup"><span data-stu-id="765ee-121">Also demonstrates enlisting and un-enlisting parties with roles.</span></span>  
  
-   <span data-ttu-id="765ee-122">[ReceiveLocations (ejemplo de BizTalk Server)](../core/receivelocations-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="765ee-122">[ReceiveLocations (BizTalk Server Sample)](../core/receivelocations-biztalk-server-sample.md).</span></span> <span data-ttu-id="765ee-123">Muestra cómo crear y administrar ubicaciones de recepción para puertos de recepción.</span><span class="sxs-lookup"><span data-stu-id="765ee-123">Demonstrates how to create and manage receive locations for receive ports.</span></span>  
  
-   <span data-ttu-id="765ee-124">[ReceivePorts (ejemplo de BizTalk Server)](../core/receiveports-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="765ee-124">[ReceivePorts (BizTalk Server Sample)](../core/receiveports-biztalk-server-sample.md).</span></span> <span data-ttu-id="765ee-125">Muestra cómo crear, enumerar y eliminar puertos de recepción.</span><span class="sxs-lookup"><span data-stu-id="765ee-125">Demonstrates creating, enumerating and deleting receive ports.</span></span>  
  
-   <span data-ttu-id="765ee-126">[SendPortGroups (ejemplo de BizTalk Server)](../core/sendportgroups-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="765ee-126">[SendPortGroups (BizTalk Server Sample)](../core/sendportgroups-biztalk-server-sample.md).</span></span> <span data-ttu-id="765ee-127">Muestra cómo enumerar y administrar grupos de puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="765ee-127">Demonstrates how to enumerate and manage send port groups.</span></span>  
  
-   <span data-ttu-id="765ee-128">[PuertosEnvío (ejemplo de BizTalk Server)](../core/sendports-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="765ee-128">[SendPorts (BizTalk Server Sample)](../core/sendports-biztalk-server-sample.md).</span></span> <span data-ttu-id="765ee-129">Muestra cómo enumerar y administrar puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="765ee-129">Demonstrates how to enumerate and manage send ports.</span></span>  
  
-   <span data-ttu-id="765ee-130">[UnenlistParties (ejemplo de BizTalk Server)](../core/unenlistparties-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="765ee-130">[UnenlistParties (BizTalk Server Sample)](../core/unenlistparties-biztalk-server-sample.md).</span></span> <span data-ttu-id="765ee-131">Muestra cómo dar de baja todas las entidades asociadas a un ensamblado de BizTalk implementado.</span><span class="sxs-lookup"><span data-stu-id="765ee-131">Demonstrates how to unenlist all of the parties associated with a deployed BizTalk assembly.</span></span>