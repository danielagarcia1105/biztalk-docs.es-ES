---
title: "Cómo establecer las canalizaciones de JD Edwards OneWorld | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive pipelines
- send pipelines
- setting pipelines
- pipelines, setting
ms.assetid: 821d4081-a2d4-4957-abc0-d6370e719ba8
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e45ec6f6eb3be74e150e77de9ef6dbbe461a361a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-jd-edwards-oneworld-pipelines"></a><span data-ttu-id="f58fc-102">Establecimiento de canalizaciones de JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="f58fc-102">How to Set JD Edwards OneWorld Pipelines</span></span>
<span data-ttu-id="f58fc-103">Microsoft BizTalk Adapter para JD Edwards OneWorld necesita que seleccione XMLTransmit y XMLReceive para las canalizaciones de envío y recepción respectivamente.</span><span class="sxs-lookup"><span data-stu-id="f58fc-103">Microsoft BizTalk Adapter for JD Edwards OneWorld requires that you select XMLTransmit and XMLReceive for the send and receive pipelines respectively.</span></span>  
  
### <a name="to-set-pipelines"></a><span data-ttu-id="f58fc-104">Para establecer las canalizaciones</span><span class="sxs-lookup"><span data-stu-id="f58fc-104">To set pipelines</span></span>  
  
1.  <span data-ttu-id="f58fc-105">En el **iniciar** menú, elija **archivos de programa**, seleccione **Microsoft BizTalk Server** y, a continuación, haga clic en **administración de BizTalk Server** Para iniciar la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="f58fc-105">On the **Start** menu, point to **Program Files**, point to **Microsoft BizTalk Server** , and then click **BizTalk Server Administration** to start the BizTalk Server Administration Console.</span></span>  
  
2.  <span data-ttu-id="f58fc-106">Expanda Administración de BizTalk Server, **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda la aplicación deseada.</span><span class="sxs-lookup"><span data-stu-id="f58fc-106">Expand BizTalk Server Administration, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
3.  <span data-ttu-id="f58fc-107">Seleccione **puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="f58fc-107">Select **Send Ports**.</span></span> <span data-ttu-id="f58fc-108">En el panel de detalles, haga clic en el puerto de envío seleccionado y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f58fc-108">In the details pane, right-click the selected send port and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="f58fc-109">En el **propiedades de puertos de envío** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f58fc-109">In the **Send Ports Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="f58fc-110">Seleccione la canalización de envío de la **canalización de envío** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="f58fc-110">Select the send pipeline from the **Send Pipeline** drop-down list.</span></span>  
  
    2.  <span data-ttu-id="f58fc-111">Seleccione la canalización de recepción de la **canalización de recepción** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="f58fc-111">Select the Receive pipeline from the **Receive Pipeline** drop-down list.</span></span>  
  
5.  <span data-ttu-id="f58fc-112">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f58fc-112">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f58fc-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f58fc-113">See Also</span></span>  
 [<span data-ttu-id="f58fc-114">Crear controladores de envío de OneWorld JD Edwards</span><span class="sxs-lookup"><span data-stu-id="f58fc-114">Creating JD Edwards OneWorld Send Handlers</span></span>](../core/creating-jd-edwards-oneworld-send-handlers.md)