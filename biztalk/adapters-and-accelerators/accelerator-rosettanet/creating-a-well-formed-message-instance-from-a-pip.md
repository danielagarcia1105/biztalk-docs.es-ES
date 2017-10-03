---
title: Crear una instancia de mensaje correcto a partir de un PIP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message templates
- PIPs, message templates
ms.assetid: fed3698c-25d9-40ca-878a-60171f425bec
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e16020afb17d17c8add8e973ade0cd0c5cfcbbc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-a-well-formed-message-instance-from-a-pip"></a><span data-ttu-id="920cf-102">Crear una instancia de mensaje correcto a partir de un PIP</span><span class="sxs-lookup"><span data-stu-id="920cf-102">Creating a Well-Formed Message Instance from a PIP</span></span>
<span data-ttu-id="920cf-103">En este tema se describe cómo generar una instancia de mensaje correcto.</span><span class="sxs-lookup"><span data-stu-id="920cf-103">This topic describes how to produce a well-formed message instance.</span></span> <span data-ttu-id="920cf-104">Puede generar una plantilla para una instancia de mensaje a partir del Proceso de interfaz de socio (PIP).</span><span class="sxs-lookup"><span data-stu-id="920cf-104">You can generate a template for a message instance from the Partner Interface Process (PIP).</span></span> <span data-ttu-id="920cf-105">Después de hacerlo, debe modificar la plantilla para que sea correcta antes de agregar los datos.</span><span class="sxs-lookup"><span data-stu-id="920cf-105">After doing this, you have to modify that template, so that it is well formed, before adding your data.</span></span>  
  
### <a name="to-generate-a-message-instance-template-from-the-pip"></a><span data-ttu-id="920cf-106">Para generar una plantilla de instancia de mensaje a partir del PIP</span><span class="sxs-lookup"><span data-stu-id="920cf-106">To generate a message instance template from the PIP</span></span>  
  
1.  <span data-ttu-id="920cf-107">Inicie **Microsoft Visual Studio 2012**.</span><span class="sxs-lookup"><span data-stu-id="920cf-107">Start **Microsoft Visual Studio 2012**.</span></span>  
  
2.  <span data-ttu-id="920cf-108">En el menú **Archivo** , seleccione **Abrir**y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="920cf-108">On the **File** menu, point to **Open**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="920cf-109">Busque \< *unidad*> \Program BizTalk \<versión > Accelerator for RosettaNetSDK\Schemas, haga clic en **RNPIPs.btproj**y, a continuación, haga clic en **Abiertos**.</span><span class="sxs-lookup"><span data-stu-id="920cf-109">Locate \<*drive*>\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNetSDK\Schemas, click **RNPIPs.btproj**, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="920cf-110">En el Explorador de soluciones, expanda **RNPIP**y haga clic con el botón derecho en el PIP para el que desea crear una instancia.</span><span class="sxs-lookup"><span data-stu-id="920cf-110">In Solution Explorer, expand **RNPIPs**, and then right-click the PIP for which you want to create an instance.</span></span>  
  
5.  <span data-ttu-id="920cf-111">Haga clic en **Generar instancia**.</span><span class="sxs-lookup"><span data-stu-id="920cf-111">Click **Generate Instance**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="920cf-112">De este modo se genera un archivo con el nombre del PIP, con "_output" anexado al nombre de archivo y una extensión .xml.</span><span class="sxs-lookup"><span data-stu-id="920cf-112">This generates a file named after the PIP, with "_output" appended to the file name, and with an .xml extension.</span></span> <span data-ttu-id="920cf-113">Una instrucción en el panel de salida indica dónde [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] generó la instancia.</span><span class="sxs-lookup"><span data-stu-id="920cf-113">A statement in the Output pane indicates where [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] generated the instance.</span></span>  
  
### <a name="to-modify-the-message-instance-template"></a><span data-ttu-id="920cf-114">Para modificar la plantilla de instancia de mensaje</span><span class="sxs-lookup"><span data-stu-id="920cf-114">To modify the message instance template</span></span>  
  
1.  <span data-ttu-id="920cf-115">En [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, busque la carpeta que contiene el archivo XML y haga doble clic en el nombre de archivo para abrir la carpeta.</span><span class="sxs-lookup"><span data-stu-id="920cf-115">In [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, locate the folder holding the XML file, and double-click the file name to open the folder.</span></span>  
  
2.  <span data-ttu-id="920cf-116">Agregue una etiqueta de encabezado XML antes del resto del texto que indique la versión del XML y la codificación.</span><span class="sxs-lookup"><span data-stu-id="920cf-116">Add an XML header tag before all other text indicating the version of XML and the encoding.</span></span> <span data-ttu-id="920cf-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="920cf-117">For example:</span></span>  
  
    ```  
    <?xml version="1.0" encoding="UTF-8" ?>  
    ```  
  
3.  <span data-ttu-id="920cf-118">Después de la línea que acaba de agregar, agregue una línea DOCTYPE que indique la DTD.</span><span class="sxs-lookup"><span data-stu-id="920cf-118">After the line that you just added, add a DOCTYPE line indicating the DTD.</span></span> <span data-ttu-id="920cf-119">Por ejemplo, para una instancia de solicitud de pedido de compra 3A4, la línea sería como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="920cf-119">For example, for a 3A4 Purchase Order Request instance, the line would be as follows:</span></span>  
  
    ```  
    <!DOCTYPE Pip3A4PurchaseOrderRequest SYSTEM "3A4_MS_V02_02_PurchaseOrderRequest.dtd">  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="920cf-120">Cada instancia de mensaje debe incluir la línea DOCTYPE que va a procesarse.</span><span class="sxs-lookup"><span data-stu-id="920cf-120">Each message instance must include the DOCTYPE line to be processed.</span></span>  
  
4.  <span data-ttu-id="920cf-121">Ahora puede personalizar esta instancia de mensaje para adaptarla a sus necesidades empresariales.</span><span class="sxs-lookup"><span data-stu-id="920cf-121">You may now customize this message instance to suit your business needs.</span></span> <span data-ttu-id="920cf-122">Modifique la instancia XML de modo que no use espacios de nombres XML o prefijos de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="920cf-122">Modify the XML instance so that it does not use XML namespaces or namespace prefixes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="920cf-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="920cf-123">See Also</span></span>  
 [<span data-ttu-id="920cf-124">Guía de programación</span><span class="sxs-lookup"><span data-stu-id="920cf-124">Programming Guide</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)