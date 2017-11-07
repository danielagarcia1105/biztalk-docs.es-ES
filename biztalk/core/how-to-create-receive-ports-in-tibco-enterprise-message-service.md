---
redirect_url: /biztalk/core/creating-tibco-enterprise-message-service-receive-handlers/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: e31246cf90f42206de6a22fcc32338fcb2936db3
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-create-receive-ports-in-tibco-enterprise-message-service"></a><span data-ttu-id="8d1bb-101">Creación de puertos de recepción en TIBCO Enterprise Message Service</span><span class="sxs-lookup"><span data-stu-id="8d1bb-101">How to Create Receive Ports in TIBCO Enterprise Message Service</span></span>
<span data-ttu-id="8d1bb-102">Siga los pasos siguientes para crear un puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="8d1bb-102">Follow these steps to create a receive port.</span></span>  
  
### <a name="to-create-a-receive-port"></a><span data-ttu-id="8d1bb-103">Para crear un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="8d1bb-103">To create a receive port</span></span>  
  
1.  <span data-ttu-id="8d1bb-104">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el deseado aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d1bb-104">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="8d1bb-105">Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puertos de recepción unidireccionales**.</span><span class="sxs-lookup"><span data-stu-id="8d1bb-105">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Ports**.</span></span>  
  
3.  <span data-ttu-id="8d1bb-106">En el **propiedades de puerto de recepción** ventana, en la **General** página, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8d1bb-106">In the **Receive Port Properties** window, on the **General** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="8d1bb-107">En el **nombre** , escriba `ReceiveFromTIBCOEMS`.</span><span class="sxs-lookup"><span data-stu-id="8d1bb-107">In the **Name** field, type `ReceiveFromTIBCOEMS`.</span></span>  
  
    2.  <span data-ttu-id="8d1bb-108">En el **autenticación** cuadro del grupo, especifique cómo se administran los mensajes al utilizar la autenticación.</span><span class="sxs-lookup"><span data-stu-id="8d1bb-108">In the **Authentication** group box, specify how messages are handled when using authentication.</span></span>  
  
    3.  <span data-ttu-id="8d1bb-109">Seleccione el **habilitar enrutamiento para mensajes con errores** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="8d1bb-109">Select the **Enable routing for failed messages** checkbox.</span></span>  
  
4.  <span data-ttu-id="8d1bb-110">En el **ubicaciones de recepción** página, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8d1bb-110">On the **Receive Locations** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="8d1bb-111">Haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="8d1bb-111">Click **New**.</span></span>  
  
    2.  <span data-ttu-id="8d1bb-112">En el **ubicaciones de recepción** ventana, en la **General** página, escriba el **nombre** de la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="8d1bb-112">In the **Receive Locations** window, on the **General** page, type the **Name** of the receive location.</span></span>  
  
    3.  <span data-ttu-id="8d1bb-113">Desde el **tipo** lista desplegable, seleccione el tipo de transporte y desde el **controlador de recepción** lista desplegable, seleccione la dirección de transporte.</span><span class="sxs-lookup"><span data-stu-id="8d1bb-113">From the **Type** drop-down list, select the transport type, and from the **Receive handler** drop-down list, select the transport address.</span></span>  
  
    4.  <span data-ttu-id="8d1bb-114">Desde el **canalización de recepción** lista desplegable, seleccione la canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="8d1bb-114">From the **Receive pipeline** drop-down list, select the receive pipeline.</span></span>  
  
    5.  <span data-ttu-id="8d1bb-115">En el **programación** página, seleccione la **fecha de inicio** y **fecha de finalización** para restringir la recepción de documentos.</span><span class="sxs-lookup"><span data-stu-id="8d1bb-115">On the **Schedule** page, select the **Start date** and the **End date** to restrict receiving documents.</span></span>  
  
    6.  <span data-ttu-id="8d1bb-116">Seleccione el **habilitar ventana de servicio** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="8d1bb-116">Select the **Enable service window** checkbox.</span></span>  
  
    7.  <span data-ttu-id="8d1bb-117">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8d1bb-117">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="8d1bb-118">En el **asignaciones de entrada** , seleccione las asignaciones de entrada para transformar documentos en el puerto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="8d1bb-118">On the **Inbound Maps** page, select the inbound maps for transforming documents on the selected port.</span></span>  
  
6.  <span data-ttu-id="8d1bb-119">En el **seguimiento** página, seleccione el seguimiento de cuerpos de mensaje y el seguimiento de propiedades de mensaje deseado.</span><span class="sxs-lookup"><span data-stu-id="8d1bb-119">On the **Tracking** page, select the desired tracking message bodies and tracking message properties.</span></span>  
  
7.  <span data-ttu-id="8d1bb-120">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8d1bb-120">Click **OK**.</span></span>  
  
