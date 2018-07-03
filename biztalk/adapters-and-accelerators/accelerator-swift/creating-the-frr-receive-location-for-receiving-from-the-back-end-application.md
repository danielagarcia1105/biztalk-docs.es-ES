---
title: Crear el FRR ubicación de recepción para recibir de la aplicación de Back-End | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, creating
- creating, receive locations
- FRR, creating receive locations
ms.assetid: 78bd8084-ddec-4066-a474-ab5b1a0a849f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26ac72c9d122b626411e67cfc6e18f76de226415
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002861"
---
# <a name="creating-the-frr-receive-location-for-receiving-from-the-back-end-application"></a><span data-ttu-id="0f6e2-102">Crear el FRR ubicación de recepción para recibir de la aplicación de Back-End</span><span class="sxs-lookup"><span data-stu-id="0f6e2-102">Creating the FRR Receive Location for Receiving from the Back-End Application</span></span>
<span data-ttu-id="0f6e2-103">Para llevar a cabo la conciliación de respuestas de FIN, deberá crear una ubicación de recepción que recibe un mensaje de la aplicación de back-end en [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f6e2-103">To perform FIN Response Reconciliation, you need to create a receive location that receives a message from the back-end application into [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span>  

 <span data-ttu-id="0f6e2-104">**Resumen**</span><span class="sxs-lookup"><span data-stu-id="0f6e2-104">**Summary**</span></span>  

 <span data-ttu-id="0f6e2-105">Crear una ubicación de recepción con los componentes y las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="0f6e2-105">Create a receive location with the following properties and components:</span></span>  


| <span data-ttu-id="0f6e2-106">Propiedad o el componente</span><span class="sxs-lookup"><span data-stu-id="0f6e2-106">Property/Component</span></span> |                                                                 <span data-ttu-id="0f6e2-107">Configuración</span><span class="sxs-lookup"><span data-stu-id="0f6e2-107">Setting</span></span>                                                                 |
|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------|
|    <span data-ttu-id="0f6e2-108">Puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="0f6e2-108">Receive port</span></span>    |                                                              <span data-ttu-id="0f6e2-109">Puerto unidireccional</span><span class="sxs-lookup"><span data-stu-id="0f6e2-109">One-way port</span></span>                                                               |
|   <span data-ttu-id="0f6e2-110">Tipo de transporte</span><span class="sxs-lookup"><span data-stu-id="0f6e2-110">Transport type</span></span>   |                                           <span data-ttu-id="0f6e2-111">El tipo de transporte utilizado por la aplicación back-end</span><span class="sxs-lookup"><span data-stu-id="0f6e2-111">The transport type used by the back-end application</span></span>                                           |
|    <span data-ttu-id="0f6e2-112">Dirección URI</span><span class="sxs-lookup"><span data-stu-id="0f6e2-112">Address URI</span></span>     |                                                   <span data-ttu-id="0f6e2-113">Según sea necesario para el tipo de transporte</span><span class="sxs-lookup"><span data-stu-id="0f6e2-113">As required for the transport type</span></span>                                                    |
|  <span data-ttu-id="0f6e2-114">Controlador de recepción</span><span class="sxs-lookup"><span data-stu-id="0f6e2-114">Receive handler</span></span>   |                                                        <span data-ttu-id="0f6e2-115">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="0f6e2-115">BizTalkServerApplication</span></span>                                                         |
|  <span data-ttu-id="0f6e2-116">Canalización de recepción</span><span class="sxs-lookup"><span data-stu-id="0f6e2-116">Receive pipeline</span></span>  | <span data-ttu-id="0f6e2-117">El [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] canalización de recepción que ha creado para FRR</span><span class="sxs-lookup"><span data-stu-id="0f6e2-117">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receive pipeline that you created for FRR</span></span> |

### <a name="to-add-an-frr-receive-location-for-receiving-from-the-back-end-application"></a><span data-ttu-id="0f6e2-118">Para agregar una ubicación de recepción FRR para recibir de la aplicación de back-end</span><span class="sxs-lookup"><span data-stu-id="0f6e2-118">To add an FRR receive location for receiving from the back-end application</span></span>  

1. <span data-ttu-id="0f6e2-119">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, **grupo de BizTalk**, **aplicaciones**, y **aplicación de BizTalk 1** nodos.</span><span class="sxs-lookup"><span data-stu-id="0f6e2-119">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and **BizTalk Application 1** nodes.</span></span>  

2. <span data-ttu-id="0f6e2-120">Haga clic en **canalizaciones**y, a continuación, haga clic en **actualizar**.</span><span class="sxs-lookup"><span data-stu-id="0f6e2-120">Right-click **Pipelines**, and then click **Refresh**.</span></span>  

3. <span data-ttu-id="0f6e2-121">Haga clic en **puertos de recepción**, apunte a **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="0f6e2-121">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  

4. <span data-ttu-id="0f6e2-122">En el cuadro de diálogo Propiedades de puerto de recepción, en el **nombre** , escriba un nombre para el puerto de recepción, como FRRBackEndReceivePort.</span><span class="sxs-lookup"><span data-stu-id="0f6e2-122">In the Receive Port Properties dialog box, in the **Name** box, type a name for the receive port, such as FRRBackEndReceivePort.</span></span>  

5. <span data-ttu-id="0f6e2-123">Haga clic en **aplicar** para enlazar el puerto y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0f6e2-123">Click **Apply** to bind the port, and then click **OK**.</span></span>  

6. <span data-ttu-id="0f6e2-124">En la consola de administración, haga clic en **ubicaciones de recepción**, apunte a **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="0f6e2-124">In the Administration Console, right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  

7. <span data-ttu-id="0f6e2-125">En el, seleccione un cuadro de diálogo de puerto de recepción, seleccione el puerto de recepción que acaba de crear y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0f6e2-125">In the Select a Receive Port dialog box, select the receive port that you just created, and then click **OK**.</span></span>  

8. <span data-ttu-id="0f6e2-126">En el cuadro de diálogo Propiedades de ubicación de recepción, en el **nombre** , escriba un nombre para la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="0f6e2-126">In the Receive Location Properties dialog box, in the **Name** box, type a name for the receive location.</span></span>  

9. <span data-ttu-id="0f6e2-127">En el **transporte** sección, para el **tipo** cuadro de texto, seleccione el tipo de transporte utilizado por la aplicación de back-end.</span><span class="sxs-lookup"><span data-stu-id="0f6e2-127">In the **Transport** section, for the **Type** text box, select the transport type used by the back-end application.</span></span>  

10. <span data-ttu-id="0f6e2-128">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="0f6e2-128">Click **Configure**.</span></span>  

11. <span data-ttu-id="0f6e2-129">En el cuadro de diálogo Propiedades de transporte de archivo, rellene las propiedades necesarias para el tipo de transporte y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0f6e2-129">In the FILE Transport Properties dialog box, fill in the properties required for the transport type, and then click **OK**.</span></span>  

12. <span data-ttu-id="0f6e2-130">En el cuadro de diálogo Propiedades de ubicación de recepción para **controlador de recepción**, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="0f6e2-130">In the Receive Location Properties dialog box, for **Receive Handler**, select **BizTalkServerApplication**.</span></span>  

13. <span data-ttu-id="0f6e2-131">En el cuadro de diálogo Propiedades de ubicación de recepción para **canalización de recepción**, seleccione el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] canalización de recepción que ha creado para FRR.</span><span class="sxs-lookup"><span data-stu-id="0f6e2-131">In the Receive Location Properties dialog box, for **Receive Pipeline**, select the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receive pipeline that you created for FRR.</span></span>  

14. <span data-ttu-id="0f6e2-132">Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar** para cerrar el **propiedades de ubicación de recepción** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="0f6e2-132">Click **Apply**, and then click **OK** to close the **Receive Location Properties** dialog box.</span></span>  

15. <span data-ttu-id="0f6e2-133">En el Explorador de BizTalk, haga clic en la ubicación de recepción recién creado y, a continuación, haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="0f6e2-133">In BizTalk Explorer, right-click the receive location that you just created, and then click **Enable**.</span></span>
