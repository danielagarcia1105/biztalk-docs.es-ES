---
title: 'Paso 3: Configurar una entidad y perfil de negocio de su Organization1 | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 849e5146-a82a-41f2-bb96-089841b2444d
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1eff579959840f760449422ebbe7af35792e7cc8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-configure-a-party-and-business-profile-for-your-organization"></a><span data-ttu-id="8c1ce-102">Paso 3: Configurar una entidad y perfil de negocio para su organización</span><span class="sxs-lookup"><span data-stu-id="8c1ce-102">Step 3: Configure a Party and Business Profile for Your Organization</span></span>
<span data-ttu-id="8c1ce-103">![Paso 3 de 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-3of9.gif "Step_3of9")</span><span class="sxs-lookup"><span data-stu-id="8c1ce-103">![Step 3 of 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-3of9.gif "Step_3of9")</span></span>  
  
 <span data-ttu-id="8c1ce-104">En este paso, se configura una entidad y un perfil de negocio para que su organización reciba un mensaje 850 de su socio comercial y devuelva un mensaje de confirmación 997.</span><span class="sxs-lookup"><span data-stu-id="8c1ce-104">In this step, you configure a party and a business profile for your organization to receive an 850 message from your trading partner and return a 997 acknowledgment message.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8c1ce-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8c1ce-105">Prerequisites</span></span>  
 <span data-ttu-id="8c1ce-106">Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c1ce-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-a-party-and-business-profile-for-your-organization"></a><span data-ttu-id="8c1ce-107">Procedimiento para configurar un perfil de entidad y empresa para su organización</span><span class="sxs-lookup"><span data-stu-id="8c1ce-107">To configure a party and business profile for your organization</span></span>  
  
1.  <span data-ttu-id="8c1ce-108">Abra la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **iniciar**, seleccionando **todos los programas**, seleccionando **Microsoft BizTalk Server**y, a continuación, haga clic en  **Administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="8c1ce-108">Open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console by clicking **Start**, pointing to **All Programs**, pointing to **Microsoft BizTalk Server**, and then clicking **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="8c1ce-109">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]y, a continuación, expanda **grupo de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="8c1ce-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then expand **BizTalk Group**.</span></span> <span data-ttu-id="8c1ce-110">Haga clic en **partes**, seleccione **New**y, a continuación, haga clic en **entidad**.</span><span class="sxs-lookup"><span data-stu-id="8c1ce-110">Right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
3.  <span data-ttu-id="8c1ce-111">En el **propiedades de la entidad** diálogo cuadro, escriba **OrderSystem** en el **nombre** campo.</span><span class="sxs-lookup"><span data-stu-id="8c1ce-111">In the **Party Properties** dialog box, enter **OrderSystem** in the **Name** field.</span></span>  
  
4.  <span data-ttu-id="8c1ce-112">Seleccione el **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="8c1ce-112">Select the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box.</span></span> <span data-ttu-id="8c1ce-113">Si selecciona la casilla de verificación, se especifica que la entidad (en este caso, **OrderSystem**) también aloja BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="8c1ce-113">By selecting the check box you specify that the party (in this case, **OrderSystem**) also hosts BizTalk Server.</span></span>  
  
5.  <span data-ttu-id="8c1ce-114">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8c1ce-114">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="8c1ce-115">Haga clic en el nombre de la entidad, seleccione **New**y, a continuación, haga clic en **perfil de negocio**.</span><span class="sxs-lookup"><span data-stu-id="8c1ce-115">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
7.  <span data-ttu-id="8c1ce-116">En el **propiedades de perfil** cuadro de diálogo la **General** escriba `OrderSystem_Profile` en el **nombre** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="8c1ce-116">In the **Profile Properties** dialog box, on the **General** page, enter `OrderSystem_Profile` in the **Name** text box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8c1ce-117">Cuando se crea una entidad, un perfil denominado *PartyName*_Profile automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8c1ce-117">When you create a party, a profile named *PartyName*_Profile is automatically created.</span></span> <span data-ttu-id="8c1ce-118">Puede usar este perfil, en lugar de crear uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="8c1ce-118">You can use this profile instead of creating a new one.</span></span> <span data-ttu-id="8c1ce-119">Para cambiar el nombre de un perfil, haga clic en el perfil y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="8c1ce-119">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="8c1ce-120">En el **General** página, especifique un nombre para el perfil.</span><span class="sxs-lookup"><span data-stu-id="8c1ce-120">In the **General** page, specify a name for the profile.</span></span>  
  
8.  <span data-ttu-id="8c1ce-121">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8c1ce-121">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8c1ce-122">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="8c1ce-122">Next Steps</span></span>  
 <span data-ttu-id="8c1ce-123">Configurar un perfil de entidad y de negocio para su organización de socios comerciales (**Fabrikam**), tal y como se describe en [paso 4: configurar una entidad y perfil de negocio para el socio comercial](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner1.md).</span><span class="sxs-lookup"><span data-stu-id="8c1ce-123">You configure a party and business profile for your partner organization (**Fabrikam**), as described in [Step 4: Configure a Party and Business Profile for Your Trading Partner](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner1.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c1ce-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c1ce-124">See Also</span></span>  
 [<span data-ttu-id="8c1ce-125">Configurar propiedades de EDI</span><span class="sxs-lookup"><span data-stu-id="8c1ce-125">Configuring EDI Properties</span></span>](../core/configuring-edi-properties.md)