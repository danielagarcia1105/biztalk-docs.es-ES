---
title: 'Lección 2: Agregar un puerto de envío de archivos planos | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, flat files
- flat files, send ports
- creating, send ports
- send ports, creating
ms.assetid: 33dceb0d-85f5-4e19-820f-cd33b60cd32a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90b08dd8083e78d1e7cd98e8e8f705ac23d9bd17
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997325"
---
# <a name="lesson-2-adding-a-flat-file-send-port"></a><span data-ttu-id="df916-102">Lección 2: Agregar un puerto de envío de archivos planos</span><span class="sxs-lookup"><span data-stu-id="df916-102">Lesson 2: Adding a Flat File Send Port</span></span>
<span data-ttu-id="df916-103">En esta lección, configurará el puerto de envío y la ubicación de envío.</span><span class="sxs-lookup"><span data-stu-id="df916-103">In this lesson, you configure the send port and the send location.</span></span> <span data-ttu-id="df916-104">Utilice el puerto de envío para definir cómo desea que los mensajes enviados.</span><span class="sxs-lookup"><span data-stu-id="df916-104">You use the send port to define how you want messages sent.</span></span> <span data-ttu-id="df916-105">También crea una ubicación de carpeta de archivos para los mensajes enviados.</span><span class="sxs-lookup"><span data-stu-id="df916-105">You also create a file folder location for sent messages.</span></span>  

### <a name="to-add-a-flat-file-send-port"></a><span data-ttu-id="df916-106">Para agregar un puerto de envío de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="df916-106">To add a flat file send port</span></span>  

1. <span data-ttu-id="df916-107">En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="df916-107">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  

2. <span data-ttu-id="df916-108">En el cuadro de diálogo Propiedades de puerto de envío, en el **nombre** , escriba **MT103_FlatFile_SendPort**.</span><span class="sxs-lookup"><span data-stu-id="df916-108">In the Send Port Properties dialog box, in the **Name** box, type **MT103_FlatFile_SendPort**.</span></span>  

3. <span data-ttu-id="df916-109">En el **transporte** sección, para el **tipo** cuadro, haga clic en la lista desplegable y, a continuación, seleccione **archivo**.</span><span class="sxs-lookup"><span data-stu-id="df916-109">In the **Transport** section, for the **Type** box, click the drop-down list, and then select **FILE**.</span></span>  

4. <span data-ttu-id="df916-110">Haga clic en el **configurar** situado a la derecha de la lista desplegable de tipos.</span><span class="sxs-lookup"><span data-stu-id="df916-110">Click the **Configure** button to the right of the Type drop-down list.</span></span>  

5. <span data-ttu-id="df916-111">En el cuadro de diálogo Propiedades de transporte de archivo, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="df916-111">In the FILE Transport Properties dialog box, click **Browse**.</span></span>  

6. <span data-ttu-id="df916-112">En el cuadro de diálogo Buscar carpeta, desplácese a la  **\<unidad\>: \Labs** carpeta y, a continuación, haga clic en **crear nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="df916-112">In the Browse For Folder dialog box, move to the **\<drive\>:\Labs** folder, and then click **Make New Folder**.</span></span>  

7. <span data-ttu-id="df916-113">Crear un **saliente** carpeta  **\<unidad\>: \Labs**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="df916-113">Create an **Outbound** folder in **\<drive\>:\Labs**, and then click **OK**.</span></span>  

8. <span data-ttu-id="df916-114">En el **nombre de archivo** , escriba **%MessageID%.txt**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="df916-114">In the **File name** box, type **%MessageID%.txt**, and then click **OK**.</span></span>  

9. <span data-ttu-id="df916-115">En el cuadro de diálogo Propiedades de puerto de envío, haga clic en la lista desplegable para la **canalización de envío** cuadro y, a continuación, seleccione **MT103SendPipeline**.</span><span class="sxs-lookup"><span data-stu-id="df916-115">In the Send Port Properties dialog box, click the drop-down list for the **Send pipeline** box, and then select **MT103SendPipeline**.</span></span>  

10. <span data-ttu-id="df916-116">En el panel izquierdo, haga clic en **filtros**, y, a continuación, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="df916-116">In the left pane, click **Filters**, and then do the following:</span></span>  


    |   <span data-ttu-id="df916-117">Use</span><span class="sxs-lookup"><span data-stu-id="df916-117">Use this</span></span>   |           <span data-ttu-id="df916-118">Para</span><span class="sxs-lookup"><span data-stu-id="df916-118">To do this</span></span>            |
    |--------------|---------------------------------|
    | <span data-ttu-id="df916-119">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="df916-119">**Property**</span></span> | <span data-ttu-id="df916-120">Seleccione **BTS. ReceivePortName**.</span><span class="sxs-lookup"><span data-stu-id="df916-120">Select **BTS.ReceivePortName**.</span></span> |
    | <span data-ttu-id="df916-121">**Operador**</span><span class="sxs-lookup"><span data-stu-id="df916-121">**Operator**</span></span> |         <span data-ttu-id="df916-122">Seleccione **==**.</span><span class="sxs-lookup"><span data-stu-id="df916-122">Select **==**.</span></span>          |
    |  <span data-ttu-id="df916-123">**Value**</span><span class="sxs-lookup"><span data-stu-id="df916-123">**Value**</span></span>   | <span data-ttu-id="df916-124">Tipo **MT103_XML_ReceivePort**.</span><span class="sxs-lookup"><span data-stu-id="df916-124">Type **MT103_XML_ReceivePort**.</span></span> |


11. <span data-ttu-id="df916-125">Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="df916-125">Click **Apply**, and then click **OK.**</span></span>  

12. <span data-ttu-id="df916-126">En el **puertos de envío** panel, haga clic en **MT103_FlatFile_SendPort**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="df916-126">In the **Send Ports** pane, right-click **MT103_FlatFile_SendPort**, and then click **Start**.</span></span>  

    <span data-ttu-id="df916-127">Continúe con [módulo 5: agregar una ubicación de recepción y puerto de envío XML](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md).</span><span class="sxs-lookup"><span data-stu-id="df916-127">Proceed to [Module 5: Adding a Flat File Receive Location and XML Send Port](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md).</span></span>