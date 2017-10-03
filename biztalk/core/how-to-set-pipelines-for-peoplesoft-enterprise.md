---
title: "Cómo establecer las canalizaciones para PeopleSoft Enterprise | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- setting pipelines
- pipelines, setting
ms.assetid: 36914615-eac0-47b6-9e66-deeb40d21f10
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69bebce2dadf0bb038b0e8c56ffa544ad02c78ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-pipelines-for-peoplesoft-enterprise"></a><span data-ttu-id="0e394-102">Configuración de canalizaciones para PeopleSoft Enterprise</span><span class="sxs-lookup"><span data-stu-id="0e394-102">How to Set Pipelines for PeopleSoft Enterprise</span></span>
<span data-ttu-id="0e394-103">El Adaptador de Microsoft BizTalk para PeopleSoft Enterprise requiere que seleccione una canalización apropiada.</span><span class="sxs-lookup"><span data-stu-id="0e394-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise requires that you select an appropriate pipeline.</span></span>  
  
## <a name="setting-pipelines"></a><span data-ttu-id="0e394-104">Configuración de canalizaciones</span><span class="sxs-lookup"><span data-stu-id="0e394-104">Setting Pipelines</span></span>  
  
#### <a name="to-set-pipelines"></a><span data-ttu-id="0e394-105">Para establecer las canalizaciones</span><span class="sxs-lookup"><span data-stu-id="0e394-105">To set pipelines</span></span>  
  
1.  <span data-ttu-id="0e394-106">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el deseado aplicación.</span><span class="sxs-lookup"><span data-stu-id="0e394-106">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="0e394-107">Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.</span><span class="sxs-lookup"><span data-stu-id="0e394-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="0e394-108">En el **propiedades de puerto de envío** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0e394-108">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="0e394-109">Escriba un nombre para el puerto de envío, por ejemplo, `SSOSendToPeopleSoft`.</span><span class="sxs-lookup"><span data-stu-id="0e394-109">Type a name for the send port, for example, `SSOSendToPeopleSoft`.</span></span>  
  
    2.  <span data-ttu-id="0e394-110">Desde el **tipo** lista desplegable, seleccione **PeopleSoft**.</span><span class="sxs-lookup"><span data-stu-id="0e394-110">From the **Type** drop-down list, select **PeopleSoft**.</span></span>  
  
    3.  <span data-ttu-id="0e394-111">Desde el **controlador de envío** lista desplegable, seleccione el URI.</span><span class="sxs-lookup"><span data-stu-id="0e394-111">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="0e394-112">En la lista desplegable de canalización de envío, seleccione **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="0e394-112">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="0e394-113">Desde el **canalización de recepción** lista desplegable, seleccione **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span><span class="sxs-lookup"><span data-stu-id="0e394-113">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
4.  <span data-ttu-id="0e394-114">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0e394-114">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e394-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e394-115">See Also</span></span>  
 [<span data-ttu-id="0e394-116">Crear controladores de envío de PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="0e394-116">Creating PeopleSoft Send Handlers</span></span>](../core/creating-peoplesoft-send-handlers.md)