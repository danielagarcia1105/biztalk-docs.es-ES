---
redirect_url: /biztalk/core/creating-peoplesoft-send-handlers/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: ec518c16383d847bf13706a6469b038b447c1543
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-create-send-ports-for-peoplesoft-enterprise"></a><span data-ttu-id="c6d42-101">Creación de puertos de envío para PeopleSoft Enterprise</span><span class="sxs-lookup"><span data-stu-id="c6d42-101">How to Create Send Ports for PeopleSoft Enterprise</span></span>
<span data-ttu-id="c6d42-102">Siga estos pasos para crear un puerto de envío mediante la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="c6d42-102">Follow these steps to create a send port using BizTalk Server Administration Console.</span></span>  
  
## <a name="creating-a-send-port"></a><span data-ttu-id="c6d42-103">Crear un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="c6d42-103">Creating a Send Port</span></span>  
  
#### <a name="to-create-a-send-port"></a><span data-ttu-id="c6d42-104">Procedimiento para crear un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="c6d42-104">To create a send port</span></span>  
  
1.  <span data-ttu-id="c6d42-105">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el deseado aplicación.</span><span class="sxs-lookup"><span data-stu-id="c6d42-105">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="c6d42-106">Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.</span><span class="sxs-lookup"><span data-stu-id="c6d42-106">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="c6d42-107">En el **propiedades de puerto de envío** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c6d42-107">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="c6d42-108">Escriba un nombre para el puerto de envío, por ejemplo, `SSOSendToPeopleSoft`.</span><span class="sxs-lookup"><span data-stu-id="c6d42-108">Type a name for the send port, for example, `SSOSendToPeopleSoft`.</span></span>  
  
    2.  <span data-ttu-id="c6d42-109">Desde el **tipo** lista desplegable, seleccione **PeopleSoft**.</span><span class="sxs-lookup"><span data-stu-id="c6d42-109">From the **Type** drop-down list, select **PeopleSoft**.</span></span>  
  
    3.  <span data-ttu-id="c6d42-110">Desde el **controlador de envío** lista desplegable, seleccione el URI.</span><span class="sxs-lookup"><span data-stu-id="c6d42-110">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="c6d42-111">En la lista desplegable de canalización de envío, seleccione **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="c6d42-111">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="c6d42-112">Desde el **canalización de recepción** lista desplegable, seleccione **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span><span class="sxs-lookup"><span data-stu-id="c6d42-112">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
    6.  <span data-ttu-id="c6d42-113">Haga clic en **configurar** para configurar el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="c6d42-113">Click **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="c6d42-114">En el **propiedades de transporte de PeopleSoft** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c6d42-114">In the **PeopleSoft Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="c6d42-115">Expanda **propiedades de adaptador necesarias**y escriba **ruta de acceso de servidor de aplicación**, **JAVA_HOME**, **nombre de usuario**,  **contraseña**y el archivo Jar para la conexión en el sistema Peoplesoft.</span><span class="sxs-lookup"><span data-stu-id="c6d42-115">Expand **Adapter Required Properties**, and enter **Application Server Path**, **JAVA_HOME**, **user name**, **password**, and the Jar file for connecting into the Peoplesoft system.</span></span>  
  
         <span data-ttu-id="c6d42-116">No tiene que establecer la información de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="c6d42-116">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="c6d42-117">En la lista, seleccione la aplicación afiliada de SSO que ha creado para representar el sistema PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="c6d42-117">In the list, select the SSO affiliate application you created to represent the PeopleSoft system.</span></span>  
  
    3.  <span data-ttu-id="c6d42-118">Para **usar SSO**, seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="c6d42-118">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="c6d42-119">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c6d42-119">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="c6d42-120">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c6d42-120">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6d42-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6d42-121">See Also</span></span>  
 [<span data-ttu-id="c6d42-122">Creación de controladores de envío de PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="c6d42-122">Creating PeopleSoft Send Handlers</span></span>](../core/creating-peoplesoft-send-handlers.md)