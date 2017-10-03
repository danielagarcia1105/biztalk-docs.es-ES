---
title: "Lección 2: Agregar un puerto de envío de archivo sin formato | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send ports, flat files
- flat files, send ports
- creating, send ports
- send ports, creating
ms.assetid: 33dceb0d-85f5-4e19-820f-cd33b60cd32a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1370b4877c2e32055e2ee0a0aca1f922bd8668a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-2-adding-a-flat-file-send-port"></a><span data-ttu-id="ff2c3-102">Lección 2: Agregar un puerto de envío de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="ff2c3-102">Lesson 2: Adding a Flat File Send Port</span></span>
<span data-ttu-id="ff2c3-103">En esta lección, configurará el puerto de envío y la ubicación de envío.</span><span class="sxs-lookup"><span data-stu-id="ff2c3-103">In this lesson, you configure the send port and the send location.</span></span> <span data-ttu-id="ff2c3-104">Utilice el puerto de envío para definir cómo desea que los mensajes enviados.</span><span class="sxs-lookup"><span data-stu-id="ff2c3-104">You use the send port to define how you want messages sent.</span></span> <span data-ttu-id="ff2c3-105">También crea una ubicación de carpeta de archivos para los mensajes enviados.</span><span class="sxs-lookup"><span data-stu-id="ff2c3-105">You also create a file folder location for sent messages.</span></span>  
  
### <a name="to-add-a-flat-file-send-port"></a><span data-ttu-id="ff2c3-106">Para agregar un puerto de envío de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="ff2c3-106">To add a flat file send port</span></span>  
  
1.  <span data-ttu-id="ff2c3-107">En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="ff2c3-107">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="ff2c3-108">En el cuadro de diálogo Propiedades de puerto de envío, en la **nombre** , escriba **MT103_FlatFile_SendPort**.</span><span class="sxs-lookup"><span data-stu-id="ff2c3-108">In the Send Port Properties dialog box, in the **Name** box, type **MT103_FlatFile_SendPort**.</span></span>  
  
3.  <span data-ttu-id="ff2c3-109">En el **transporte** sección, para la **tipo** cuadro, haga clic en la lista desplegable y, a continuación, seleccione **archivo**.</span><span class="sxs-lookup"><span data-stu-id="ff2c3-109">In the **Transport** section, for the **Type** box, click the drop-down list, and then select **FILE**.</span></span>  
  
4.  <span data-ttu-id="ff2c3-110">Haga clic en el **configurar** situado a la derecha de la lista desplegable de tipo.</span><span class="sxs-lookup"><span data-stu-id="ff2c3-110">Click the **Configure** button to the right of the Type drop-down list.</span></span>  
  
5.  <span data-ttu-id="ff2c3-111">En el cuadro de diálogo Propiedades de transporte de archivo, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="ff2c3-111">In the FILE Transport Properties dialog box, click **Browse**.</span></span>  
  
6.  <span data-ttu-id="ff2c3-112">En el cuadro de diálogo Buscar carpeta, desplácese a la  **\<unidad >: \Labs** carpeta y, a continuación, haga clic en **crear nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="ff2c3-112">In the Browse For Folder dialog box, move to the **\<drive>:\Labs** folder, and then click **Make New Folder**.</span></span>  
  
7.  <span data-ttu-id="ff2c3-113">Crear un **saliente** carpeta  **\<unidad >: \Labs**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff2c3-113">Create an **Outbound** folder in **\<drive>:\Labs**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="ff2c3-114">En el **nombre de archivo** , escriba **%MessageID%.txt**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff2c3-114">In the **File name** box, type **%MessageID%.txt**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="ff2c3-115">En el cuadro de diálogo Propiedades de puerto de envío, haga clic en la lista desplegable para la **canalización de envío** cuadro y, a continuación, seleccione **MT103SendPipeline**.</span><span class="sxs-lookup"><span data-stu-id="ff2c3-115">In the Send Port Properties dialog box, click the drop-down list for the **Send pipeline** box, and then select **MT103SendPipeline**.</span></span>  
  
10. <span data-ttu-id="ff2c3-116">En el panel izquierdo, haga clic en **filtros**, y, a continuación, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ff2c3-116">In the left pane, click **Filters**, and then do the following:</span></span>  
  
    |<span data-ttu-id="ff2c3-117">Use</span><span class="sxs-lookup"><span data-stu-id="ff2c3-117">Use this</span></span>|<span data-ttu-id="ff2c3-118">Para</span><span class="sxs-lookup"><span data-stu-id="ff2c3-118">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="ff2c3-119">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="ff2c3-119">**Property**</span></span>|<span data-ttu-id="ff2c3-120">Seleccione **BTS. ReceivePortName**.</span><span class="sxs-lookup"><span data-stu-id="ff2c3-120">Select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="ff2c3-121">**Operador**</span><span class="sxs-lookup"><span data-stu-id="ff2c3-121">**Operator**</span></span>|<span data-ttu-id="ff2c3-122">Seleccione  **==** .</span><span class="sxs-lookup"><span data-stu-id="ff2c3-122">Select **==**.</span></span>|  
    |<span data-ttu-id="ff2c3-123">**Valor**</span><span class="sxs-lookup"><span data-stu-id="ff2c3-123">**Value**</span></span>|<span data-ttu-id="ff2c3-124">Tipo de **MT103_XML_ReceivePort**.</span><span class="sxs-lookup"><span data-stu-id="ff2c3-124">Type **MT103_XML_ReceivePort**.</span></span>|  
  
11. <span data-ttu-id="ff2c3-125">Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="ff2c3-125">Click **Apply**, and then click **OK.**</span></span>  
  
12. <span data-ttu-id="ff2c3-126">En el **puertos de envío** panel, haga clic en **MT103_FlatFile_SendPort**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="ff2c3-126">In the **Send Ports** pane, right-click **MT103_FlatFile_SendPort**, and then click **Start**.</span></span>  
  
 <span data-ttu-id="ff2c3-127">Continúe con [módulo 5: agregar un archivo plano ubicación de recepción y puertos de envío XML](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md).</span><span class="sxs-lookup"><span data-stu-id="ff2c3-127">Proceed to [Module 5: Adding a Flat File Receive Location and XML Send Port](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md).</span></span>