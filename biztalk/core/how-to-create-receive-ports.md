---
redirect_url: /biztalk/core/creating-tibco-rendezvous-receive-handlers/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 0cd93bcd2d1855f137600214b6a07d52b6f52e4f
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-create-receive-ports"></a><span data-ttu-id="eaeaf-101">Cómo crear puertos de recepción</span><span class="sxs-lookup"><span data-stu-id="eaeaf-101">How to Create Receive Ports</span></span>
<span data-ttu-id="eaeaf-102">Siga estos pasos para crear un puerto de recepción mediante Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="eaeaf-102">Follow these steps to create a receive port using Visual Studio.</span></span>  
  
### <a name="to-create-a-receive-port"></a><span data-ttu-id="eaeaf-103">Para crear un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="eaeaf-103">To create a receive port</span></span>  
  
1.  <span data-ttu-id="eaeaf-104">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el deseado aplicación.</span><span class="sxs-lookup"><span data-stu-id="eaeaf-104">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="eaeaf-105">Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puertos de recepción unidireccionales**.</span><span class="sxs-lookup"><span data-stu-id="eaeaf-105">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Ports**.</span></span>  
  
3.  <span data-ttu-id="eaeaf-106">En el **propiedades de puerto de recepción** ventana, en la **General** página, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="eaeaf-106">In the **Receive Port Properties** window, on the **General** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="eaeaf-107">En el **nombre** , escriba `ReceiveFromTIBCORV`.</span><span class="sxs-lookup"><span data-stu-id="eaeaf-107">In the **Name** field, type `ReceiveFromTIBCORV`.</span></span>  
  
    2.  <span data-ttu-id="eaeaf-108">En el **autenticación** cuadro del grupo, especifique cómo se administran los mensajes al utilizar la autenticación.</span><span class="sxs-lookup"><span data-stu-id="eaeaf-108">In the **Authentication** group box, specify how messages are handled when using authentication.</span></span>  
  
    3.  <span data-ttu-id="eaeaf-109">Seleccione el **habilitar enrutamiento para mensajes con errores** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="eaeaf-109">Select the **Enable routing for failed messages** checkbox.</span></span>  
  
4.  <span data-ttu-id="eaeaf-110">En el **ubicaciones de recepción** página, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="eaeaf-110">On the **Receive Locations** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="eaeaf-111">Haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="eaeaf-111">Click **New**.</span></span>  
  
    2.  <span data-ttu-id="eaeaf-112">En el **ubicaciones de recepción** ventana, en la **General** página, escriba el **nombre** de la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="eaeaf-112">In the **Receive Locations** window, on the **General** page, type the **Name** of the receive location.</span></span>  
  
    3.  <span data-ttu-id="eaeaf-113">Desde el **tipo** lista desplegable, seleccione el tipo de transporte y desde el **controlador de recepción** lista desplegable, seleccione la dirección de transporte.</span><span class="sxs-lookup"><span data-stu-id="eaeaf-113">From the **Type** drop-down list, select the transport type, and from the **Receive handler** drop-down list, select the transport address.</span></span>  
  
    4.  <span data-ttu-id="eaeaf-114">Desde el **canalización de recepción** lista desplegable, seleccione la canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="eaeaf-114">From the **Receive pipeline** drop-down list, select the receive pipeline.</span></span>  
  
    5.  <span data-ttu-id="eaeaf-115">En el **programación** página, seleccione la **fecha de inicio** y **fecha de finalización** para restringir la recepción de documentos.</span><span class="sxs-lookup"><span data-stu-id="eaeaf-115">On the **Schedule** page, select the **Start date** and the **End date** to restrict receiving documents.</span></span>  
  
    6.  <span data-ttu-id="eaeaf-116">Seleccione el **habilitar ventana de servicio** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="eaeaf-116">Select the **Enable service window** checkbox.</span></span>  
  
    7.  <span data-ttu-id="eaeaf-117">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="eaeaf-117">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="eaeaf-118">En el **asignaciones de entrada** , seleccione las asignaciones de entrada para transformar documentos en el puerto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="eaeaf-118">On the **Inbound Maps** page, select the inbound maps for transforming documents on the selected port.</span></span>  
  
6.  <span data-ttu-id="eaeaf-119">En el **seguimiento** página, seleccione el seguimiento de cuerpos de mensaje y el seguimiento de propiedades de mensaje deseado.</span><span class="sxs-lookup"><span data-stu-id="eaeaf-119">On the **Tracking** page, select the desired tracking message bodies and tracking message properties.</span></span>  
  
7.  <span data-ttu-id="eaeaf-120">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="eaeaf-120">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaeaf-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="eaeaf-121">See Also</span></span>  
 [<span data-ttu-id="eaeaf-122">Creación de controladores de recepción de TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="eaeaf-122">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)