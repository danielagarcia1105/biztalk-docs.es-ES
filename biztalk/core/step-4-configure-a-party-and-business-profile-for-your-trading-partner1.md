---
title: 'Paso 4: Configurar una entidad y perfil de negocio para sus socios comerciales Partner1 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db50d0f6-e838-4e92-8548-a63a2c445d55
caps.latest.revision: 40
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa53034af1a07ca55574e2e37eecb7c0875f8a2e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989685"
---
# <a name="step-4-configure-a-party-and-business-profile-for-your-trading-partner"></a><span data-ttu-id="f0443-102">Paso 4: Configurar una entidad y perfil de negocio para el socio comercial</span><span class="sxs-lookup"><span data-stu-id="f0443-102">Step 4: Configure a Party and Business Profile for Your Trading Partner</span></span>
<span data-ttu-id="f0443-103">![Paso 4 de 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-4of9.gif "Step_4of9")</span><span class="sxs-lookup"><span data-stu-id="f0443-103">![Step 4 of 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-4of9.gif "Step_4of9")</span></span>  
  
 <span data-ttu-id="f0443-104">En este paso, se configura un perfil de entidad y negocio para que el socio comercial Fabrikam envíe un mensaje 850 a su organización y pueda recibir un mensaje de confirmación 997 a cambio.</span><span class="sxs-lookup"><span data-stu-id="f0443-104">In this step, you configure a party and business profile for your trading partner Fabrikam to send an 850 message to your organization and receive a 997 acknowledgment message in return.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f0443-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f0443-105">Prerequisites</span></span>  
 <span data-ttu-id="f0443-106">Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0443-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-a-party-and-business-profile-for-your-trading-partner"></a><span data-ttu-id="f0443-107">Procedimiento para configurar una entidad y el perfil empresarial para el asociado comercial</span><span class="sxs-lookup"><span data-stu-id="f0443-107">To configure a party and business profile for your trading partner</span></span>  
  
1. <span data-ttu-id="f0443-108">Abra el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **iniciar**, seleccionando **todos los programas**, seleccionando **Microsoft BizTalk Server**y, a continuación, haga clic en  **Administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="f0443-108">Open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console by clicking **Start**, pointing to **All Programs**, pointing to **Microsoft BizTalk Server**, and then clicking **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="f0443-109">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]y, a continuación, expanda **grupo de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="f0443-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then expand **BizTalk Group**.</span></span> <span data-ttu-id="f0443-110">Haga clic en **partes**, apunte a **New**y, a continuación, haga clic en **entidad**.</span><span class="sxs-lookup"><span data-stu-id="f0443-110">Right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
3. <span data-ttu-id="f0443-111">En el **las propiedades de entidad** diálogo cuadro, escriba **Fabrikam** en el **nombre** campo.</span><span class="sxs-lookup"><span data-stu-id="f0443-111">In the **Party Properties** dialog box, enter **Fabrikam** in the **Name** field.</span></span>  
  
4. <span data-ttu-id="f0443-112">Desactive el **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes desde esta entidad** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="f0443-112">Clear the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box.</span></span> <span data-ttu-id="f0443-113">Si desactiva la casilla de verificación especificar que la entidad (en este caso, **Fabrikam**) no aloja BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="f0443-113">By clearing the check box you specify that the party (in this case, **Fabrikam**) does not host BizTalk Server.</span></span>  
  
5. <span data-ttu-id="f0443-114">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f0443-114">Click **OK**.</span></span>  
  
6. <span data-ttu-id="f0443-115">Haga clic en el nombre de la entidad, seleccione **New**y, a continuación, haga clic en **perfil de negocio**.</span><span class="sxs-lookup"><span data-stu-id="f0443-115">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
7. <span data-ttu-id="f0443-116">En el **propiedades de perfil** cuadro de diálogo el **General** , escriba `Fabrikam_Profile` en el **nombre** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="f0443-116">In the **Profile Properties** dialog box, on the **General** page, enter `Fabrikam_Profile` in the **Name** text box.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="f0443-117">Cuando se crea una entidad, un perfil denominado *PartyName*_Profile automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f0443-117">When you create a party, a profile named *PartyName*_Profile is automatically created.</span></span> <span data-ttu-id="f0443-118">Puede usar este perfil, en lugar de crear uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="f0443-118">You can use this profile instead of creating a new one.</span></span> <span data-ttu-id="f0443-119">Para cambiar el nombre de un perfil, haga clic en el perfil y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f0443-119">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="f0443-120">En el **General** , especifique un nombre para el perfil.</span><span class="sxs-lookup"><span data-stu-id="f0443-120">In the **General** page, specify a name for the profile.</span></span>  
  
8. <span data-ttu-id="f0443-121">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f0443-121">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f0443-122">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="f0443-122">Next Steps</span></span>  
 <span data-ttu-id="f0443-123">Configurar la ubicación de recepción (**fromTHEM_4010_850**) para recibir el mensaje 850 de Fabrikam, tal como se describe en [paso 5: configurar un puerto de recepción y ubicación de recepción](../core/step-5-configure-a-receive-port-and-receive-location.md).</span><span class="sxs-lookup"><span data-stu-id="f0443-123">You configure the receive location (**fromTHEM_4010_850**) to receive the 850 message from Fabrikam, as described in [Step 5: Configure a Receive Port and Receive Location](../core/step-5-configure-a-receive-port-and-receive-location.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0443-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0443-124">See Also</span></span>  
 [<span data-ttu-id="f0443-125">Configuración de las propiedades de EDI</span><span class="sxs-lookup"><span data-stu-id="f0443-125">Configuring EDI Properties</span></span>](../core/configuring-edi-properties.md)