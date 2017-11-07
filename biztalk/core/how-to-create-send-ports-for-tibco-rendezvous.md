---
redirect_url: /biztalk/core/creating-tibco-rendezvous-send-handlers/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 44da7839f0bee96db332dada214bdbc503067f56
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-create-send-ports-for-tibco-rendezvous"></a><span data-ttu-id="1b9fe-101">Creación de puertos de envío para TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="1b9fe-101">How to Create Send Ports for TIBCO Rendezvous</span></span>
<span data-ttu-id="1b9fe-102">Siga estos pasos para crear un puerto de envío mediante [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b9fe-102">Follow these steps to create a send port using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
### <a name="to-create-a-send-port"></a><span data-ttu-id="1b9fe-103">Procedimiento para crear un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="1b9fe-103">To create a send port</span></span>  
  
1.  <span data-ttu-id="1b9fe-104">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el deseado aplicación.</span><span class="sxs-lookup"><span data-stu-id="1b9fe-104">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="1b9fe-105">Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.</span><span class="sxs-lookup"><span data-stu-id="1b9fe-105">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="1b9fe-106">En el **propiedades de puerto de envío** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1b9fe-106">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="1b9fe-107">Escriba un nombre para el puerto de envío, por ejemplo, `SendToTIBCORV`.</span><span class="sxs-lookup"><span data-stu-id="1b9fe-107">Type a name for the send port, for example, `SendToTIBCORV`.</span></span>  
  
    2.  <span data-ttu-id="1b9fe-108">Desde el **tipo** lista desplegable, seleccione **TIBCO Rendezvous**.</span><span class="sxs-lookup"><span data-stu-id="1b9fe-108">From the **Type** drop-down list, select **TIBCO Rendezvous**.</span></span>  
  
    3.  <span data-ttu-id="1b9fe-109">Desde el **controlador de envío** lista desplegable, seleccione el URI.</span><span class="sxs-lookup"><span data-stu-id="1b9fe-109">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="1b9fe-110">Desde el **canalización de envío** lista desplegable, seleccione **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="1b9fe-110">From the **Send Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span> <span data-ttu-id="1b9fe-111">Desde el **canalización de recepción** lista desplegable, seleccione **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span><span class="sxs-lookup"><span data-stu-id="1b9fe-111">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
    6.  <span data-ttu-id="1b9fe-112">Haga clic en **configurar** para configurar el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="1b9fe-112">Click **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="1b9fe-113">En el **propiedades de transporte de TIBCO Rendezvous** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1b9fe-113">In the **TIBCO Rendezvous Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="1b9fe-114">Especifique las propiedades.</span><span class="sxs-lookup"><span data-stu-id="1b9fe-114">Enter the properties.</span></span>  
  
         <span data-ttu-id="1b9fe-115">No tiene que establecer la información de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="1b9fe-115">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="1b9fe-116">En la lista, seleccione la aplicación afiliada de SSO que ha creado para representar el sistema TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="1b9fe-116">In the list, select the SSO affiliate application you created to represent the TIBCO Rendezvous system.</span></span>  
  
    3.  <span data-ttu-id="1b9fe-117">Para **usar SSO**, seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="1b9fe-117">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="1b9fe-118">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1b9fe-118">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="1b9fe-119">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1b9fe-119">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b9fe-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b9fe-120">See Also</span></span>  
 [<span data-ttu-id="1b9fe-121">Creación de controladores de envío de TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="1b9fe-121">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)