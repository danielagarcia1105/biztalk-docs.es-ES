---
title: 'Lección 1: Agregar XML puerto de recepción y ubicación | Documentos de Microsoft'
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
- receive ports, creating
- creating, receive ports
ms.assetid: 252bc080-3820-44cc-8749-715869f3f684
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d01f9457404e135027f35f1402575efeec311e2e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961266"
---
# <a name="lesson-1-adding-xml-receive-port-and-location"></a><span data-ttu-id="96926-102">Lección 1: Agregar puerto y la ubicación de recepción de XML</span><span class="sxs-lookup"><span data-stu-id="96926-102">Lesson 1: Adding XML Receive Port and Location</span></span>
<span data-ttu-id="96926-103">Un puerto de recepción es una agrupación lógica de ubicaciones de recepción similares.</span><span class="sxs-lookup"><span data-stu-id="96926-103">A receive port is a logical grouping of similar receive locations.</span></span> <span data-ttu-id="96926-104">Una ubicación de recepción define una dirección específica (por ejemplo, una ubicación de archivo o dirección URL) para un mensaje entrante y la canalización que se utiliza para procesar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="96926-104">A receive location defines a specific address (such as a URL or file location) for an incoming message and the pipeline that is used to process the message.</span></span>  
  
### <a name="to-add-a-receive-port"></a><span data-ttu-id="96926-105">Para agregar un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="96926-105">To add a receive port</span></span>  
  
1.  <span data-ttu-id="96926-106">Iniciar **administración de BizTalk Server** consola.</span><span class="sxs-lookup"><span data-stu-id="96926-106">Start **BizTalk Server Administration** console.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="96926-107">La consola de administración de BizTalk Server también puede abrir desde dentro de Visual Studio, haga clic en **administración de BizTalk Server** en el **herramientas** menú.</span><span class="sxs-lookup"><span data-stu-id="96926-107">The BizTalk Server Administration Console can also be opened from within Visual Studio by clicking **BizTalk Server Administration** in the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="96926-108">En la consola de administración de BizTalk Server, expanda el **administración de BizTalk Server** nodo, la **grupo de BizTalk** nodo, la **aplicaciones** nodo y, a continuación, el **BizTalk Application 1** nodo.</span><span class="sxs-lookup"><span data-stu-id="96926-108">In the BizTalk Server Administration Console, expand the **BizTalk Server Administration** node, then the **BizTalk Group** node, then the **Applications** node, and then the **BizTalk Application 1** node.</span></span>  
  
3.  <span data-ttu-id="96926-109">Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="96926-109">Right-click **Receive Ports**, point to **New**, and then click **One-Way Receive Port**.</span></span>  
  
4.  <span data-ttu-id="96926-110">En el cuadro de diálogo Propiedades de puerto de recepción, en el **nombre** , escriba **MT103_XML_ReceivePort**.</span><span class="sxs-lookup"><span data-stu-id="96926-110">In the Receive Port Properties dialog box, in the **Name** box, type **MT103_XML_ReceivePort**.</span></span>  
  
5.  <span data-ttu-id="96926-111">Haga clic en **aplicar** para enlazar el puerto y, a continuación, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="96926-111">Click **Apply** to bind the port, and then click **OK.**</span></span>  
  
6.  <span data-ttu-id="96926-112">Haga clic en **ubicaciones de recepción**, seleccione **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="96926-112">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
7.  <span data-ttu-id="96926-113">En el, seleccione un cuadro de diálogo de puerto de recepción, haga clic en **MT103_XML_ReceivePort**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="96926-113">In the Select a Receive Port dialog box, click **MT103_XML_ReceivePort**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="96926-114">En el cuadro de diálogo Propiedades de la ubicación de recepción, en el **nombre** , escriba **MT103_XML_ReceiveLocation**.</span><span class="sxs-lookup"><span data-stu-id="96926-114">In the Receive Location Properties dialog box, in the **Name** box, type **MT103_XML_ReceiveLocation**.</span></span>  
  
