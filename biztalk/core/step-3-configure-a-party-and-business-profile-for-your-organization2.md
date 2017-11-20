---
title: 'Paso 3: Configurar una entidad y perfil de negocio de su Organization2 | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 024d1ec7-237a-43cb-8159-90f9c71a670e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7cb8e65d85ef189a17fc95b3599a5e26da0d308
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-configure-a-party-and-business-profile-for-your-organization"></a><span data-ttu-id="84d08-102">Paso 3: Configurar una entidad y perfil de negocio para su organización</span><span class="sxs-lookup"><span data-stu-id="84d08-102">Step 3: Configure a Party and Business Profile for Your Organization</span></span>
<span data-ttu-id="84d08-103">![Paso 3 de 11](../core/media/tut-step3-of-11.gif "Tut_Step3_of_11")</span><span class="sxs-lookup"><span data-stu-id="84d08-103">![Step 3 of 11](../core/media/tut-step3-of-11.gif "Tut_Step3_of_11")</span></span>  
  
 <span data-ttu-id="84d08-104">En este paso, se configura una entidad y un perfil de negocio para que su organización reciba un mensaje 864 de su socio comercial y devuelva un mensaje de confirmación 997 y un MDN asincrónico.</span><span class="sxs-lookup"><span data-stu-id="84d08-104">In this step, you configure a party and a business profile for your organization to receive an 864 message from your trading partner and return a 997 acknowledgment message and an asynchronous MDN.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="84d08-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="84d08-105">Prerequisites</span></span>  
 <span data-ttu-id="84d08-106">Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="84d08-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-a-party-and-business-profile-for-your-organization"></a><span data-ttu-id="84d08-107">Procedimiento para configurar un perfil de entidad y empresa para su organización</span><span class="sxs-lookup"><span data-stu-id="84d08-107">To configure a party and business profile for your organization</span></span>  
  
1.  <span data-ttu-id="84d08-108">Abra la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **iniciar**, seleccionando **todos los programas**, seleccionando [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server** .</span><span class="sxs-lookup"><span data-stu-id="84d08-108">Open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console by clicking **Start**, pointing to **All Programs**, pointing to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then clicking **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="84d08-109">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]y, a continuación, expanda **grupo de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="84d08-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then expand **BizTalk Group**.</span></span> <span data-ttu-id="84d08-110">Haga clic en **partes**, seleccione **New**y, a continuación, haga clic en **entidad**.</span><span class="sxs-lookup"><span data-stu-id="84d08-110">Right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
3.  <span data-ttu-id="84d08-111">En el **propiedades de la entidad** diálogo cuadro, escriba **Contoso** en el **nombre** campo.</span><span class="sxs-lookup"><span data-stu-id="84d08-111">In the **Party Properties** dialog box, enter **Contoso** in the **Name** field.</span></span>  
  
4.  <span data-ttu-id="84d08-112">Seleccione el **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="84d08-112">Select the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box.</span></span> <span data-ttu-id="84d08-113">Si selecciona la casilla de verificación, se especifica que la entidad (en este caso, **Contoso**) también aloja BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="84d08-113">By selecting the check box you specify that the party (in this case, **Contoso**) also hosts BizTalk Server.</span></span>  
  
5.  <span data-ttu-id="84d08-114">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="84d08-114">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="84d08-115">Haga clic en el nombre de la entidad, seleccione **New**y, a continuación, haga clic en **perfil de negocio**.</span><span class="sxs-lookup"><span data-stu-id="84d08-115">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
7.  <span data-ttu-id="84d08-116">En el **propiedades de perfil** cuadro de diálogo la **General** escriba `Contoso_Profile` en el **nombre** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="84d08-116">In the **Profile Properties** dialog box, on the **General** page, enter `Contoso_Profile` in the **Name** text box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="84d08-117">Cuando se crea una entidad, también se crea un perfil.</span><span class="sxs-lookup"><span data-stu-id="84d08-117">When you create a party, a profile is also created.</span></span> <span data-ttu-id="84d08-118">Puede cambiar el nombre y usar ese perfil en lugar de crear uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="84d08-118">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="84d08-119">Para cambiar el nombre de un perfil, haga clic en el perfil y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="84d08-119">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="84d08-120">En el **General** página, especifique un nombre para el perfil.</span><span class="sxs-lookup"><span data-stu-id="84d08-120">In the **General** page, specify a name for the profile.</span></span>  
  
8.  <span data-ttu-id="84d08-121">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="84d08-121">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="84d08-122">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="84d08-122">Next Steps</span></span>  
 <span data-ttu-id="84d08-123">Configurar un perfil de entidad y de negocio para su organización de socios comerciales (**Fabrikam**), tal y como se describe en [paso 4: configurar una entidad y perfil de negocio para el socio comercial](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner2.md).</span><span class="sxs-lookup"><span data-stu-id="84d08-123">You configure a party and business profile for your partner organization (**Fabrikam**), as described in [Step 4: Configure a Party and Business Profile for Your Trading Partner](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84d08-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="84d08-124">See Also</span></span>  
 [<span data-ttu-id="84d08-125">Configurar propiedades de EDI</span><span class="sxs-lookup"><span data-stu-id="84d08-125">Configuring EDI Properties</span></span>](../core/configuring-edi-properties.md)