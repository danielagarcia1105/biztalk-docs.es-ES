---
title: "Configuración de mensajes de remitente (NRR) de seguimiento | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e6ca2709-ac4b-48c0-82f8-8a43971a86cb
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1785a5502bc1adb9cc8b9aa7f85b6a4473d21c5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-sender-message-tracking-nrr"></a><span data-ttu-id="42247-102">Configuración del seguimiento de mensajes de remitente (NRR)</span><span class="sxs-lookup"><span data-stu-id="42247-102">Configuring Sender Message Tracking (NRR)</span></span>
<span data-ttu-id="42247-103">Como parte de la configuración de esta página, se puede especificar si los mensajes de salida y sus confirmaciones (MDN) se almacenan en la base de datos sin repudio.</span><span class="sxs-lookup"><span data-stu-id="42247-103">As part of the settings on this page, you can specify whether the outbound messages and their acknowledgements (MDNs) are stored in the non-repudiation database.</span></span> <span data-ttu-id="42247-104">Para obtener más información, consulte [procesamiento de AS2 en BizTalk Server](../core/as2-processing-in-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="42247-104">For more information, see [AS2 Processing in BizTalk Server](../core/as2-processing-in-biztalk-server.md).</span></span>  
  
 <span data-ttu-id="42247-105">Para almacenar mensajes en la base de datos sin repudio, las entidades deben habilitar NRR (recepción sin repudio) como parte de las propiedades del acuerdo AS2.</span><span class="sxs-lookup"><span data-stu-id="42247-105">To store messages in the non-repudiation database, the parties must enable NRR (Non-repudiation of receipt) as part of the AS2 agreement properties.</span></span> <span data-ttu-id="42247-106">NRR garantiza que la entidad remitente ha verificado el recibo firmado procedente del destinatario del mensaje.</span><span class="sxs-lookup"><span data-stu-id="42247-106">NRR ensures that the sender party has verified the signed receipt from the message recipient.</span></span> <span data-ttu-id="42247-107">Conceptualmente, un NRR es una prueba irrefutable para el remitente del mensaje de que el mensaje ha llegado a su destino sin alteraciones.</span><span class="sxs-lookup"><span data-stu-id="42247-107">Conceptually, an NRR is an undeniable proof for the message sender that the message reached the destination unaltered.</span></span> <span data-ttu-id="42247-108">Se puede establecer NRR solo cuando el mensaje original y la confirmación están firmados digitalmente.</span><span class="sxs-lookup"><span data-stu-id="42247-108">NRR can be established only when the original message and the receipt are digitally signed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="42247-109">Todas las propiedades se deshabilitan en esta página si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación al crear la entidad para la que se crea el contrato.</span><span class="sxs-lookup"><span data-stu-id="42247-109">All the properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  <span data-ttu-id="42247-110">Las propiedades solo se deshabilitan en la ficha de acuerdo unidireccional que corresponde a las propiedades de los intercambios que se envían desde la entidad.</span><span class="sxs-lookup"><span data-stu-id="42247-110">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="42247-111">Por ejemplo, si crea dos entidades, entidad A y entidad B y para la entidad A ha desactivado la casilla de verificación, la lista de propiedades anterior se deshabilita en el **entidad A -> B entidad** ficha de acuerdo unidireccional.</span><span class="sxs-lookup"><span data-stu-id="42247-111">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="42247-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="42247-112">Prerequisites</span></span>  
 <span data-ttu-id="42247-113">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42247-113">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-message-tracking-for-outbound-as2-messages-and-inbound-mdn"></a><span data-ttu-id="42247-114">Para configurar el seguimiento de mensajes para mensajes AS2 salientes y MDN entrantes</span><span class="sxs-lookup"><span data-stu-id="42247-114">To configure message tracking for outbound AS2 messages and inbound MDN</span></span>  
  
1.  <span data-ttu-id="42247-115">Crear un acuerdo de AS2 como se describe en [configurar las opciones generales (AS2)](../core/configuring-general-settings-as2.md).</span><span class="sxs-lookup"><span data-stu-id="42247-115">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="42247-116">Para actualizar un acuerdo AS2 existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="42247-116">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="42247-117">En una ficha de acuerdo unidireccional, bajo **configuración de Host Local** sección, haga clic en **seguimiento de mensaje de remitente (NRR)**.</span><span class="sxs-lookup"><span data-stu-id="42247-117">On a one-way agreement tab, under **Local Host Settings** section, click **Sender Message Tracking (NRR)**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="42247-118">Para garantizar la recepción sin repudio, debe establecer la autenticación e integridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="42247-118">To guarantee non-repudiation of receipt, you must establish the authentication and integrity of the message.</span></span> <span data-ttu-id="42247-119">La forma recomendada de hacerlo es mediante una firma digital en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="42247-119">The recommended way of doing so is by using a digital signature on the message.</span></span> <span data-ttu-id="42247-120">Como resultado, si selecciona cualquiera de las propiedades para almacenar mensajes en la base de datos sin repudio, debería firmar el mensaje seleccionando la **debe firmarse el mensaje** propiedad en el **validación** página.</span><span class="sxs-lookup"><span data-stu-id="42247-120">As a result, if you select any of the properties to store messages in the non-repudiation database, you should sign the message by selecting the **Message should be signed** property on the **Validation** page.</span></span>  
  
3.  <span data-ttu-id="42247-121">Seleccione **NRR habilitado para mensajes AS2 salientes codificados** para almacenar mensajes AS2 salientes codificados en la base de datos sin repudio.</span><span class="sxs-lookup"><span data-stu-id="42247-121">Select **NRR enabled for outbound encoded AS2 messages** to store outbound encoded AS2 messages in the non-repudiation database.</span></span>  
  
4.  <span data-ttu-id="42247-122">Seleccione **NRR habilitado para mensajes AS2 salientes descodificados** para almacenar mensajes AS2 salientes descodificados en la base de datos sin repudio.</span><span class="sxs-lookup"><span data-stu-id="42247-122">Select **NRR enabled for outbound decoded AS2 messages** to store outbound decoded AS2 messages in the non-repudiation database.</span></span>  
  
5.  <span data-ttu-id="42247-123">Seleccione **NRR habilitado para MDN de entrada** para almacenar MDN entrantes en la base de datos sin repudio.</span><span class="sxs-lookup"><span data-stu-id="42247-123">Select **NRR enabled for inbound MDN** to store inbound MDN in the non-repudiation database.</span></span>  
  
6.  <span data-ttu-id="42247-124">Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="42247-124">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42247-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="42247-125">See Also</span></span>  
 [<span data-ttu-id="42247-126">Configuración del Host Local (AS2)</span><span class="sxs-lookup"><span data-stu-id="42247-126">Configuring Local Host Settings (AS2)</span></span>](../core/configuring-local-host-settings-as2.md)