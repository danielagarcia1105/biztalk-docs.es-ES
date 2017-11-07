---
redirect_url: /biztalk/core/creating-peoplesoft-send-handlers/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: e5f68232aa0cb59835523df0afac01f3d1949489
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-set-pipelines-for-peoplesoft-enterprise"></a><span data-ttu-id="f5ecd-101">Configuración de canalizaciones para PeopleSoft Enterprise</span><span class="sxs-lookup"><span data-stu-id="f5ecd-101">How to Set Pipelines for PeopleSoft Enterprise</span></span>
<span data-ttu-id="f5ecd-102">El Adaptador de Microsoft BizTalk para PeopleSoft Enterprise requiere que seleccione una canalización apropiada.</span><span class="sxs-lookup"><span data-stu-id="f5ecd-102">Microsoft BizTalk Adapter for PeopleSoft Enterprise requires that you select an appropriate pipeline.</span></span>  
  
## <a name="setting-pipelines"></a><span data-ttu-id="f5ecd-103">Configuración de canalizaciones</span><span class="sxs-lookup"><span data-stu-id="f5ecd-103">Setting Pipelines</span></span>  
  
#### <a name="to-set-pipelines"></a><span data-ttu-id="f5ecd-104">Para establecer las canalizaciones</span><span class="sxs-lookup"><span data-stu-id="f5ecd-104">To set pipelines</span></span>  
  
1.  <span data-ttu-id="f5ecd-105">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el deseado aplicación.</span><span class="sxs-lookup"><span data-stu-id="f5ecd-105">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="f5ecd-106">Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.</span><span class="sxs-lookup"><span data-stu-id="f5ecd-106">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="f5ecd-107">En el **propiedades de puerto de envío** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f5ecd-107">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="f5ecd-108">Escriba un nombre para el puerto de envío, por ejemplo, `SSOSendToPeopleSoft`.</span><span class="sxs-lookup"><span data-stu-id="f5ecd-108">Type a name for the send port, for example, `SSOSendToPeopleSoft`.</span></span>  
  
    2.  <span data-ttu-id="f5ecd-109">Desde el **tipo** lista desplegable, seleccione **PeopleSoft**.</span><span class="sxs-lookup"><span data-stu-id="f5ecd-109">From the **Type** drop-down list, select **PeopleSoft**.</span></span>  
  
    3.  <span data-ttu-id="f5ecd-110">Desde el **controlador de envío** lista desplegable, seleccione el URI.</span><span class="sxs-lookup"><span data-stu-id="f5ecd-110">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="f5ecd-111">En la lista desplegable de canalización de envío, seleccione **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="f5ecd-111">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="f5ecd-112">Desde el **canalización de recepción** lista desplegable, seleccione **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span><span class="sxs-lookup"><span data-stu-id="f5ecd-112">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
4.  <span data-ttu-id="f5ecd-113">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f5ecd-113">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5ecd-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5ecd-114">See Also</span></span>  
 [<span data-ttu-id="f5ecd-115">Creación de controladores de envío de PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="f5ecd-115">Creating PeopleSoft Send Handlers</span></span>](../core/creating-peoplesoft-send-handlers.md)