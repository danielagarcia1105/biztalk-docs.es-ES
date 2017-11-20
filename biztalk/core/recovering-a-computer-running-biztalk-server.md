---
title: Recuperar un equipo que ejecuta BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a55af6d6-f11a-46e4-9b8e-0a1ca35998c4
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74d9234fa1d3a572afadcc8e8ba90dd4735eb5c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="recovering-a-computer-running-biztalk-server"></a><span data-ttu-id="23527-102">Recuperar un equipo que ejecuta BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="23527-102">Recovering a Computer Running BizTalk Server</span></span>
<span data-ttu-id="23527-103">Para recuperar un equipo que ejecuta BizTalk Server, debe tener acceso a las bases de datos de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="23527-103">In order to recover a computer running BizTalk Server, you must be able to access the BizTalk Server databases.</span></span> <span data-ttu-id="23527-104">En caso necesario, restaure las bases de datos de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="23527-104">If necessary, restore the BizTalk Server databases.</span></span> <span data-ttu-id="23527-105">Asimismo, antes de poder recuperar el equipo que ejecuta BizTalk Server, debe volver a instalar BizTalk Server y todos los prerrequisitos.</span><span class="sxs-lookup"><span data-stu-id="23527-105">In addition, before you can recover the computer running BizTalk Server, you must reinstall BizTalk Server and all of the prerequisites.</span></span>  
  
 <span data-ttu-id="23527-106">Cuando se completan estos pasos, puede utilizar los procedimientos que se describen en esta sección para recuperar el servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="23527-106">When these steps are complete, you can use the procedures in this section to recover your BizTalk server.</span></span> <span data-ttu-id="23527-107">Los procedimientos que hay que seguir para recuperar BizTalk Server dependen de la edición que se utiliza.</span><span class="sxs-lookup"><span data-stu-id="23527-107">The procedures you must follow to recover BizTalk Server depend on the edition you are using.</span></span> <span data-ttu-id="23527-108">La tabla siguiente enumera los procedimientos necesarios para esta edición.</span><span class="sxs-lookup"><span data-stu-id="23527-108">The following table lists the required procedures for each edition.</span></span>  
  
