---
title: Creación de instancias de servicio de Bus de eventos BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 454bdde7-45a6-41ab-9196-f662273f0f2b
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: daf847afc8f5c1d284a8266d70006a0f43508ed9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984005"
---
# <a name="creating-instances-of-the-bam-event-bus-service"></a><span data-ttu-id="738ad-102">Creación de instancias de servicio de Bus de eventos BAM</span><span class="sxs-lookup"><span data-stu-id="738ad-102">Creating Instances of the BAM Event Bus Service</span></span>
<span data-ttu-id="738ad-103">El servicio de bus de eventos BAM se ejecuta en un host de aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="738ad-103">The BAM Event Bus Service runs inside a BizTalk application host.</span></span> <span data-ttu-id="738ad-104">Se puede utilizar el host predeterminado para alojar el servicio de bus de eventos BAM o, como alternativa, crear un nuevo host.</span><span class="sxs-lookup"><span data-stu-id="738ad-104">You can use the default host to host the BAM Event Bus Service, or you can create a new host.</span></span> <span data-ttu-id="738ad-105">Si un host aloja el servicio de bus de eventos BAM, todas las nuevas instancias de ese host que se creen </span><span class="sxs-lookup"><span data-stu-id="738ad-105">If a host hosts the BAM Event Bus service, any new instances you create for that host also hosts the service.</span></span>  
  
 <span data-ttu-id="738ad-106">Para obtener información sobre el host predeterminado, consulte [Hosts](../core/hosts.md).</span><span class="sxs-lookup"><span data-stu-id="738ad-106">For information about the default host, see [Hosts](../core/hosts.md).</span></span>  
  
 <span data-ttu-id="738ad-107">Para obtener información sobre la creación de hosts, consulte [cómo crear un nuevo Host](../core/how-to-create-a-new-host.md).</span><span class="sxs-lookup"><span data-stu-id="738ad-107">For information about creating hosts, see [How to Create a New Host](../core/how-to-create-a-new-host.md).</span></span>  
  
 <span data-ttu-id="738ad-108">Para obtener información sobre la creación de instancias de host, consulte [cómo agregar una instancia de Host](../core/how-to-add-a-host-instance.md).</span><span class="sxs-lookup"><span data-stu-id="738ad-108">For information about creating host instances, see [How to Add a Host Instance](../core/how-to-add-a-host-instance.md).</span></span>  
  
 <span data-ttu-id="738ad-109">Para obtener información sobre la creación y configuración de hosts e instancias de host, consulte [administración de Hosts de BizTalk e instancias de Host](../core/managing-biztalk-hosts-and-host-instances.md).</span><span class="sxs-lookup"><span data-stu-id="738ad-109">For information about creating and configuring hosts and host instances, see [Managing BizTalk Hosts and Host Instances](../core/managing-biztalk-hosts-and-host-instances.md).</span></span>  
  
### <a name="to-create-the-host-that-hosts-the-bam-event-bus-service"></a><span data-ttu-id="738ad-110">Para crear el host que alojará el servicio de bus de eventos BAM</span><span class="sxs-lookup"><span data-stu-id="738ad-110">To create the host that hosts the BAM Event Bus Service</span></span>  
  
1. <span data-ttu-id="738ad-111">Haga clic en **iniciar**, apunte a **todos los programas**, haga clic en **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="738ad-111">Click **Start**, point to **All Programs**, click **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="738ad-112">En la ventana de consola de administración de BizTalk, expanda el **administración de BizTalk Server** nodo, expanda el **grupo de Biztalk** nodo y expanda el **configuración de plataforma** nodo , haga clic en el **Hosts** nodo, seleccione **New**y, a continuación, haga clic en **Host**.</span><span class="sxs-lookup"><span data-stu-id="738ad-112">In the BizTalk Administration Console window, expand the **BizTalk Server Administration** node, expand the **Biztalk Group** node and expand the **Platform Settings** node, right-click the **Hosts** node, select **New**, and then click **Host**.</span></span>  
  
3. <span data-ttu-id="738ad-113">En el **propiedades de Host** cuadro de diálogo el **nombre** cuadro, escriba un nombre descriptivo para el host.</span><span class="sxs-lookup"><span data-stu-id="738ad-113">In the **Host Properties** dialog box, in the **Name** box, type a descriptive name for the host.</span></span>  
  
