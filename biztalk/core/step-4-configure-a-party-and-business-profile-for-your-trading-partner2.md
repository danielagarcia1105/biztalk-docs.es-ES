---
title: 'Paso 4: Configurar una entidad y perfil de negocio para sus socios comerciales Partner2 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce07a1a6-4d5d-44ea-b1cb-04d7ae85747f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d0ecc92a435455d15db31e2de454ff935c1504f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977933"
---
# <a name="step-4-configure-a-party-and-business-profile-for-your-trading-partner"></a><span data-ttu-id="1a90d-102">Paso 4: Configurar una entidad y perfil de negocio para el socio comercial</span><span class="sxs-lookup"><span data-stu-id="1a90d-102">Step 4: Configure a Party and Business Profile for Your Trading Partner</span></span>
<span data-ttu-id="1a90d-103">![Paso 4 de 11](../core/media/tut-step4-of-11.gif "Tut_Step4_of_11")</span><span class="sxs-lookup"><span data-stu-id="1a90d-103">![Step 4 of 11](../core/media/tut-step4-of-11.gif "Tut_Step4_of_11")</span></span>  
  
 <span data-ttu-id="1a90d-104">En este paso, configurará una entidad y perfil de negocio para que el socio comercial Fabrikam envíe un mensaje 864 a la organización y reciba un mensaje de confirmación 997 y un MDN asincrónico de vuelta.</span><span class="sxs-lookup"><span data-stu-id="1a90d-104">In this step, you configure a party and business profile for your trading partner Fabrikam to send an 864 message to your organization and receive a 997 acknowledgment message and an asynchronous MDN in return.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1a90d-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="1a90d-105">Prerequisites</span></span>  
 <span data-ttu-id="1a90d-106">Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1a90d-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-a-party-and-business-profile-for-your-trading-partner"></a><span data-ttu-id="1a90d-107">Procedimiento para configurar una entidad y el perfil empresarial para el asociado comercial</span><span class="sxs-lookup"><span data-stu-id="1a90d-107">To configure a party and business profile for your trading partner</span></span>  
  
1. <span data-ttu-id="1a90d-108">Abra el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **iniciar**, seleccionando **todos los programas**, seleccionando [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server** .</span><span class="sxs-lookup"><span data-stu-id="1a90d-108">Open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console by clicking **Start**, pointing to **All Programs**, pointing to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then clicking **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="1a90d-109">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]y, a continuación, expanda **grupo de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="1a90d-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then expand **BizTalk Group**.</span></span> <span data-ttu-id="1a90d-110">Haga clic en **partes**, apunte a **New**y, a continuación, haga clic en **entidad**.</span><span class="sxs-lookup"><span data-stu-id="1a90d-110">Right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
3. <span data-ttu-id="1a90d-111">En el **las propiedades de entidad** diálogo cuadro, escriba **Fabrikam** en el **nombre** campo.</span><span class="sxs-lookup"><span data-stu-id="1a90d-111">In the **Party Properties** dialog box, enter **Fabrikam** in the **Name** field.</span></span>  
  
4. <span data-ttu-id="1a90d-112">Desactive el **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes desde esta entidad** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="1a90d-112">Clear the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box.</span></span> <span data-ttu-id="1a90d-113">Si desactiva la casilla de verificación especificar que la entidad (en este caso, **Fabrikam**) no aloja BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="1a90d-113">By clearing the check box you specify that the party (in this case, **Fabrikam**) does not host BizTalk Server.</span></span>  
  
5. <span data-ttu-id="1a90d-114">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1a90d-114">Click **OK**.</span></span>  
  
6. <span data-ttu-id="1a90d-115">Haga clic en el nombre de la entidad, seleccione **New**y, a continuación, haga clic en **perfil de negocio**.</span><span class="sxs-lookup"><span data-stu-id="1a90d-115">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
7. <span data-ttu-id="1a90d-116">En el **propiedades de perfil** cuadro de diálogo el **General** , escriba `Fabrikam_Profile` en el **nombre** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="1a90d-116">In the **Profile Properties** dialog box, on the **General** page, enter `Fabrikam_Profile` in the **Name** text box.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="1a90d-117">Cuando se crea una entidad, también se crea un perfil.</span><span class="sxs-lookup"><span data-stu-id="1a90d-117">When you create a party, a profile is also created.</span></span> <span data-ttu-id="1a90d-118">Puede cambiar el nombre y usar ese perfil en lugar de crear uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="1a90d-118">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="1a90d-119">Para cambiar el nombre de un perfil, haga clic en el perfil y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="1a90d-119">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="1a90d-120">En el **General** , especifique un nombre para el perfil.</span><span class="sxs-lookup"><span data-stu-id="1a90d-120">In the **General** page, specify a name for the profile.</span></span>  
  
8. <span data-ttu-id="1a90d-121">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1a90d-121">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="1a90d-122">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="1a90d-122">Next Steps</span></span>  
 <span data-ttu-id="1a90d-123">Configurar el filtro ISAPI de BTS y Fabrikam y páginas Web de Contoso en [paso 5: configurar las páginas Web de socios comerciales](../core/step-5-configure-the-trading-partner-web-pages.md).</span><span class="sxs-lookup"><span data-stu-id="1a90d-123">You configure the BTS ISAPI filter and the Fabrikam and Contoso Web pages in [Step 5: Configure the Trading Partner Web Pages](../core/step-5-configure-the-trading-partner-web-pages.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a90d-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a90d-124">See Also</span></span>  
 [<span data-ttu-id="1a90d-125">Configuración de las propiedades de EDI</span><span class="sxs-lookup"><span data-stu-id="1a90d-125">Configuring EDI Properties</span></span>](../core/configuring-edi-properties.md)