|<span data-ttu-id="23527-109">Tarea</span><span class="sxs-lookup"><span data-stu-id="23527-109">Task</span></span>|<span data-ttu-id="23527-110">Standard</span><span class="sxs-lookup"><span data-stu-id="23527-110">Standard</span></span>|<span data-ttu-id="23527-111">Desarrollador</span><span class="sxs-lookup"><span data-stu-id="23527-111">Developer</span></span>|<span data-ttu-id="23527-112">Enterprise</span><span class="sxs-lookup"><span data-stu-id="23527-112">Enterprise</span></span>|  
|----------|--------------|---------------|----------------|  
|<span data-ttu-id="23527-113">**Cómo restaurar el almacén de certificados**</span><span class="sxs-lookup"><span data-stu-id="23527-113">**How to Restore the Certificate Store**</span></span>|<span data-ttu-id="23527-114">**X**</span><span class="sxs-lookup"><span data-stu-id="23527-114">**X**</span></span>|||  
|<span data-ttu-id="23527-115">**Cómo recuperar Enterprise Single Sign-On (SSO)**</span><span class="sxs-lookup"><span data-stu-id="23527-115">**How to Recover Enterprise Single Sign-On (SSO)**</span></span>|<span data-ttu-id="23527-116">**X**</span><span class="sxs-lookup"><span data-stu-id="23527-116">**X**</span></span>|<span data-ttu-id="23527-117">**X**</span><span class="sxs-lookup"><span data-stu-id="23527-117">**X**</span></span>|<span data-ttu-id="23527-118">**X**</span><span class="sxs-lookup"><span data-stu-id="23527-118">**X**</span></span>|  
|<span data-ttu-id="23527-119">**Cómo recuperar el grupo de BizTalk**</span><span class="sxs-lookup"><span data-stu-id="23527-119">**How to Recover the BizTalk Group**</span></span>|<span data-ttu-id="23527-120">**X**</span><span class="sxs-lookup"><span data-stu-id="23527-120">**X**</span></span>|<span data-ttu-id="23527-121">**X**</span><span class="sxs-lookup"><span data-stu-id="23527-121">**X**</span></span>|<span data-ttu-id="23527-122">**X**</span><span class="sxs-lookup"><span data-stu-id="23527-122">**X**</span></span>|  
|<span data-ttu-id="23527-123">**Cómo recuperar la configuración de BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="23527-123">**How to Recover the BizTalk Server Configuration**</span></span>|<span data-ttu-id="23527-124">**X**</span><span class="sxs-lookup"><span data-stu-id="23527-124">**X**</span></span>|<span data-ttu-id="23527-125">**X**</span><span class="sxs-lookup"><span data-stu-id="23527-125">**X**</span></span>|<span data-ttu-id="23527-126">**X**</span><span class="sxs-lookup"><span data-stu-id="23527-126">**X**</span></span>|  
|<span data-ttu-id="23527-127">**Cómo recuperar las alertas de BAM**</span><span class="sxs-lookup"><span data-stu-id="23527-127">**How to Recover BAM Alerts**</span></span><br /><br /> <span data-ttu-id="23527-128">No se requiere a menos que utilice BAM.</span><span class="sxs-lookup"><span data-stu-id="23527-128">Not required unless you're using BAM.</span></span>|<span data-ttu-id="23527-129">**X**</span><span class="sxs-lookup"><span data-stu-id="23527-129">**X**</span></span>|<span data-ttu-id="23527-130">**X**</span><span class="sxs-lookup"><span data-stu-id="23527-130">**X**</span></span>|<span data-ttu-id="23527-131">**X**</span><span class="sxs-lookup"><span data-stu-id="23527-131">**X**</span></span>|  
|<span data-ttu-id="23527-132">**Cómo recuperar el Portal de BAM**</span><span class="sxs-lookup"><span data-stu-id="23527-132">**How to Recover the BAM Portal**</span></span><br /><br /> <span data-ttu-id="23527-133">No se requiere a menos que utilice BAM.</span><span class="sxs-lookup"><span data-stu-id="23527-133">Not required unless you're using BAM.</span></span>|<span data-ttu-id="23527-134">**X**</span><span class="sxs-lookup"><span data-stu-id="23527-134">**X**</span></span>|<span data-ttu-id="23527-135">**X**</span><span class="sxs-lookup"><span data-stu-id="23527-135">**X**</span></span>|<span data-ttu-id="23527-136">**X**</span><span class="sxs-lookup"><span data-stu-id="23527-136">**X**</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="23527-137">En esta sección</span><span class="sxs-lookup"><span data-stu-id="23527-137">In This Section</span></span>  
  
-   [<span data-ttu-id="23527-138">Cómo restaurar el almacén de certificados</span><span class="sxs-lookup"><span data-stu-id="23527-138">How to Restore the Certificate Store</span></span>](../core/how-to-restore-the-certificate-store.md)  
  
-   [<span data-ttu-id="23527-139">Cómo recuperar el inicio de sesión único empresarial</span><span class="sxs-lookup"><span data-stu-id="23527-139">How to Recover Enterprise Single Sign-On</span></span>](../core/how-to-recover-enterprise-single-sign-on.md)  
  
-   [<span data-ttu-id="23527-140">Cómo recuperar el grupo de BizTalk</span><span class="sxs-lookup"><span data-stu-id="23527-140">How to Recover the BizTalk Group</span></span>](../core/how-to-recover-the-biztalk-group.md)  
  
-   [<span data-ttu-id="23527-141">Cómo recuperar la configuración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="23527-141">How to Recover the BizTalk Server Configuration</span></span>](../core/how-to-recover-the-biztalk-server-configuration.md)  
  
-   [<span data-ttu-id="23527-142">Cómo recuperar las alertas de BAM</span><span class="sxs-lookup"><span data-stu-id="23527-142">How to Recover BAM Alerts</span></span>](../core/how-to-recover-bam-alerts.md)  
  
-   [<span data-ttu-id="23527-143">Cómo recuperar el Portal de BAM</span><span class="sxs-lookup"><span data-stu-id="23527-143">How to Recover the BAM Portal</span></span>](../core/how-to-recover-the-bam-portal.md)