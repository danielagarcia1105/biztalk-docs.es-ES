---
title: "Cómo establecer envío canalizaciones para TIBCO Rendezvous | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send pipelines
- pipelines, send
ms.assetid: a28a02c1-6f30-4749-b819-c1e707757680
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48d3a72c2282e335f2d3e020ec0e77a8b7afbd35
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-send-pipelines-for-tibco-rendezvous"></a><span data-ttu-id="163f9-102">Establecimiento de canalizaciones de envío para TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="163f9-102">How to Set Send Pipelines for TIBCO Rendezvous</span></span>
<span data-ttu-id="163f9-103">Microsoft BizTalk Adapter para TIBCO Rendezvous requiere que seleccione XMLTransmit y XMLReceive para las canalizaciones de envío y recepción respectivamente.</span><span class="sxs-lookup"><span data-stu-id="163f9-103">Microsoft BizTalk Adapter for TIBCO Rendezvous requires that you select XMLTransmit and XMLReceive for the send and receive pipelines respectively.</span></span>  
  
### <a name="to-set-pipelines"></a><span data-ttu-id="163f9-104">Para establecer las canalizaciones</span><span class="sxs-lookup"><span data-stu-id="163f9-104">To set pipelines</span></span>  
  
1.  <span data-ttu-id="163f9-105">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el deseado aplicación.</span><span class="sxs-lookup"><span data-stu-id="163f9-105">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="163f9-106">Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.</span><span class="sxs-lookup"><span data-stu-id="163f9-106">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="163f9-107">En el **propiedades de puerto de envío** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="163f9-107">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="163f9-108">Escriba un nombre para el puerto de envío, por ejemplo, `SendToTIBCORV`.</span><span class="sxs-lookup"><span data-stu-id="163f9-108">Type a name for the send port, for example, `SendToTIBCORV`.</span></span>  
  
    2.  <span data-ttu-id="163f9-109">Desde el **tipo** lista desplegable, seleccione **TIBCO Rendezvous**.</span><span class="sxs-lookup"><span data-stu-id="163f9-109">From the **Type** drop-down list, select **TIBCO Rendezvous**.</span></span>  
  
    3.  <span data-ttu-id="163f9-110">Desde el **controlador de envío** lista desplegable, seleccione el URI.</span><span class="sxs-lookup"><span data-stu-id="163f9-110">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="163f9-111">En la lista desplegable de canalización de envío, seleccione **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="163f9-111">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="163f9-112">Desde el **canalización de recepción** lista desplegable, seleccione **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span><span class="sxs-lookup"><span data-stu-id="163f9-112">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
4.  <span data-ttu-id="163f9-113">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="163f9-113">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="163f9-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="163f9-114">See Also</span></span>  
 <span data-ttu-id="163f9-115">[Crear controladores de envío TIBCO Rendezvous](../core/creating-tibco-rendezvous-send-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="163f9-115">[Creating TIBCO Rendezvous Send Handlers](../core/creating-tibco-rendezvous-send-handlers.md) </span></span>  
 [<span data-ttu-id="163f9-116">Controladores de recepción de creación TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="163f9-116">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)