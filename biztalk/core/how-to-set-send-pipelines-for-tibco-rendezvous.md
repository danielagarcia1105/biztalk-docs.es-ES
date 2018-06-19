---
redirect_url: /biztalk/core/creating-tibco-rendezvous-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 72cdd3553289df39442b71730a61e3271db381e7
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013147"
---
# <a name="how-to-set-send-pipelines-for-tibco-rendezvous"></a><span data-ttu-id="8c287-101">Establecimiento de canalizaciones de envío para TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="8c287-101">How to Set Send Pipelines for TIBCO Rendezvous</span></span>
<span data-ttu-id="8c287-102">Microsoft BizTalk Adapter para TIBCO Rendezvous requiere que seleccione XMLTransmit y XMLReceive para las canalizaciones de envío y recepción respectivamente.</span><span class="sxs-lookup"><span data-stu-id="8c287-102">Microsoft BizTalk Adapter for TIBCO Rendezvous requires that you select XMLTransmit and XMLReceive for the send and receive pipelines respectively.</span></span>  
  
### <a name="to-set-pipelines"></a><span data-ttu-id="8c287-103">Para establecer las canalizaciones</span><span class="sxs-lookup"><span data-stu-id="8c287-103">To set pipelines</span></span>  
  
1.  <span data-ttu-id="8c287-104">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el deseado aplicación.</span><span class="sxs-lookup"><span data-stu-id="8c287-104">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="8c287-105">Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.</span><span class="sxs-lookup"><span data-stu-id="8c287-105">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="8c287-106">En el **propiedades de puerto de envío** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8c287-106">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="8c287-107">Escriba un nombre para el puerto de envío, por ejemplo, `SendToTIBCORV`.</span><span class="sxs-lookup"><span data-stu-id="8c287-107">Type a name for the send port, for example, `SendToTIBCORV`.</span></span>  
  
    2.  <span data-ttu-id="8c287-108">Desde el **tipo** lista desplegable, seleccione **TIBCO Rendezvous**.</span><span class="sxs-lookup"><span data-stu-id="8c287-108">From the **Type** drop-down list, select **TIBCO Rendezvous**.</span></span>  
  
    3.  <span data-ttu-id="8c287-109">Desde el **controlador de envío** lista desplegable, seleccione el URI.</span><span class="sxs-lookup"><span data-stu-id="8c287-109">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="8c287-110">En la lista desplegable de canalización de envío, seleccione **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="8c287-110">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="8c287-111">Desde el **canalización de recepción** lista desplegable, seleccione **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span><span class="sxs-lookup"><span data-stu-id="8c287-111">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
4.  <span data-ttu-id="8c287-112">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8c287-112">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c287-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c287-113">See Also</span></span>  
 <span data-ttu-id="8c287-114">[Crear controladores de envío TIBCO Rendezvous](../core/creating-tibco-rendezvous-send-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="8c287-114">[Creating TIBCO Rendezvous Send Handlers](../core/creating-tibco-rendezvous-send-handlers.md) </span></span>  
 [<span data-ttu-id="8c287-115">Creación de controladores de recepción de TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="8c287-115">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)