4. <span data-ttu-id="738ad-114">En el **General** ficha, seleccione el **Permitir seguimiento de Host** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="738ad-114">On the **General** tab, select the **Allow Host Tracking** check box.</span></span>  
  
    <span data-ttu-id="738ad-115">Aparece un nuevo nodo secundario bajo el **Hosts** nodo con el nombre del nuevo host.</span><span class="sxs-lookup"><span data-stu-id="738ad-115">A new child node appears under the **Hosts** node with the name of the new host.</span></span>  
  
5. <span data-ttu-id="738ad-116">En el **grupo Windows** , escriba el nombre del grupo de Windows para asignar el host y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="738ad-116">In the **Windows group** box, type the name of the Windows group to assign this host, and then click **OK**.</span></span>  
  
    <span data-ttu-id="738ad-117">Aparece un nuevo nodo secundario bajo el **Hosts** nodo con el nombre del nuevo host.</span><span class="sxs-lookup"><span data-stu-id="738ad-117">A new child node appears under the **Hosts** node with the name of the new host.</span></span>  
  
### <a name="to-create-a-new-host-instance-of-the-host"></a><span data-ttu-id="738ad-118">Para crear una nueva instancia del host</span><span class="sxs-lookup"><span data-stu-id="738ad-118">To create a new host instance of the host</span></span>  
  
1.  <span data-ttu-id="738ad-119">Haga clic en el **instancia de Host** nodo, seleccione **New**y, a continuación, haga clic en **instancia de Host**.</span><span class="sxs-lookup"><span data-stu-id="738ad-119">Right-click the **Host Instance** node, select **New**, and then click **Host Instance**.</span></span>  
  
2.  <span data-ttu-id="738ad-120">Seleccione un servidor que ejecute la instancia de host y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="738ad-120">Select a server where the host instance will run, and then click **OK**.</span></span>  
  
### <a name="to-add-hosting-tracking-to-the-host"></a><span data-ttu-id="738ad-121">Para agregar el seguimiento de alojamiento al host</span><span class="sxs-lookup"><span data-stu-id="738ad-121">To add hosting tracking to the host</span></span>  
  
1.  <span data-ttu-id="738ad-122">Haga clic en el host que desea volver a configurar y, a continuación, haga clic en **propiedades** .</span><span class="sxs-lookup"><span data-stu-id="738ad-122">Right-click the host you want to reconfigure, and then click **Properties** .</span></span>  
  
2.  <span data-ttu-id="738ad-123">En el **General** ficha, seleccione **Permitir seguimiento de Host**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="738ad-123">On the **General** tab, select **Allow Host Tracking**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="738ad-124">Reinicie todas las instancias de ese host.</span><span class="sxs-lookup"><span data-stu-id="738ad-124">Restart all instances of that host.</span></span>  
  
### <a name="to-remove-hosting-tracking-from-the-host"></a><span data-ttu-id="738ad-125">Para quitar el seguimiento de alojamiento del host</span><span class="sxs-lookup"><span data-stu-id="738ad-125">To remove hosting tracking from the host</span></span>  
  
1.  <span data-ttu-id="738ad-126">Haga clic en el host desde el que desea quitar el seguimiento de host y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="738ad-126">Right-click the host from which you want to remove host tracking, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="738ad-127">Desactive el **Permitir seguimiento de Host** casilla de verificación y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="738ad-127">Clear the **Allow Host tracking** check box, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="738ad-128">Reinicie las instancias de ese host.</span><span class="sxs-lookup"><span data-stu-id="738ad-128">Restart instances of that host.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="738ad-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="738ad-129">See Also</span></span>  
 <span data-ttu-id="738ad-130">[Administrar el servicio de Bus de eventos BAM](../core/managing-the-bam-event-bus-service.md) </span><span class="sxs-lookup"><span data-stu-id="738ad-130">[Managing the BAM Event Bus Service](../core/managing-the-bam-event-bus-service.md) </span></span>  
 <span data-ttu-id="738ad-131">[Recomendaciones de seguridad BAM](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="738ad-131">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="738ad-132">Supervisión de la actividad económica (BAM)</span><span class="sxs-lookup"><span data-stu-id="738ad-132">Business Activity Monitoring (BAM)</span></span>](../core/business-activity-monitoring-bam.md)