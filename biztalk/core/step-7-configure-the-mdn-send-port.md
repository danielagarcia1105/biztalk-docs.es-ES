---
title: 'Paso 7: Configurar el puerto de envío MDN | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 983033ac-9d32-47c8-9bb8-b4161bcdf183
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e65ac8f264e1d8784c97645383b055391397da1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987749"
---
# <a name="step-7-configure-the-mdn-send-port"></a><span data-ttu-id="6f744-102">Paso 7: Configurar el puerto de envío MDN</span><span class="sxs-lookup"><span data-stu-id="6f744-102">Step 7: Configure the MDN Send Port</span></span>
<span data-ttu-id="6f744-103">![Paso 7 de 11](../core/media/tut-step7-of-11.gif "Tut_Step7_of_11")</span><span class="sxs-lookup"><span data-stu-id="6f744-103">![Step 7 of 11](../core/media/tut-step7-of-11.gif "Tut_Step7_of_11")</span></span>  
  
 <span data-ttu-id="6f744-104">En este paso, se establecerá un puerto de envío dinámico para enviar un MDN asincrónico para el \\carpeta _MDNToFabrikam.</span><span class="sxs-lookup"><span data-stu-id="6f744-104">In this step, you set up a dynamic send port to send an asynchronous MDN to the \\_MDNToFabrikam folder.</span></span> <span data-ttu-id="6f744-105">Este puerto de envío utiliza la canalización de envío AS2Send para generar la respuesta MDN saliente.</span><span class="sxs-lookup"><span data-stu-id="6f744-105">This send port uses the AS2Send send pipeline to generate the outgoing MDN response.</span></span> <span data-ttu-id="6f744-106">Ya que se trata de un puerto de envío dinámico, utilizará la dirección en la línea Receipt-Delivery-Option en el encabezado del mensaje para enrutar el mensaje a la \\carpeta _MDNToFabrikam.</span><span class="sxs-lookup"><span data-stu-id="6f744-106">Since this is a dynamic send port, it will use the address in the Receipt-Delivery-Option line in the header of the message to route the message to the \\_MDNToFabrikam folder.</span></span> <span data-ttu-id="6f744-107">Dicha dirección es la del directorio virtual de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="6f744-107">That address is the Fabrikam virtual directory.</span></span> <span data-ttu-id="6f744-108">El archivo Default.aspx.cs asociado a este directorio virtual generará el MDN con una extensión .msg y enviará el archivo a la carpeta de destino (también especificada en la línea Receipt-Delivery-Option).</span><span class="sxs-lookup"><span data-stu-id="6f744-108">The Default.aspx.cs file associated with that virtual directory builds the MDN with an .msg extension, and sends the file to the destination folder (which is also specified in Receipt-Delivery-Option).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6f744-109">También puede configurar el acuerdo para enviar el MDN a otra dirección, invalidando la configuración de mensaje con la nueva configuración de acuerdo.</span><span class="sxs-lookup"><span data-stu-id="6f744-109">You can also configure the agreement to send the MDN to another address, by overriding the message settings with the agreement settings.</span></span> <span data-ttu-id="6f744-110">Para obtener más información, vea</span><span class="sxs-lookup"><span data-stu-id="6f744-110">For more information, see</span></span>  
  
 <span data-ttu-id="6f744-111">En este ejemplo el MDN se envía usando un puerto de envío dinámico; sin embargo, también puede usar un puerto de envío estático para enviar el MDN a una dirección estática.</span><span class="sxs-lookup"><span data-stu-id="6f744-111">In this example the MDN is sent using a dynamic send port; however you can also use a static send port to send the MDN to a static address.</span></span> <span data-ttu-id="6f744-112">Para obtener más información, consulte [configurar un puerto de envío estático para MDN asíncronos a través de AS2](../core/configuring-a-static-send-port-for-asynchronous-mdns-over-as2.md) y [configurar un puerto de envío dinámico para MDN asíncronos a través de AS2](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md).</span><span class="sxs-lookup"><span data-stu-id="6f744-112">For more information, see [Configuring a Static Send Port for Asynchronous MDNs over AS2](../core/configuring-a-static-send-port-for-asynchronous-mdns-over-as2.md) and [Configuring a Dynamic Send Port for Asynchronous MDNs over AS2](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6f744-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6f744-113">Prerequisites</span></span>  
 <span data-ttu-id="6f744-114">Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f744-114">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-create-the-sendasyncmdn-send-port"></a><span data-ttu-id="6f744-115">Para crear el puerto de envío Send_Async_MDN:</span><span class="sxs-lookup"><span data-stu-id="6f744-115">To create the Send_Async_MDN send port</span></span>  
  
1. <span data-ttu-id="6f744-116">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, bajo el nodo BizTalk Application 1, haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **puerto de envío de unidireccionaldinámico**.</span><span class="sxs-lookup"><span data-stu-id="6f744-116">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the BizTalk Application 1 node, right-click **Send Ports**, point to **New**, and then click **Dynamic One-way Send Port**.</span></span>  
  
2. <span data-ttu-id="6f744-117">En el **propiedades de puerto de envío** cuadro de diálogo, el envío de nombre de puerto como **Send_Async_MDN**.</span><span class="sxs-lookup"><span data-stu-id="6f744-117">In the **Send Port Properties** dialog box, name the send port as **Send_Async_MDN**.</span></span>  
  
3. <span data-ttu-id="6f744-118">Seleccione **AS2Send** para **canalización de envío**.</span><span class="sxs-lookup"><span data-stu-id="6f744-118">Select **AS2Send** for **Send pipeline**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6f744-119">Se utiliza la canalización AS2Send debido a que no se requiere procesamiento de EDI para el MDN.</span><span class="sxs-lookup"><span data-stu-id="6f744-119">The AS2Send pipeline is used because no EDI processing is required for the MDN.</span></span>  
  
4. <span data-ttu-id="6f744-120">Haga clic en **filtros** en el árbol de consola.</span><span class="sxs-lookup"><span data-stu-id="6f744-120">Click **Filters** in the console tree.</span></span> <span data-ttu-id="6f744-121">En el panel filtros, seleccione **EdiIntAS.IsAS2AsynchronousMdn** para **propiedad**, **==** para **operador**y escriba **True** para **valor**.</span><span class="sxs-lookup"><span data-stu-id="6f744-121">In the Filters pane, select **EdiIntAS.IsAS2AsynchronousMdn** for **Property**, **==** for **Operator**, and enter **True** for **Value**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6f744-122">Este filtro garantiza que el puerto de envío dinámico sólo recoge los MDN asíncronos del cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="6f744-122">This filter ensures that the dynamic send port only picks up asynchronous MDNs from the MessageBox.</span></span>  
  
5. <span data-ttu-id="6f744-123">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6f744-123">Click **OK**.</span></span>  
  
6. <span data-ttu-id="6f744-124">En el **puertos de envío** panel de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **Send_Async_MDN**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="6f744-124">In the **Send Ports** pane of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click **Send_Async_MDN**, and then click **Start**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="6f744-125">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="6f744-125">Next Steps</span></span>  
 <span data-ttu-id="6f744-126">Configurar el puerto de envío (**Send_Async_997**) para enviar el 997 confirmación de nuevo a Fabrikam, tal como se describe en [paso 8: configurar el puerto de envío 997](../core/step-8-configure-the-997-send-port.md).</span><span class="sxs-lookup"><span data-stu-id="6f744-126">You configure the send port (**Send_Async_997**) to send the 997 acknowledgement back to Fabrikam, as described in [Step 8: Configure the 997 Send Port](../core/step-8-configure-the-997-send-port.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f744-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f744-127">See Also</span></span>  
 <span data-ttu-id="6f744-128">[Cómo BizTalk Server envía mensajes AS2](../core/how-biztalk-server-sends-as2-messages.md) </span><span class="sxs-lookup"><span data-stu-id="6f744-128">[How BizTalk Server Sends AS2 Messages](../core/how-biztalk-server-sends-as2-messages.md) </span></span>  
 <span data-ttu-id="6f744-129">[Configurar un puerto de envío estático para MDN asíncronos a través de AS2](../core/configuring-a-static-send-port-for-asynchronous-mdns-over-as2.md) </span><span class="sxs-lookup"><span data-stu-id="6f744-129">[Configuring a Static Send Port for Asynchronous MDNs over AS2](../core/configuring-a-static-send-port-for-asynchronous-mdns-over-as2.md) </span></span>  
 [<span data-ttu-id="6f744-130">Configuración de un puerto de envío dinámico para mensajes a través de AS2</span><span class="sxs-lookup"><span data-stu-id="6f744-130">Configuring a Dynamic Send Port for Messages over AS2</span></span>](../core/configuring-a-dynamic-send-port-for-messages-over-as2.md)