9. <span data-ttu-id="96926-115">En el **transporte** sección, para la **tipo** cuadro de texto, haga clic en la lista desplegable y, a continuación, seleccione **archivo**.</span><span class="sxs-lookup"><span data-stu-id="96926-115">In the **Transport** section, for the **Type** text box, click the drop-down list, and then select **FILE**.</span></span>  
  
10. <span data-ttu-id="96926-116">Haga clic en el **configurar** situado a la derecha de la lista desplegable de tipo.</span><span class="sxs-lookup"><span data-stu-id="96926-116">Click the **Configure** button to the right of the Type drop-down list.</span></span>  
  
11. <span data-ttu-id="96926-117">En el cuadro de diálogo Propiedades de transporte de archivo, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="96926-117">In the FILE Transport Properties dialog box, click **Browse**.</span></span> <span data-ttu-id="96926-118">Mover a la  **\<unidad\>: \Labs** carpeta y, a continuación, haga clic en **crear nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="96926-118">Move to the **\<drive\>:\Labs** folder, and then click **Make New Folder**.</span></span>  
  
12. <span data-ttu-id="96926-119">En el cuadro de diálogo Buscar carpeta, cree un **entrada** carpeta  **\<unidad\>: \Labs**y, a continuación, cree un **XMLFile** carpeta  **\<unidad\>: \Labs\Inbound**.</span><span class="sxs-lookup"><span data-stu-id="96926-119">In the Browse For Folder dialog box, create an **Inbound** folder in **\<drive\>:\Labs**, and then create an **XMLFile** folder in **\<drive\>:\Labs\Inbound**.</span></span> <span data-ttu-id="96926-120">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="96926-120">Click **OK**.</span></span>  
  
13. <span data-ttu-id="96926-121">En el cuadro de diálogo Propiedades de transporte de archivo, asegúrese de que  **\*.xml** se escribe en el **máscara de archivo** cuadro y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="96926-121">In the FILE Transport Properties dialog box, ensure that **\*.xml** is entered in the **File Mask** box, and then click **OK**.</span></span>  
  
14. <span data-ttu-id="96926-122">En el cuadro de diálogo Propiedades de la ubicación de recepción, asegúrese de que **BizTalkServerApplication** se haya especificado para la **controlador de recepción** cuadro.</span><span class="sxs-lookup"><span data-stu-id="96926-122">In the Receive Location Properties dialog box, ensure that **BizTalkServerApplication** is entered for the **Receive handler** box.</span></span>  
  
15. <span data-ttu-id="96926-123">Para el **canalización de recepción** cuadro, seleccione **XMLReceive** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="96926-123">For the **Receive Pipeline** box, select **XMLReceive** from the drop-down list.</span></span>  
  
16. <span data-ttu-id="96926-124">Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="96926-124">Click **Apply**, and then click **OK**.</span></span>  
  
17. <span data-ttu-id="96926-125">En la consola de administración de BizTalk Server, haga clic en **ubicaciones de recepción**, haga clic en **MT103_XML_ReceiveLocation**y, a continuación, haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="96926-125">In the BizTalk Server Administration Console, click **Receive Locations**, right-click **MT103_XML_ReceiveLocation**, and then click **Enable**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="96926-126">Después de habilitar la ubicación de recepción, BizTalk sondea activamente la carpeta de archivos.</span><span class="sxs-lookup"><span data-stu-id="96926-126">After you enable the receive location, BizTalk actively polls your file folder.</span></span>  
  
 <span data-ttu-id="96926-127">Continúe con [lección 2: agregar el puerto de envío de archivo sin formato](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-a-flat-file-send-port.md).</span><span class="sxs-lookup"><span data-stu-id="96926-127">Proceed to [Lesson 2: Adding the Flat File Send Port](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-a-flat-file-send-port.md).</span></span>