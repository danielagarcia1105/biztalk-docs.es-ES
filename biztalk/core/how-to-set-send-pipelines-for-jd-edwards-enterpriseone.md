---
title: "Cómo establecer envío canalizaciones para JD Edwards EnterpriseOne | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, send pipelines
- send pipelines, configuring [JD Edwards EnterpriseOne adapters]
- adapters [JD Edwards EnterpriseOne adapters], configuring
- adapters [JD Edwards EnterpriseOne adapters], send pipelines
- JD Edwards EnterpriseOne adapters, configuring
ms.assetid: 4cfcecc1-febe-47c8-b75f-2b84defcdbbc
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c9a6337195c8050afca1f12a015ec492db7f7ae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-send-pipelines-for-jd-edwards-enterpriseone"></a><span data-ttu-id="0d4a6-102">Establecimiento de canalizaciones de envío para JD Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="0d4a6-102">How to Set Send Pipelines for JD Edwards EnterpriseOne</span></span>
<span data-ttu-id="0d4a6-103">Microsoft BizTalk Adapter para JD Edwards EnterpriseOne requiere que seleccione **XMLTransmit** y **XMLReceive** para el envío y las canalizaciones de recepción respectivamente.</span><span class="sxs-lookup"><span data-stu-id="0d4a6-103">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne requires that you select **XMLTransmit** and **XMLReceive** for the send and receive pipelines respectively.</span></span>  
  
### <a name="to-set-pipelines"></a><span data-ttu-id="0d4a6-104">Para establecer las canalizaciones</span><span class="sxs-lookup"><span data-stu-id="0d4a6-104">To set pipelines</span></span>  
  
1.  <span data-ttu-id="0d4a6-105">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el deseado aplicación.</span><span class="sxs-lookup"><span data-stu-id="0d4a6-105">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="0d4a6-106">Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.</span><span class="sxs-lookup"><span data-stu-id="0d4a6-106">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="0d4a6-107">En el **propiedades de puerto de envío** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0d4a6-107">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="0d4a6-108">Escriba un nombre para el puerto de envío, por ejemplo, `SendToJDEEnterpriseOne`.</span><span class="sxs-lookup"><span data-stu-id="0d4a6-108">Type a name for the send port, for example, `SendToJDEEnterpriseOne`.</span></span>  
  
    2.  <span data-ttu-id="0d4a6-109">Desde el **tipo** lista desplegable, seleccione **JDE EnterpriseOne**.</span><span class="sxs-lookup"><span data-stu-id="0d4a6-109">From the **Type** drop-down list, select **JDE EnterpriseOne**.</span></span>  
  
    3.  <span data-ttu-id="0d4a6-110">Desde el **controlador de envío** lista desplegable, seleccione el URI.</span><span class="sxs-lookup"><span data-stu-id="0d4a6-110">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="0d4a6-111">En la lista desplegable de canalización de envío, seleccione **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="0d4a6-111">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="0d4a6-112">Desde el **canalización de recepción** lista desplegable, seleccione **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span><span class="sxs-lookup"><span data-stu-id="0d4a6-112">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
4.  <span data-ttu-id="0d4a6-113">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0d4a6-113">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d4a6-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d4a6-114">See Also</span></span>  
 [<span data-ttu-id="0d4a6-115">Crear controladores de JD Edwards EnterpriseOne envío</span><span class="sxs-lookup"><span data-stu-id="0d4a6-115">Creating JD Edwards EnterpriseOne Send Handlers</span></span>](../core/creating-jd-edwards-enterpriseone-send-handlers.md)