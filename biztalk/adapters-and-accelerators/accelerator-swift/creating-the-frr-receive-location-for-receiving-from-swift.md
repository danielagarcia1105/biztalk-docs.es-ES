---
title: "Crear la FRR ubicación de recepción para la recepción de SWIFT | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive locations, creating
- creating, receive locations
- FRR, creating receive locations
ms.assetid: e10857f4-21cb-4c09-8eed-cb6e9b0a0aa9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e43ac2ac0fab9b2a29a44784032f9d3369833ae2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-the-frr-receive-location-for-receiving-from-swift"></a><span data-ttu-id="586a9-102">Crear la FRR ubicación de recepción para la recepción de SWIFT.</span><span class="sxs-lookup"><span data-stu-id="586a9-102">Creating the FRR Receive Location for Receiving from SWIFT</span></span>
<span data-ttu-id="586a9-103">Para realizar la conciliación de respuesta de FIN, debe crear una ubicación de recepción que recibe un mensaje desde la red SWIFT en A4SWIFT.</span><span class="sxs-lookup"><span data-stu-id="586a9-103">To perform FIN Response Reconciliation, you need to create a receive location that receives a message from the SWIFT Network into A4SWIFT.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="586a9-104">Es aconsejable configurar dos ubicaciones de recepción para recibir mensajes de AAS: uno para recibir PAN/NaN y otro para todos los demás mensajes de recepción.</span><span class="sxs-lookup"><span data-stu-id="586a9-104">It is advisable to set up two receive locations for receiving messages from SAA: one to receive PAN/NANs and one to receive all other messages.</span></span> <span data-ttu-id="586a9-105">Para configurar ubicaciones de recepción de los dos, debe recibir mensajes de dos colas de MQSeries en AAS: uno para PAN/NaN y otro para los demás tipos de mensaje.</span><span class="sxs-lookup"><span data-stu-id="586a9-105">To set up the two receive locations, you must receive messages from two MQSeries queues at SAA: one for PAN/NANs and one for all other message types.</span></span>  
  
 <span data-ttu-id="586a9-106">**Resumen**</span><span class="sxs-lookup"><span data-stu-id="586a9-106">**Summary**</span></span>  
  
 <span data-ttu-id="586a9-107">Crear una ubicación de recepción con las siguientes propiedades y los componentes:</span><span class="sxs-lookup"><span data-stu-id="586a9-107">Create a receive location with the following properties and components:</span></span>  
  
|<span data-ttu-id="586a9-108">Propiedad/componente</span><span class="sxs-lookup"><span data-stu-id="586a9-108">Property/Component</span></span>|<span data-ttu-id="586a9-109">Configuración</span><span class="sxs-lookup"><span data-stu-id="586a9-109">Setting</span></span>|  
|-------------------------|-------------|  
|<span data-ttu-id="586a9-110">Puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="586a9-110">Receive port</span></span>|<span data-ttu-id="586a9-111">Puerto unidireccional</span><span class="sxs-lookup"><span data-stu-id="586a9-111">One-way port</span></span>|  
|<span data-ttu-id="586a9-112">Tipo de transporte</span><span class="sxs-lookup"><span data-stu-id="586a9-112">Transport type</span></span>|<span data-ttu-id="586a9-113">MQSeries</span><span class="sxs-lookup"><span data-stu-id="586a9-113">MQSeries</span></span>|  
|<span data-ttu-id="586a9-114">Definición de la cola (MQSeries)</span><span class="sxs-lookup"><span data-stu-id="586a9-114">Queue Definition (MQSeries)</span></span>|<span data-ttu-id="586a9-115">Servidor de MQSeries</span><span class="sxs-lookup"><span data-stu-id="586a9-115">MQSeries server</span></span><br /><span data-ttu-id="586a9-116">Administrador de cola</span><span class="sxs-lookup"><span data-stu-id="586a9-116">Queue manager</span></span><br /><span data-ttu-id="586a9-117">Cola</span><span class="sxs-lookup"><span data-stu-id="586a9-117">Queue</span></span>|  
|<span data-ttu-id="586a9-118">Controlador de recepción</span><span class="sxs-lookup"><span data-stu-id="586a9-118">Receive handler</span></span>|<span data-ttu-id="586a9-119">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="586a9-119">BizTalkServerApplication</span></span>|  
|<span data-ttu-id="586a9-120">Canalización de recepción</span><span class="sxs-lookup"><span data-stu-id="586a9-120">Receive pipeline</span></span>|<span data-ttu-id="586a9-121">El A4SWIFT canalización de recepción que haya creado para FRR</span><span class="sxs-lookup"><span data-stu-id="586a9-121">The A4SWIFT receive pipeline that you created for FRR</span></span>|  
  
