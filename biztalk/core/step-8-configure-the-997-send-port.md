---
title: "Paso 8: Configurar el puerto de 997 envío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4780c491-9f1a-4f13-b346-6a2e1801ec09
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec3c022ec1236d760c69250a2faecc7cacdb543c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-8-configure-the-997-send-port"></a><span data-ttu-id="be140-102">Paso 8: Configurar el puerto de 997 envío</span><span class="sxs-lookup"><span data-stu-id="be140-102">Step 8: Configure the 997 Send Port</span></span>
<span data-ttu-id="be140-103">![Paso 8 de 11](../core/media/tut-step8-of-11.gif "Tut_Step8_of_11")</span><span class="sxs-lookup"><span data-stu-id="be140-103">![Step 8 of 11](../core/media/tut-step8-of-11.gif "Tut_Step8_of_11")</span></span>  
  
 <span data-ttu-id="be140-104">En este paso, configurará un puerto de envío para enviar el mensaje 997 al socio comercial:</span><span class="sxs-lookup"><span data-stu-id="be140-104">In this step, you set up a send port to send the 997 message to the partner.</span></span> <span data-ttu-id="be140-105">Este puerto de envío usa la canalización de envío AS2EdiSend para transportar una confirmación 997 con codificación EDIINT/AS2 a la carpeta _997ToFabrikam.</span><span class="sxs-lookup"><span data-stu-id="be140-105">This send port uses the AS2EdiSend send pipeline to transport an EDIINT/AS2-encoded 997 acknowledgment to the _997ToFabrikam folder.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="be140-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="be140-106">Prerequisites</span></span>  
 <span data-ttu-id="be140-107">Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="be140-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-create-the-sendasync997-send-port"></a><span data-ttu-id="be140-108">Para crear el puerto de envío Send_Async_997</span><span class="sxs-lookup"><span data-stu-id="be140-108">To create the Send_Async_997 send port</span></span>  
  
1.  <span data-ttu-id="be140-109">En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, bajo el nodo BizTalk Application 1, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático** .</span><span class="sxs-lookup"><span data-stu-id="be140-109">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the BizTalk Application 1 node, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="be140-110">Usará un puerto de envío unidireccional estático, ya que no se ha configurado ningún MDN para la entidad Fabrikam como un receptor de mensaje AS2.</span><span class="sxs-lookup"><span data-stu-id="be140-110">You will use a static one-way send port because no MDN has been set up for the Fabrikam party as an AS2 message receiver.</span></span>  
  
2.  <span data-ttu-id="be140-111">En el **propiedades de puerto de envío** diálogo cuadro, asigne el nombre el puerto de envío **Send_Async_997**.</span><span class="sxs-lookup"><span data-stu-id="be140-111">In the **Send Port Properties** dialog box, name your send port **Send_Async_997**.</span></span> <span data-ttu-id="be140-112">Seleccione **HTTP** para **tipo**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="be140-112">Select **HTTP** for **Type**, and then click **Configure**.</span></span>  
  
3.  <span data-ttu-id="be140-113">En el **propiedades de transporte HTTP** cuadro de diálogo para **dirección URL de destino**, escriba `http://localhost/Fabrikam/Default.aspx?Destination=_997ToFabrikam`.</span><span class="sxs-lookup"><span data-stu-id="be140-113">In the **HTTP Transport Properties** dialog box, for **Destination URL**, enter `http://localhost/Fabrikam/Default.aspx?Destination=_997ToFabrikam`.</span></span> <span data-ttu-id="be140-114">Desactive **Habilitar codificación fragmentada** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="be140-114">Clear **Enable chunked encoding** and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="be140-115">El **dirección URL de destino** valor garantiza que el puerto de envío enviará el mensaje 997 al directorio virtual de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="be140-115">The **Destination URL** setting ensures that the send port will send the 997 message to the Fabrikam virtual directory.</span></span> <span data-ttu-id="be140-116">El archivo Default.aspx.cs asociado a este directorio virtual generará el 997 con una extensión .msg y lo enviará a la carpeta de destino.</span><span class="sxs-lookup"><span data-stu-id="be140-116">The Default.aspx.cs file associated with that virtual directory builds the 997 with an .msg extension, and sends it to the destination folder.</span></span>  
  
4.  <span data-ttu-id="be140-117">En el **propiedades de puerto de envío** cuadro de diálogo, seleccione **AS2EdiSend** para **canalización de envío**.</span><span class="sxs-lookup"><span data-stu-id="be140-117">In the **Send Port Properties** dialog box, select **AS2EdiSend** for **Send Pipeline**.</span></span>  
  
5.  <span data-ttu-id="be140-118">Haga clic en **filtros** en el árbol de consola.</span><span class="sxs-lookup"><span data-stu-id="be140-118">Click **Filters** in the console tree.</span></span> <span data-ttu-id="be140-119">Para **propiedad**, seleccione **BTS. MessageType**.</span><span class="sxs-lookup"><span data-stu-id="be140-119">For **Property**, select **BTS.MessageType**.</span></span> <span data-ttu-id="be140-120">Para **operador**, seleccione  **==** .</span><span class="sxs-lookup"><span data-stu-id="be140-120">For **Operator**, select **==**.</span></span> <span data-ttu-id="be140-121">Para **valor**, escriba `http://schemas.microsoft.com/Edi/X12#X12_997_Root`.</span><span class="sxs-lookup"><span data-stu-id="be140-121">For **Value**, enter `http://schemas.microsoft.com/Edi/X12#X12_997_Root`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="be140-122">Este filtro garantiza que el puerto de envío sólo recogerá confirmaciones 997 del cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="be140-122">This filter ensures that the send port will only pick up 997 acknowledgments from the MessageBox.</span></span>  
  
6.  <span data-ttu-id="be140-123">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="be140-123">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="be140-124">En el **puertos de envío** panel de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **Send_Async_997** puerto de envío y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="be140-124">In the **Send Ports** pane of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Send_Async_997** send port, and then click **Start**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="be140-125">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="be140-125">Next Steps</span></span>  
 <span data-ttu-id="be140-126">Configurar el puerto de envío (**Send_Payload_EdiXml**) para enviar la carga EDI a Contoso, como se describe en [paso 9: configurar el puerto de envío EDI carga](../core/step-9-configure-the-edi-payload-send-port.md).</span><span class="sxs-lookup"><span data-stu-id="be140-126">You configure the send port (**Send_Payload_EdiXml**) to send the EDI payload to Contoso, as described in [Step 9: Configure the EDI Payload Send Port](../core/step-9-configure-the-edi-payload-send-port.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be140-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="be140-127">See Also</span></span>  
 <span data-ttu-id="be140-128">[Cómo BizTalk Server envía mensajes AS2](../core/how-biztalk-server-sends-as2-messages.md) </span><span class="sxs-lookup"><span data-stu-id="be140-128">[How BizTalk Server Sends AS2 Messages](../core/how-biztalk-server-sends-as2-messages.md) </span></span>  
 [<span data-ttu-id="be140-129">Configurar un puerto de envío estático para mensajes a través de AS2</span><span class="sxs-lookup"><span data-stu-id="be140-129">Configuring a Static Send Port for Messages over AS2</span></span>](../core/configuring-a-static-send-port-for-messages-over-as2.md)