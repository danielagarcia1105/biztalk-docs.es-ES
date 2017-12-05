---
title: "Lección 1: Agregar un archivo sin formato puerto de recepción y ubicación | Documentos de Microsoft"
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
- receive ports, creating
- creating, receive ports
ms.assetid: 881f58d8-f541-4a85-b534-cb1ca627c002
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9856e0da6e8a4bc958b5fe08e0e1b5e87494531b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="lesson-1-adding-flat-file-receive-port-and-location"></a><span data-ttu-id="d2121-102">Lección 1: Agregar archivos sin puerto de recepción y ubicación</span><span class="sxs-lookup"><span data-stu-id="d2121-102">Lesson 1: Adding Flat File Receive Port and Location</span></span>
<span data-ttu-id="d2121-103">El puerto de recepción siempre tiene una ubicación de recepción asociada que se debe configurar al agregar el puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="d2121-103">The receive port always has an associated receive location that you must configure when you add the receive port.</span></span> <span data-ttu-id="d2121-104">Una ubicación de recepción define una dirección específica para un mensaje entrante y la canalización que se utiliza para procesar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="d2121-104">A receive location defines a specific address for an incoming message and the pipeline that you use to process the message.</span></span>  
  
### <a name="to-add-a-receive-port"></a><span data-ttu-id="d2121-105">Para agregar un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="d2121-105">To add a receive port</span></span>  
  
1.  <span data-ttu-id="d2121-106">En la consola de administración de BizTalk Server, haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="d2121-106">In the BizTalk Server Administration Console, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
2.  <span data-ttu-id="d2121-107">En el cuadro de diálogo Propiedades de puerto de recepción, en el **nombre** , escriba **MT103_FlatFile_ReceivePort**.</span><span class="sxs-lookup"><span data-stu-id="d2121-107">In the Receive Port Properties dialog box, in the **Name** box, type **MT103_FlatFile_ReceivePort**.</span></span>  
  
3.  <span data-ttu-id="d2121-108">Haga clic en **aplicar** para enlazar el puerto y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d2121-108">Click **Apply** to bind the port, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="d2121-109">En la consola de administración de BizTalk Server, haga clic en **ubicaciones de recepción**, seleccione **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="d2121-109">In the BizTalk Server Administration Console, right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
5.  <span data-ttu-id="d2121-110">En el, seleccione un cuadro de diálogo de puerto de recepción, haga clic en **MT103_FlatFile_ReceivePort**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d2121-110">In the Select a Receive Port dialog box, click **MT103_FlatFile_ReceivePort**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="d2121-111">En el cuadro de diálogo Propiedades de la ubicación de recepción, en el **nombre** , escriba **MT103_FlatFile_ReceiveLocation**.</span><span class="sxs-lookup"><span data-stu-id="d2121-111">In the Receive Location Properties dialog box, in the **Name** box, type **MT103_FlatFile_ReceiveLocation**.</span></span>  
  
7.  <span data-ttu-id="d2121-112">En el **transporte** sección, para la **tipo** cuadro de texto, haga clic en la lista desplegable y, a continuación, seleccione **archivo**.</span><span class="sxs-lookup"><span data-stu-id="d2121-112">In the **Transport** section, for the **Type** text box, click the drop-down list, and then select **FILE**.</span></span>  
  
8.  <span data-ttu-id="d2121-113">Haga clic en el **configurar** situado a la derecha de la lista desplegable de tipo.</span><span class="sxs-lookup"><span data-stu-id="d2121-113">Click the **Configure** button to the right of the Type drop-down list.</span></span>  
  
9. <span data-ttu-id="d2121-114">En el cuadro de diálogo Propiedades de transporte de archivo, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="d2121-114">In the FILE Transport Properties dialog box, click **Browse**.</span></span>  
  
10. <span data-ttu-id="d2121-115">En el cuadro de diálogo Buscar carpeta, desplácese a la  **\<unidad\>: \Labs\Inbound** carpeta y, a continuación, haga clic en **crear nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="d2121-115">In the Browse For Folder dialog box, move to the **\<drive\>:\Labs\Inbound** folder, and then click **Make New Folder**.</span></span>  
  
11. <span data-ttu-id="d2121-116">Crear un **FlatFile** carpeta  **\<unidad\>: \Labs\Inbound**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d2121-116">Create a **FlatFile** folder in **\<drive\>:\Labs\Inbound**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="d2121-117">En el **máscara de archivo** , escriba  **\*.txt**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d2121-117">In the **File mask** box, type **\*.txt**, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="d2121-118">En el cuadro de diálogo Propiedades de la ubicación de recepción, asegúrese de que **BizTalkServerApplication** se haya especificado para la **controlador de recepción** cuadro.</span><span class="sxs-lookup"><span data-stu-id="d2121-118">In the Receive Location Properties dialog box, ensure that **BizTalkServerApplication** is entered for the **Receive handler** box.</span></span>  
  
14. <span data-ttu-id="d2121-119">Para el **canalización de recepción** cuadro, seleccione **MT103ReceivePipeline** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="d2121-119">For the **Receive Pipeline** box, select **MT103ReceivePipeline** from the drop-down list.</span></span>  
  
15. <span data-ttu-id="d2121-120">Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d2121-120">Click **Apply**, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="d2121-121">En la consola de administración de BizTalk Server, haga clic en **ubicaciones de recepción**, haga clic en **MT103_FlatFile_ReceiveLocation**y, a continuación, haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="d2121-121">In the BizTalk Server Administration Console, click **Receive Locations**, right-click **MT103_FlatFile_ReceiveLocation**, and then click **Enable**.</span></span>  
  
 <span data-ttu-id="d2121-122">Continúe con [lección 2: agregar un puerto de envío XML](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-an-xml-send-port.md).</span><span class="sxs-lookup"><span data-stu-id="d2121-122">Proceed to [Lesson 2: Adding an XML Send Port](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-an-xml-send-port.md).</span></span>