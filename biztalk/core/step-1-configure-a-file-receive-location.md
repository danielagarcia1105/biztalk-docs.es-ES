---
title: 'Paso 1: Configurar un archivo de ubicación de recepción | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df591263-964a-4ad8-bc3a-a553de8dae4f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78f8bccc187bf310b8426fc3d5fee36add44a9f3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278260"
---
# <a name="step-1-configure-a-file-receive-location"></a><span data-ttu-id="78d59-102">Paso 1: Configurar un archivo de ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="78d59-102">Step 1: Configure a FILE Receive Location</span></span>
<span data-ttu-id="78d59-103">En este tema configurará una ubicación de recepción de FILE que consume el mensaje de solicitud ficticio que coloca en una carpeta de archivos para invocar el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="78d59-103">In this topic, you configure a FILE receive location that consumes the dummy request message that you drop to a file folder to invoke the send port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="78d59-104">Los pasos de este tutorial se supone que usa la aplicación predeterminada (**BizTalk Application 1**) para crear la solución.</span><span class="sxs-lookup"><span data-stu-id="78d59-104">The steps in this tutorial assume that you use the default application (**BizTalk Application 1**) to create the solution.</span></span> <span data-ttu-id="78d59-105">También puede crear otra aplicación y realizar los mismos pasos en cualquier aplicación.</span><span class="sxs-lookup"><span data-stu-id="78d59-105">You can also create another application and perform the same steps in any that application.</span></span>  
  
### <a name="to-configure-a-file-receive-location"></a><span data-ttu-id="78d59-106">Para configurar una ubicación de recepción de archivos</span><span class="sxs-lookup"><span data-stu-id="78d59-106">To configure a FILE receive location</span></span>  
  
1.  <span data-ttu-id="78d59-107">Desde la consola de administración de BizTalk Server, en la **BizTalk Application 1** nodo, haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en  **Unidireccional puerto de recepción**.</span><span class="sxs-lookup"><span data-stu-id="78d59-107">From BizTalk Server Administration Console, under the **BizTalk Application 1** node, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
2.  <span data-ttu-id="78d59-108">En la ficha General, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="78d59-108">On the General tab, do the following:</span></span>  
  
    |<span data-ttu-id="78d59-109">Use</span><span class="sxs-lookup"><span data-stu-id="78d59-109">Use this</span></span>|<span data-ttu-id="78d59-110">Para</span><span class="sxs-lookup"><span data-stu-id="78d59-110">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="78d59-111">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="78d59-111">**Name**</span></span>|<span data-ttu-id="78d59-112">Tipo de **ReceivePortRestAzureMarketPlace**.</span><span class="sxs-lookup"><span data-stu-id="78d59-112">Type **ReceivePortRestAzureMarketPlace**.</span></span>|  
    |<span data-ttu-id="78d59-113">**Habilitar enrutamiento para mensajes con errores**</span><span class="sxs-lookup"><span data-stu-id="78d59-113">**Enable routing for failed messages**</span></span>|<span data-ttu-id="78d59-114">(clear)</span><span class="sxs-lookup"><span data-stu-id="78d59-114">(clear)</span></span>|  
  
3.  <span data-ttu-id="78d59-115">Haga clic en **ubicaciones de recepción**y, a continuación, haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="78d59-115">Click **Receive Locations**, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="78d59-116">Desde Ubicación de recepción1 - Propiedades de ubicación de recepción, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="78d59-116">From Receive Location1 – Receive Location Properties, do the following:</span></span>  
  
    |<span data-ttu-id="78d59-117">Use</span><span class="sxs-lookup"><span data-stu-id="78d59-117">Use this</span></span>|<span data-ttu-id="78d59-118">Para</span><span class="sxs-lookup"><span data-stu-id="78d59-118">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="78d59-119">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="78d59-119">**Name**</span></span>|<span data-ttu-id="78d59-120">Tipo de **ReceiveLocationAzureMarketPlace**.</span><span class="sxs-lookup"><span data-stu-id="78d59-120">Type **ReceiveLocationAzureMarketPlace**.</span></span>|  
    |<span data-ttu-id="78d59-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="78d59-121">**Type**</span></span>|<span data-ttu-id="78d59-122">Seleccione **archivo**.</span><span class="sxs-lookup"><span data-stu-id="78d59-122">Select **FILE**.</span></span>|  
    |<span data-ttu-id="78d59-123">**Controlador de recepción**</span><span class="sxs-lookup"><span data-stu-id="78d59-123">**Receive handler**</span></span>|<span data-ttu-id="78d59-124">Seleccionar **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="78d59-124">Select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="78d59-125">**La canalización de recepción**</span><span class="sxs-lookup"><span data-stu-id="78d59-125">**Receive pipeline**</span></span>|<span data-ttu-id="78d59-126">Seleccione **PassThruReceive**.</span><span class="sxs-lookup"><span data-stu-id="78d59-126">Select **PassThruReceive**.</span></span>|  
  
5.  <span data-ttu-id="78d59-127">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="78d59-127">Click **Configure**.</span></span>  
  
6.  <span data-ttu-id="78d59-128">Desde Propiedades de transporte de archivo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="78d59-128">From File Transport Properties, do the following:</span></span>  
  
    |<span data-ttu-id="78d59-129">Use</span><span class="sxs-lookup"><span data-stu-id="78d59-129">Use this</span></span>|<span data-ttu-id="78d59-130">Para</span><span class="sxs-lookup"><span data-stu-id="78d59-130">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="78d59-131">**Carpeta de recepción**</span><span class="sxs-lookup"><span data-stu-id="78d59-131">**Receive folder**</span></span>|<span data-ttu-id="78d59-132">Escriba una ubicación en la que colocará el mensaje de solicitud ficticio.</span><span class="sxs-lookup"><span data-stu-id="78d59-132">Type a location where you will drop the dummy request message.</span></span>|  
    |<span data-ttu-id="78d59-133">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="78d59-133">**File name**</span></span>|<span data-ttu-id="78d59-134">Conservar`*.xml`</span><span class="sxs-lookup"><span data-stu-id="78d59-134">Retain `*.xml`</span></span>|  
  
7.  <span data-ttu-id="78d59-135">Haga clic en **Aceptar** hasta que salga de todos los cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="78d59-135">Click **OK** until you exit all the dialog boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78d59-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="78d59-136">See Also</span></span>  
 [<span data-ttu-id="78d59-137">Tutorial 5: Invocar una interfaz REST con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="78d59-137">Tutorial 5: Invoking a REST Interface Using BizTalk Server</span></span>](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)