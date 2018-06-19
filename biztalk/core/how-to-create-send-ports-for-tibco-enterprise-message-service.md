---
redirect_url: /biztalk/core/creating-tibco-enterprise-message-service-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 6b15d9d03ef967bcf7189ef756da8fc63a0eb3f6
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013683"
---
# <a name="how-to-create-send-ports-for-tibco-enterprise-message-service"></a><span data-ttu-id="6fed4-101">Creación de puertos de envío para TIBCO Enterprise Message Service</span><span class="sxs-lookup"><span data-stu-id="6fed4-101">How to Create Send Ports for TIBCO Enterprise Message Service</span></span>
<span data-ttu-id="6fed4-102">Siga estos pasos para crear un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="6fed4-102">Follow these steps to create a send port.</span></span>  
  
## <a name="creating-a-send-port"></a><span data-ttu-id="6fed4-103">Crear un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="6fed4-103">Creating a Send Port</span></span>  
  
#### <a name="to-create-a-send-port"></a><span data-ttu-id="6fed4-104">Procedimiento para crear un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="6fed4-104">To create a send port</span></span>  
  
1.  <span data-ttu-id="6fed4-105">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el deseado aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fed4-105">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="6fed4-106">Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.</span><span class="sxs-lookup"><span data-stu-id="6fed4-106">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="6fed4-107">En el **propiedades de puerto de envío** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6fed4-107">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="6fed4-108">Escriba un nombre para el puerto de envío, por ejemplo, `SendToTIBCOEMS`.</span><span class="sxs-lookup"><span data-stu-id="6fed4-108">Type a name for the send port, for example, `SendToTIBCOEMS`.</span></span>  
  
    2.  <span data-ttu-id="6fed4-109">Desde el **tipo** lista desplegable, seleccione **TIBCO EMS**.</span><span class="sxs-lookup"><span data-stu-id="6fed4-109">From the **Type** drop-down list, select **TIBCO EMS**.</span></span>  
  
    3.  <span data-ttu-id="6fed4-110">Desde el **controlador de envío** lista desplegable, seleccione el URI.</span><span class="sxs-lookup"><span data-stu-id="6fed4-110">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="6fed4-111">En la lista desplegable de canalización de envío, seleccione **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="6fed4-111">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="6fed4-112">Desde el **canalización de recepción** lista desplegable, seleccione **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span><span class="sxs-lookup"><span data-stu-id="6fed4-112">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
    6.  <span data-ttu-id="6fed4-113">Haga clic en **configurar** para configurar el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="6fed4-113">Click **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="6fed4-114">En el **propiedades de transporte de TIBCO EMS** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6fed4-114">In the **TIBCO EMS Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="6fed4-115">Escriba **el control de mensajes**, **definición de conexión de servidor**, **compatibilidad con transacciones**, **nombre de usuario**y el  **contraseña**.</span><span class="sxs-lookup"><span data-stu-id="6fed4-115">Enter **Message Handling**, **Server Connection Definition**, **Transaction Support**, **Username**, and the **password**.</span></span>  
  
         <span data-ttu-id="6fed4-116">No tiene que establecer la información de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="6fed4-116">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="6fed4-117">En la lista, seleccione la aplicación afiliada que ha creado para representar el sistema TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="6fed4-117">In the list, select the affiliate application you created to represent the TIBCO EMS system.</span></span>  
  
    3.  <span data-ttu-id="6fed4-118">Para **usar SSO**, seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="6fed4-118">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="6fed4-119">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6fed4-119">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="6fed4-120">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6fed4-120">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fed4-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="6fed4-121">See Also</span></span>  
  [<span data-ttu-id="6fed4-122">Creación de controladores de envío de TIBCO Enterprise Message Service</span><span class="sxs-lookup"><span data-stu-id="6fed4-122">Creating  TIBCO Enterprise Message Service Send Handlers</span></span>](../core/creating-tibco-enterprise-message-service-send-handlers.md)