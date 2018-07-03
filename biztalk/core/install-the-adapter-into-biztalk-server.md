---
title: Instalar el adaptador en BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1164468d-75a9-4116-87a6-6055948c198b
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13e810a14fec9b51c0d6b0ef1d7b55db234d0a0b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005629"
---
# <a name="install-the-adapter-into-biztalk-server"></a><span data-ttu-id="06352-102">Instalar el adaptador en BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="06352-102">Install the Adapter into BizTalk Server</span></span>
<span data-ttu-id="06352-103">Una vez escritas las entradas apropiadas de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el Registro, es preciso agregar el adaptador a la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="06352-103">After the proper [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entries have been written to the registry the adapter must be added to the BizTalk Management database.</span></span> <span data-ttu-id="06352-104">Después de agregar el adaptador a esta base de datos, ya es un adaptador configurado de manera activa capaz de procesar mensajes cuando su configuración es correcta.</span><span class="sxs-lookup"><span data-stu-id="06352-104">After the adapter is added to this database it is an actively configured adapter and can process messages when it is properly configured.</span></span> <span data-ttu-id="06352-105">Para instalar el adaptador en la base de datos se utiliza la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06352-105">You install the adapter into the database by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="06352-106">Después de instalar el adaptador en la base de datos, reinicie la instancia de host.</span><span class="sxs-lookup"><span data-stu-id="06352-106">After installing the adapter in the database, restart the host instance.</span></span>  

> [!NOTE]
>  <span data-ttu-id="06352-107">Para que esté visible y se pueda agregar en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], un adaptador debe registrarse debidamente en el Registro HKLM e implementar las interfaces de adaptador necesarias.</span><span class="sxs-lookup"><span data-stu-id="06352-107">To be visible for addition in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, an adapter must be properly registered in the HKLM registry and must implement the necessary adapter interfaces.</span></span>  

### <a name="to-install-the-static-sample-adapter"></a><span data-ttu-id="06352-108">Para instalar el adaptador estático de ejemplo</span><span class="sxs-lookup"><span data-stu-id="06352-108">To install the static sample adapter</span></span>  

1. <span data-ttu-id="06352-109">Haga clic en **iniciar**, apunte a **todos los programas**, apunte a [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="06352-109">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="06352-110">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga doble clic en el **grupo de BizTalk** nodo.</span><span class="sxs-lookup"><span data-stu-id="06352-110">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, double-click the  **BizTalk Group** node.</span></span>  

3. <span data-ttu-id="06352-111">Expanda **configuración de plataforma** y seleccione **adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="06352-111">Expand **Platform Settings** and select **Adapters**.</span></span>  

4. <span data-ttu-id="06352-112">Haga clic en **adaptadores**, haga clic en **New**y, a continuación, haga clic en **adaptador**.</span><span class="sxs-lookup"><span data-stu-id="06352-112">Right-click **Adapters**, click **New**, and then click **Adapter**.</span></span>  

5. <span data-ttu-id="06352-113">En el **propiedades del adaptador** diálogo cuadro, realice lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="06352-113">In the **Adapter Properties** dialog box, do the following.</span></span>  


   |  <span data-ttu-id="06352-114">Use</span><span class="sxs-lookup"><span data-stu-id="06352-114">Use this</span></span>   |                      <span data-ttu-id="06352-115">Para</span><span class="sxs-lookup"><span data-stu-id="06352-115">To do this</span></span>                       |
   |-------------|-------------------------------------------------------|
   |    <span data-ttu-id="06352-116">Nombre</span><span class="sxs-lookup"><span data-stu-id="06352-116">Name</span></span>     |                   <span data-ttu-id="06352-117">Tipo **estático**.</span><span class="sxs-lookup"><span data-stu-id="06352-117">Type **Static**.</span></span>                    |
   |   <span data-ttu-id="06352-118">Adaptador</span><span class="sxs-lookup"><span data-stu-id="06352-118">Adapter</span></span>   | <span data-ttu-id="06352-119">Seleccione **DotNetFile estático** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="06352-119">Select **Static DotNetFile** from the drop-down list.</span></span> |
   | <span data-ttu-id="06352-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="06352-120">Description</span></span> |            <span data-ttu-id="06352-121">Tipo **adaptador estático de ejemplo**.</span><span class="sxs-lookup"><span data-stu-id="06352-121">Type **Sample Static Adapter**.</span></span>            |


6. <span data-ttu-id="06352-122">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="06352-122">Click **OK**.</span></span>  

    <span data-ttu-id="06352-123">El adaptador estático aparece en la lista de adaptadores, en la ventana derecha de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06352-123">The static adapter now appears in the list of adapters in the right window of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

### <a name="to-stop-and-restart-the-host-instance"></a><span data-ttu-id="06352-124">Para detener y reiniciar la instancia de host</span><span class="sxs-lookup"><span data-stu-id="06352-124">To stop and restart the host instance</span></span>  

1. <span data-ttu-id="06352-125">Haga clic en **iniciar**, apunte a **todos los programas**, apunte a [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**.</span><span class="sxs-lookup"><span data-stu-id="06352-125">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**.</span></span>  

2. <span data-ttu-id="06352-126">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga doble clic en el **grupo de BizTalk** nodo.</span><span class="sxs-lookup"><span data-stu-id="06352-126">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, double-click the  **BizTalk Group** node.</span></span>  

3. <span data-ttu-id="06352-127">Expanda **configuración de plataforma**, seleccione **Hosts**y, a continuación, seleccione **BizTalkServerApplication** en el panel de resultados.</span><span class="sxs-lookup"><span data-stu-id="06352-127">Expand **Platform Settings**, select **Hosts**, and then select **BizTalkServerApplication** in the results pane.</span></span>  

4. <span data-ttu-id="06352-128">Haga clic en la instancia de host (normalmente, el nombre del equipo) y, a continuación, haga clic en **detener**.</span><span class="sxs-lookup"><span data-stu-id="06352-128">Right-click the host instance (typically, the computer name), and then click **Stop**.</span></span>  

    <span data-ttu-id="06352-129">El estado de la instancia de host cambia a **detenido**.</span><span class="sxs-lookup"><span data-stu-id="06352-129">The status of the host instance changes to **Stopped**.</span></span>  

5. <span data-ttu-id="06352-130">En el panel de resultados, haga clic en la instancia de host y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="06352-130">In the results pane, right-click the host instance, and then click **Start**.</span></span>  

    <span data-ttu-id="06352-131">El estado de la instancia de host cambia a **Inicio pendiente**.</span><span class="sxs-lookup"><span data-stu-id="06352-131">The status of the host instance changes to **Start pending**.</span></span> <span data-ttu-id="06352-132">Debe hacer clic en **actualizar**, o haga clic en la instancia de host y, a continuación, haga clic en **actualizar**, para cambiar el estado a **ejecutando**.</span><span class="sxs-lookup"><span data-stu-id="06352-132">You must click **Refresh**, or right-click the host instance and then click **Refresh**, to change the status to **Running**.</span></span>