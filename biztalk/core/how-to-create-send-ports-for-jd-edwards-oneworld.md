---
redirect_url: /biztalk/core/adding-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: d65b87fbcbdaf89289406ae6850b70c605123451
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-create-send-ports-for-jd-edwards-oneworld"></a><span data-ttu-id="ec5a7-101">Creación de puertos de envío para JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="ec5a7-101">How to Create Send Ports for JD Edwards OneWorld</span></span>
<span data-ttu-id="ec5a7-102">Use el procedimiento siguiente para crear un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="ec5a7-102">Use the following procedure to create a send port.</span></span>  
  
### <a name="to-create-a-send-port"></a><span data-ttu-id="ec5a7-103">Procedimiento para crear un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="ec5a7-103">To create a send port</span></span>  
  
1.  <span data-ttu-id="ec5a7-104">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, navegue hasta el aplicación necesaria.</span><span class="sxs-lookup"><span data-stu-id="ec5a7-104">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then navigate to the required application.</span></span>  
  
2.  <span data-ttu-id="ec5a7-105">Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.</span><span class="sxs-lookup"><span data-stu-id="ec5a7-105">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ec5a7-106">También puede usar **Puerto unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="ec5a7-106">You can also use **Static One-Way Port**.</span></span>  
  
3.  <span data-ttu-id="ec5a7-107">En el **propiedades de puerto de envío** cuadro de diálogo, en la **nombre** , a continuación, escriba un nombre de puerto de envío (por ejemplo, escriba **SendToJDE**.)</span><span class="sxs-lookup"><span data-stu-id="ec5a7-107">In the **Send Port Properties** dialog box, in the **Name** field, type a send port name (for example, type **SendToJDE**.)</span></span>  
  
4.  <span data-ttu-id="ec5a7-108">En el **tipo** lista desplegable, seleccione **JDEOneWorld**.</span><span class="sxs-lookup"><span data-stu-id="ec5a7-108">In the **Type** drop-down list, select **JDEOneWorld**.</span></span>  
  
5.  <span data-ttu-id="ec5a7-109">En el **URI** lista desplegable, seleccione el controlador de envío.</span><span class="sxs-lookup"><span data-stu-id="ec5a7-109">In the **URI** drop-down list, select the send handler.</span></span>  
  
6.  <span data-ttu-id="ec5a7-110">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ec5a7-110">Click **OK**.</span></span>  
  
