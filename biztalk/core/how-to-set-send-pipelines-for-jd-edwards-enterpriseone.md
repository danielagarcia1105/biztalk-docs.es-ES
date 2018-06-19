---
redirect_url: /biztalk/core/adding-biztalk-adapter-for-jd-edwards-enterpriseone/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 263f1f5d9441a30687df3e1a7a1170b7bf35e2fc
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015075"
---
# <a name="how-to-set-send-pipelines-for-jd-edwards-enterpriseone"></a><span data-ttu-id="b4577-101">Establecimiento de canalizaciones de envío para JD Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="b4577-101">How to Set Send Pipelines for JD Edwards EnterpriseOne</span></span>
<span data-ttu-id="b4577-102">Microsoft BizTalk Adapter para JD Edwards EnterpriseOne requiere que seleccione **XMLTransmit** y **XMLReceive** para el envío y las canalizaciones de recepción respectivamente.</span><span class="sxs-lookup"><span data-stu-id="b4577-102">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne requires that you select **XMLTransmit** and **XMLReceive** for the send and receive pipelines respectively.</span></span>  
  
### <a name="to-set-pipelines"></a><span data-ttu-id="b4577-103">Para establecer las canalizaciones</span><span class="sxs-lookup"><span data-stu-id="b4577-103">To set pipelines</span></span>  
  
1.  <span data-ttu-id="b4577-104">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el deseado aplicación.</span><span class="sxs-lookup"><span data-stu-id="b4577-104">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="b4577-105">Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.</span><span class="sxs-lookup"><span data-stu-id="b4577-105">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="b4577-106">En el **propiedades de puerto de envío** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4577-106">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="b4577-107">Escriba un nombre para el puerto de envío, por ejemplo, `SendToJDEEnterpriseOne`.</span><span class="sxs-lookup"><span data-stu-id="b4577-107">Type a name for the send port, for example, `SendToJDEEnterpriseOne`.</span></span>  
  
    2.  <span data-ttu-id="b4577-108">Desde el **tipo** lista desplegable, seleccione **JDE EnterpriseOne**.</span><span class="sxs-lookup"><span data-stu-id="b4577-108">From the **Type** drop-down list, select **JDE EnterpriseOne**.</span></span>  
  
    3.  <span data-ttu-id="b4577-109">Desde el **controlador de envío** lista desplegable, seleccione el URI.</span><span class="sxs-lookup"><span data-stu-id="b4577-109">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="b4577-110">En la lista desplegable de canalización de envío, seleccione **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="b4577-110">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="b4577-111">Desde el **canalización de recepción** lista desplegable, seleccione **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span><span class="sxs-lookup"><span data-stu-id="b4577-111">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
4.  <span data-ttu-id="b4577-112">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b4577-112">Click **OK**.</span></span>  
  