### <a name="to-add-an-frr-receive-location-for-receiving-from-swift"></a><span data-ttu-id="586a9-122">Para agregar una FRR ubicación de recepción para la recepción de SWIFT.</span><span class="sxs-lookup"><span data-stu-id="586a9-122">To add an FRR receive location for receiving from SWIFT</span></span>  
  
1.  <span data-ttu-id="586a9-123">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, **grupo de BizTalk**, **aplicaciones**, y **aplicación de BizTalk 1** nodos.</span><span class="sxs-lookup"><span data-stu-id="586a9-123">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and  **BizTalk Application 1** nodes.</span></span>  
  
2.  <span data-ttu-id="586a9-124">Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="586a9-124">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
3.  <span data-ttu-id="586a9-125">En el cuadro de diálogo Propiedades de puerto de recepción, en el **nombre** , escriba un nombre para el puerto de recepción, por ejemplo, FRRSWIFTReceivePort.</span><span class="sxs-lookup"><span data-stu-id="586a9-125">In the Receive Port Properties dialog box, in the **Name** box, type a name for the receive port, such as FRRSWIFTReceivePort.</span></span>  
  
4.  <span data-ttu-id="586a9-126">Haga clic en **aplicar** para enlazar el puerto y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="586a9-126">Click **Apply** to bind the port, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="586a9-127">En la consola de administración, haga clic en **ubicaciones de recepción**, seleccione **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="586a9-127">In the Administration Console, right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
6.  <span data-ttu-id="586a9-128">En el, seleccione un cuadro de diálogo de puerto de recepción, seleccione el puerto de recepción recién creado y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="586a9-128">In the Select a Receive Port dialog box, select the receive port that you just created, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="586a9-129">En el cuadro de diálogo Propiedades de la ubicación de recepción, en el **nombre** , escriba un nombre para la ubicación de recepción, por ejemplo, FRRSWIFTReceiveLocation.</span><span class="sxs-lookup"><span data-stu-id="586a9-129">In the Receive Location Properties dialog box, in the **Name** box, type a name for the receive location, such as FRRSWIFTReceiveLocation.</span></span>  
  
8.  <span data-ttu-id="586a9-130">En el **transporte** sección, para la **tipo** cuadro de texto, seleccione **MQSeries**.</span><span class="sxs-lookup"><span data-stu-id="586a9-130">In the **Transport** section, for the **Type** text box, select **MQSeries**.</span></span>  
  
9. <span data-ttu-id="586a9-131">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="586a9-131">Click **Configure**.</span></span>  
  
10. <span data-ttu-id="586a9-132">En el cuadro de diálogo Propiedades de transporte MQSeries, haga clic en **definición de la cola**y, a continuación, haga clic en el botón de puntos suspensivos (**...** ) botón.</span><span class="sxs-lookup"><span data-stu-id="586a9-132">In the MQSeries Transport Properties dialog box, click **Queue Definition**, and then click the ellipsis (**…**) button.</span></span>  
  
11. <span data-ttu-id="586a9-133">En el **definición de la cola** cuadro de diálogo, especifique el servidor de MQSeries, el Administrador de cola y poner en cola.</span><span class="sxs-lookup"><span data-stu-id="586a9-133">In the **Queue Definition** dialog box, enter the MQSeries server, queue manager, and queue.</span></span> <span data-ttu-id="586a9-134">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="586a9-134">Click **OK**.</span></span>  
  
12. <span data-ttu-id="586a9-135">En el **propiedades de transporte MQSeries** diálogo cuadro, compruebe que las propiedades según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="586a9-135">In the **MQSeries Transport Properties** dialog box, verify that the properties are as needed.</span></span> <span data-ttu-id="586a9-136">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="586a9-136">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="586a9-137">Para obtener más información acerca de las propiedades de transporte de MQSeries, consulte la documentación de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="586a9-137">For more information about MQSeries transport properties, see the MQSeries documentation.</span></span>  
  
13. <span data-ttu-id="586a9-138">En el cuadro de diálogo Propiedades de la ubicación de recepción, para **controlador de recepción**, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="586a9-138">In the Receive Location Properties dialog box, for **Receive Handler**, select **BizTalkServerApplication**.</span></span>  
  
14. <span data-ttu-id="586a9-139">Para **canalización de recepción** sección, seleccione la A4SWIFT canalización de recepción que haya creado para FRR.</span><span class="sxs-lookup"><span data-stu-id="586a9-139">For **Receive Pipeline** section, select the A4SWIFT receive pipeline that you created for FRR.</span></span>  
  
15. <span data-ttu-id="586a9-140">Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**</span><span class="sxs-lookup"><span data-stu-id="586a9-140">Click **Apply**, and then click **OK**</span></span>  
  
16. <span data-ttu-id="586a9-141">En el Explorador de BizTalk, haga clic en la ubicación de recepción recién creado y, a continuación, haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="586a9-141">In BizTalk Explorer, right-click the receive location that you just created, and then click **Enable**.</span></span>