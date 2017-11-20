---
title: "Configuración del receptor de mensajes seguimiento (NRR) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ce30737a-341b-45be-81a0-a7336219185e
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 942a9c62e69f9f39bf445f0b3028a4e6707f48d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-receiver-message-tracking-nrr"></a><span data-ttu-id="6f554-102">Configuración del seguimiento de mensajes de receptor (NRR)</span><span class="sxs-lookup"><span data-stu-id="6f554-102">Configuring Receiver Message Tracking (NRR)</span></span>
<span data-ttu-id="6f554-103">Como parte de la configuración de esta página, puede especificar si los mensajes entrantes y sus confirmaciones (MDN) se almacenan en la base de datos sin repudio.</span><span class="sxs-lookup"><span data-stu-id="6f554-103">As part of the settings on this page, you can specify whether the inbound messages and their acknowledgements (MDNs) are stored in the non-repudiation database.</span></span> <span data-ttu-id="6f554-104">Para obtener más información, consulte [procesamiento de AS2 en BizTalk Server](../core/as2-processing-in-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="6f554-104">For more information, see [AS2 Processing in BizTalk Server](../core/as2-processing-in-biztalk-server.md).</span></span>  
  
 <span data-ttu-id="6f554-105">Para almacenar mensajes en la base de datos sin repudio, las entidades deben habilitar NRR (recepción sin repudio) como parte de las propiedades del acuerdo AS2.</span><span class="sxs-lookup"><span data-stu-id="6f554-105">To store messages in the non-repudiation database, the parties must enable NRR (Non-repudiation of receipt) as part of the AS2 agreement properties.</span></span> <span data-ttu-id="6f554-106">NRR garantiza que la entidad remitente ha verificado el recibo firmado procedente del destinatario del mensaje.</span><span class="sxs-lookup"><span data-stu-id="6f554-106">NRR ensures that the sender party has verified the signed receipt from the message recipient.</span></span> <span data-ttu-id="6f554-107">Conceptualmente, un NRR es una prueba irrefutable para el remitente del mensaje de que el mensaje ha llegado a su destino sin alteraciones.</span><span class="sxs-lookup"><span data-stu-id="6f554-107">Conceptually, an NRR is an undeniable proof for the message sender that the message reached the destination unaltered.</span></span> <span data-ttu-id="6f554-108">Se puede establecer NRR solo cuando el mensaje original y la confirmación están firmados digitalmente.</span><span class="sxs-lookup"><span data-stu-id="6f554-108">NRR can be established only when the original message and the receipt are digitally signed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6f554-109">Ninguna propiedad se deshabilita en **entidad A -> B entidad** ficha de acuerdo unidireccional si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación para la entidad A. Sin embargo, se deshabilitan todas las propiedades en la misma página en la **parte B -> parte A** ficha si ha seleccionado la casilla de verificación al crear la entidad A.</span><span class="sxs-lookup"><span data-stu-id="6f554-109">No properties are disabled on **Party A->Party B** one-way agreement tab if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box for Party A. However, all the properties are disabled on the same page in the **Party B->Party A** tab if you selected the check box while creating Party A.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6f554-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6f554-110">Prerequisites</span></span>  
 <span data-ttu-id="6f554-111">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f554-111">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-message-tracking-for-inbound-as2-messages-and-outbound-mdn"></a><span data-ttu-id="6f554-112">Para configurar el seguimiento de mensajes de AS2 entrantes y MDN saliente</span><span class="sxs-lookup"><span data-stu-id="6f554-112">To configure message tracking for inbound AS2 messages and outbound MDN</span></span>  
  
1.  <span data-ttu-id="6f554-113">Crear un acuerdo de AS2 como se describe en [configurar las opciones generales (AS2)](../core/configuring-general-settings-as2.md).</span><span class="sxs-lookup"><span data-stu-id="6f554-113">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="6f554-114">Para actualizar un acuerdo AS2 existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6f554-114">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="6f554-115">En una ficha de acuerdo unidireccional, bajo **configuración de Host Local** sección, haga clic en **seguimiento de mensaje de receptor (NRR)**.</span><span class="sxs-lookup"><span data-stu-id="6f554-115">On a one-way agreement tab, under **Local Host Settings** section, click **Receiver Message Tracking (NRR)**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6f554-116">Para garantizar la recepción sin repudio, debe establecer la autenticación e integridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="6f554-116">To guarantee non-repudiation of receipt, you must establish the authentication and integrity of the message.</span></span> <span data-ttu-id="6f554-117">La forma recomendada de hacerlo es mediante una firma digital en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="6f554-117">The recommended way of doing so is by using a digital signature on the message.</span></span> <span data-ttu-id="6f554-118">Como resultado, si selecciona cualquiera de las propiedades para almacenar mensajes en la base de datos sin repudio, debería firmar el mensaje seleccionando la **debe firmarse el mensaje** propiedad en el **validación** página.</span><span class="sxs-lookup"><span data-stu-id="6f554-118">As a result, if you select any of the properties to store messages in the non-repudiation database, you should sign the message by selecting the **Message should be signed** property on the **Validation** page.</span></span>  
  
3.  <span data-ttu-id="6f554-119">Seleccione **NRR habilitado para mensajes AS2 codificados de entrada** para almacenar mensajes AS2 salientes codificados en la base de datos sin repudio.</span><span class="sxs-lookup"><span data-stu-id="6f554-119">Select **NRR enabled for inbound encoded AS2 messages** to store outbound encoded AS2 messages in the non-repudiation database.</span></span>  
  
4.  <span data-ttu-id="6f554-120">Seleccione **NRR habilitado para mensajes AS2 entrantes descodificados** para almacenar mensajes AS2 salientes descodificados en la base de datos sin repudio.</span><span class="sxs-lookup"><span data-stu-id="6f554-120">Select **NRR enabled for inbound decoded AS2 messages** to store outbound decoded AS2 messages in the non-repudiation database.</span></span>  
  
5.  <span data-ttu-id="6f554-121">Seleccione **NRR habilitado para MDN de salida** para almacenar MDN entrantes en la base de datos sin repudio.</span><span class="sxs-lookup"><span data-stu-id="6f554-121">Select **NRR enabled for outbound MDN** to store inbound MDN in the non-repudiation database.</span></span>  
  
6.  <span data-ttu-id="6f554-122">Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6f554-122">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f554-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f554-123">See Also</span></span>  
 [<span data-ttu-id="6f554-124">Configuración del Host Local (AS2)</span><span class="sxs-lookup"><span data-stu-id="6f554-124">Configuring Local Host Settings (AS2)</span></span>](../core/configuring-local-host-settings-as2.md)