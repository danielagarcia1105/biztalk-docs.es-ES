---
title: "Cómo establecer envío canalizaciones para TIBCO Enterprise Message Service | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send pipelines
- setting send pipelines
- pipelines, send
ms.assetid: 6a84d874-4b4d-4b23-913f-f5c72af1e96e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d037782e2580d52c6609c3669e2805aae92ce9eb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-send-pipelines-for-tibco-enterprise-message-service"></a><span data-ttu-id="b1860-102">Configuración de canalizaciones de recepción para TIBCO Enterprise Message Service</span><span class="sxs-lookup"><span data-stu-id="b1860-102">How to Set Send Pipelines for TIBCO Enterprise Message Service</span></span>
<span data-ttu-id="b1860-103">El adaptador de Microsoft BizTalk para TIBCO Enterprise Message Service requiere que seleccione XMLTransmit y XMLReceive para las canalizaciones de envío y recepción, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="b1860-103">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service requires that you select XMLTransmit and XMLReceive for the Send and Receive pipelines respectively.</span></span>  
  
### <a name="to-set-pipelines"></a><span data-ttu-id="b1860-104">Para establecer las canalizaciones</span><span class="sxs-lookup"><span data-stu-id="b1860-104">To set pipelines</span></span>  
  
1.  <span data-ttu-id="b1860-105">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el deseado aplicación.</span><span class="sxs-lookup"><span data-stu-id="b1860-105">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="b1860-106">Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.</span><span class="sxs-lookup"><span data-stu-id="b1860-106">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="b1860-107">En el **propiedades de puerto de envío** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b1860-107">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="b1860-108">Escriba un nombre para el puerto de envío, por ejemplo, `SendToTIBCOEMS`.</span><span class="sxs-lookup"><span data-stu-id="b1860-108">Type a name for the send port, for example, `SendToTIBCOEMS`.</span></span>  
  
    2.  <span data-ttu-id="b1860-109">Desde el **tipo** lista desplegable, seleccione **TIBCO EMS**.</span><span class="sxs-lookup"><span data-stu-id="b1860-109">From the **Type** drop-down list, select **TIBCO EMS**.</span></span>  
  
    3.  <span data-ttu-id="b1860-110">Desde el **controlador de envío** lista desplegable, seleccione el URI.</span><span class="sxs-lookup"><span data-stu-id="b1860-110">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="b1860-111">En la lista desplegable de canalización de envío, seleccione **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="b1860-111">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="b1860-112">Desde el **canalización de recepción** lista desplegable, seleccione **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span><span class="sxs-lookup"><span data-stu-id="b1860-112">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
4.  <span data-ttu-id="b1860-113">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b1860-113">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1860-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1860-114">See Also</span></span>  
 [<span data-ttu-id="b1860-115">Cómo configurar canalizaciones de recepción para TIBCO Enterprise Message Service</span><span class="sxs-lookup"><span data-stu-id="b1860-115">How to Set Receive Pipelines for TIBCO Enterprise Message Service</span></span>](../core/how-to-set-receive-pipelines-for-tibco-enterprise-message-service.md)