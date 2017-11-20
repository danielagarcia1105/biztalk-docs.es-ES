---
title: "Paso 6: Configurar EDI-AS2 ubicación de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 167f8ba2-d38b-4088-863b-2bd90c2a12a2
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bbf1fce88301960a28c19fa20c9996282ce4619
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-6-configure-the-edi-as2-receive-location"></a><span data-ttu-id="9c7eb-102">Paso 6: Configurar EDI-AS2 ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="9c7eb-102">Step 6: Configure the EDI-AS2 Receive Location</span></span>
<span data-ttu-id="9c7eb-103">![Paso 6 de 11](../core/media/tut-step6-of-11.gif "Tut_Step6_of_11")</span><span class="sxs-lookup"><span data-stu-id="9c7eb-103">![Step 6 of 11](../core/media/tut-step6-of-11.gif "Tut_Step6_of_11")</span></span>  
  
 <span data-ttu-id="9c7eb-104">En este paso, configure un puerto de recepción unidireccional que reciba el mensaje EDI de la entidad de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="9c7eb-104">In this step, you set up a one-way receive location that receives the EDI message from the Fabrikam party.</span></span> <span data-ttu-id="9c7eb-105">Esta ubicación de recepción utiliza la canalización de recepción AS2EdiReceive para procesar el mensaje EDI/AS2 entrante.</span><span class="sxs-lookup"><span data-stu-id="9c7eb-105">This receive location uses the AS2EdiReceive receive pipeline to process the incoming EDI/AS2 message.</span></span> <span data-ttu-id="9c7eb-106">El mensaje se enviará a la ubicación de recepción mediante la aplicación sender.exe a través del directorio virtual de Contoso con la extensión ISAPI BTSHTTPReceive.dll.</span><span class="sxs-lookup"><span data-stu-id="9c7eb-106">The message will be sent to the receive location by the sender.exe application through the Contoso virtual directory using the BTSHTTPReceive.dll ISAPI extension.</span></span>  
  
 <span data-ttu-id="9c7eb-107">En este tutorial, establecerá un puerto de envío dinámico para enviar la respuesta MDN de forma asíncrona.</span><span class="sxs-lookup"><span data-stu-id="9c7eb-107">In this tutorial, you will set up a dynamic send port to send the MDN response asynchronously.</span></span> <span data-ttu-id="9c7eb-108">En este escenario, sólo es necesario un puerto de recepción unidireccional.</span><span class="sxs-lookup"><span data-stu-id="9c7eb-108">In this scenario, only a one-way receive port is required.</span></span> <span data-ttu-id="9c7eb-109">Sin embargo, puede también cambiar Sender.exe para enviar un mensaje AS2 que especifica un MDN sincrónico.</span><span class="sxs-lookup"><span data-stu-id="9c7eb-109">However, you could also change Sender.exe to send an AS2 message specifying a synchronous MDN.</span></span> <span data-ttu-id="9c7eb-110">Tendrá que crear un puerto de recepción de solicitud-respuesta bidireccional para devolver el MDN.</span><span class="sxs-lookup"><span data-stu-id="9c7eb-110">You would then have to create a two-way request response receive port to return the MDN.</span></span> <span data-ttu-id="9c7eb-111">Para obtener más información, vea la sección "para probar la solución" de [tutorial (AS2): recibir EDI a través de AS2 con un MDN sincrónico](../core/walkthrough-as2-receiving-edi-over-as2-with-a-synchronous-mdn.md).</span><span class="sxs-lookup"><span data-stu-id="9c7eb-111">For more information, see the "To test the solution" section of [Walkthrough (AS2): Receiving EDI over AS2 with a Synchronous MDN](../core/walkthrough-as2-receiving-edi-over-as2-with-a-synchronous-mdn.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9c7eb-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9c7eb-112">Prerequisites</span></span>  
 <span data-ttu-id="9c7eb-113">Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c7eb-113">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-create-the-biztalk-http-receive-location"></a><span data-ttu-id="9c7eb-114">Para crear la ubicación de recepción HTTP de BizTalk</span><span class="sxs-lookup"><span data-stu-id="9c7eb-114">To create the BizTalk HTTP receive location</span></span>  
  
1.  <span data-ttu-id="9c7eb-115">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, bajo el nodo BizTalk Application 1, haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="9c7eb-115">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the BizTalk Application 1 node, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
2.  <span data-ttu-id="9c7eb-116">Nombre del puerto de recepción como **Receive_AS2**.</span><span class="sxs-lookup"><span data-stu-id="9c7eb-116">Name the receive port as **Receive_AS2**.</span></span>  
  
3.  <span data-ttu-id="9c7eb-117">Haga clic en **ubicaciones de recepción** en el árbol de consola y, a continuación, haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="9c7eb-117">Click **Receive Locations** in the console tree, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="9c7eb-118">En el **propiedades de la ubicación de recepción** cuadro de diálogo, el nombre de la ubicación de recepción **Receive_AS2**, seleccione **HTTP** para **tipo**y, a continuación, Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="9c7eb-118">In the **Receive Location Properties** dialog box, name your receive location **Receive_AS2**, select **HTTP** for **Type**, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="9c7eb-119">En el **propiedades de transporte HTTP** diálogo cuadro, escriba **/Contoso/BTSHTTPReceive.dll** para **directorio Virtual más extensión ISAPI**.</span><span class="sxs-lookup"><span data-stu-id="9c7eb-119">In the **HTTP Transport Properties** dialog box, enter **/Contoso/BTSHTTPReceive.dll** for **Virtual directory plus ISAPI extension**.</span></span> <span data-ttu-id="9c7eb-120">Desactive **devolver controlador de correlación en caso de éxito** y seleccione **suspender solicitudes con errores**.</span><span class="sxs-lookup"><span data-stu-id="9c7eb-120">Clear **Return correlation handle on success** and select **Suspend failed requests**.</span></span> <span data-ttu-id="9c7eb-121">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9c7eb-121">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="9c7eb-122">Seleccione **AS2EdiReceive** para el **canalización de recepción**.</span><span class="sxs-lookup"><span data-stu-id="9c7eb-122">Select **AS2EdiReceive** for the **Receive Pipeline**.</span></span> <span data-ttu-id="9c7eb-123">Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo.</span><span class="sxs-lookup"><span data-stu-id="9c7eb-123">Click **OK**, and then click **OK** again.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c7eb-124">La canalización de recepción AS2EdiReceive realiza descodificación AS2 y desensamblado EDI.</span><span class="sxs-lookup"><span data-stu-id="9c7eb-124">The AS2EdiReceive receive pipeline performs AS2 decoding and EDI disassembly.</span></span>  
  
7.  <span data-ttu-id="9c7eb-125">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **ubicaciones de recepción** bajo el nodo BizTalk Application 1, haga clic en **Receive_AS2**y, a continuación, haga clic en **habilitar** .</span><span class="sxs-lookup"><span data-stu-id="9c7eb-125">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click **Receive Locations** under the BizTalk Application 1 node, right-click **Receive_AS2**, and then click **Enable**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9c7eb-126">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="9c7eb-126">Next Steps</span></span>  
 <span data-ttu-id="9c7eb-127">Configurar el puerto de envío (**Send_Asynch_MDN**) puerto de envío para enviar el MDN asincrónico a Fabrikam, tal y como se describe en [paso 7: configurar el puerto de envío MDN](../core/step-7-configure-the-mdn-send-port.md).</span><span class="sxs-lookup"><span data-stu-id="9c7eb-127">You configure the send port (**Send_Asynch_MDN**) send port to send the asynchronous MDN back to Fabrikam, as described in [Step 7: Configure the MDN Send Port](../core/step-7-configure-the-mdn-send-port.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c7eb-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c7eb-128">See Also</span></span>  
 <span data-ttu-id="9c7eb-129">[Cómo BizTalk Server recibe mensajes AS2](../core/how-biztalk-server-receives-as2-messages.md) </span><span class="sxs-lookup"><span data-stu-id="9c7eb-129">[How BizTalk Server Receives AS2 Messages](../core/how-biztalk-server-receives-as2-messages.md) </span></span>  
 [<span data-ttu-id="9c7eb-130">Configurar un puerto de recepción de mensajes a través de AS2</span><span class="sxs-lookup"><span data-stu-id="9c7eb-130">Configuring a Receive Port for Messages over AS2</span></span>](../core/configuring-a-receive-port-for-messages-over-as2.md)