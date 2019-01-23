---
title: Configurar los vales de SSO | Microsoft Docs
description: Utilice las administraciones de inicio de sesión único o una línea de comandos para permitir y validar único empresarial vales de sesión en el nivel de sistema y para las aplicaciones afiliadas en BizTalk Server.
ms.custom: ''
ms.date: 01/08/2019
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO], configuring tickets
- SSO, tickets
- tickets [SSO], configuring
ms.assetid: 32f0384b-ac79-4cce-b3f5-f4f8a73a673a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3ce6c1de1a94225f06d09b66cc3e6c60c471f24
ms.sourcegitcommit: 2d39bcd10a22c5945d97a03988ccdc62f6fb3c93
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2019
ms.locfileid: "54443377"
---
# <a name="configure-the-sso-tickets-in-biztalk-server"></a><span data-ttu-id="39789-103">Configurar los vales de SSO en BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="39789-103">Configure the SSO Tickets in BizTalk Server</span></span>
<span data-ttu-id="39789-104">Puede utilizar MMC de administración de inicio de sesión único (SSO) empresarial o la línea de comandos para controlar el comportamiento de vale para todo el único inicio de sesión en sistema.</span><span class="sxs-lookup"><span data-stu-id="39789-104">You can use Enterprise Single Sign-On (SSO) Administration MMC or the command line to control ticket behavior for the entire single sign-on system.</span></span> <span data-ttu-id="39789-105">Con las herramientas de este, puede permitir vales y validar vales de SSO.</span><span class="sxs-lookup"><span data-stu-id="39789-105">Using this tools, you can allow tickets and validate SSO tickets.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="39789-106">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="39789-106">Before you begin</span></span>

- <span data-ttu-id="39789-107">Si la administración de SSO está instalado en un equipo remoto, puede ejecutar un control remoto [IssueTicket](https://docs.microsoft.com/biztalk/core/technical-reference/issoticket-issueticket-method) operación.</span><span class="sxs-lookup"><span data-stu-id="39789-107">If SSO Administration is installed on a remote computer, you can run a remote [IssueTicket](https://docs.microsoft.com/biztalk/core/technical-reference/issoticket-issueticket-method) operation.</span></span> <span data-ttu-id="39789-108">Se cifra todo el tráfico entre el módulo de administración de SSO y el módulo de tiempo de ejecución (servicio ENTSSO).</span><span class="sxs-lookup"><span data-stu-id="39789-108">All traffic between the SSO Administration module and the Runtime module (ENTSSO service) is encrypted.</span></span>  
  
- <span data-ttu-id="39789-109">Mediante la utilidad de línea de comandos ssomanage.exe, puede especificar el tiempo de espera de vale en el nivel de aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="39789-109">Using the ssomanage.exe command line utility, you can enter the ticket timeout at the Affiliate Application level.</span></span> <span data-ttu-id="39789-110">Puede hacerlo sólo cuando se realiza una actualización de la aplicación, no cuando se crea la aplicación.</span><span class="sxs-lookup"><span data-stu-id="39789-110">You can do this only when an update of the application is made, not when the application is created.</span></span>
  
- <span data-ttu-id="39789-111">Solo los usuarios del grupo de administradores de SSO pueden configurar vales en el nivel de sistema SSO y en el nivel de aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="39789-111">Only users in the SSO Administrator group can configure tickets at the SSO system-level and at the Affiliate Application level.</span></span>  
  
- <span data-ttu-id="39789-112">Si el control de vales está deshabilitado en el nivel de sistema, no se puede usar en el nivel de aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="39789-112">If ticketing is disabled at the system-level, it can't be used at the Affiliate Application level.</span></span> <span data-ttu-id="39789-113">Es posible habilitar los vales en el nivel de sistema y deshabilitarlos en el nivel de aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="39789-113">It's possible to enable tickets at the system level, and disable them at the Affiliate Application level.</span></span>  
  
- <span data-ttu-id="39789-114">Si se habilita la validación en el nivel de sistema, se deben validar vales en el nivel de aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="39789-114">If validation is enabled at the system-level, tickets must be validated at the Affiliate Application level.</span></span> <span data-ttu-id="39789-115">Es posible deshabilitar la validación en el nivel de sistema y habilitarla en el nivel de aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="39789-115">It's possible to disable validation at the system-level, and enable it at the Affiliate Application level.</span></span>  
  
- <span data-ttu-id="39789-116">Si se especifica el tiempo de espera de vale en el nivel de sistema y el nivel de aplicación afiliada, se introdujo en el nivel de aplicación afiliada determina el tiempo de expiración del vale.</span><span class="sxs-lookup"><span data-stu-id="39789-116">If ticket timeout is entered at the system-level and the Affiliate Application level, the one entered at the Affiliate Application level determines the ticket expiration time.</span></span>  
  
<span data-ttu-id="39789-117">Para obtener más información acerca de vales y validación de vales, consulte [vales de SSO](../core/sso-tickets.md).</span><span class="sxs-lookup"><span data-stu-id="39789-117">For more information about tickets and tickets validation, see [SSO Tickets](../core/sso-tickets.md).</span></span>  
  
## <a name="allow-affiliate-application-tickets-using-sso-administration"></a><span data-ttu-id="39789-118">Permitir vales de aplicación afiliada con la administración de SSO</span><span class="sxs-lookup"><span data-stu-id="39789-118">Allow Affiliate Application tickets using SSO Administration</span></span>  
  
1.  <span data-ttu-id="39789-119">Desde el **iniciar** menú, seleccione **todos los programas** > **Microsoft Enterprise Single Sign-On** > **administración de SSO** .</span><span class="sxs-lookup"><span data-stu-id="39789-119">From the **Start** menu, select **All Programs** > **Microsoft Enterprise Single Sign-On** > **SSO Administration**.</span></span>
  
2.  <span data-ttu-id="39789-120">En el panel de ámbito del complemento MMC de ENTSSO, expanda el **aplicaciones afiliadas** nodo.</span><span class="sxs-lookup"><span data-stu-id="39789-120">In the scope pane of the ENTSSO MMC Snap-In, expand the **Affiliate Applications** node.</span></span>  
  
3.  <span data-ttu-id="39789-121">Haga clic en **aplicación afiliada** > **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="39789-121">Right-click **Affiliate Application** > **Properties**.</span></span>  
  
4.  <span data-ttu-id="39789-122">Elija la **opciones** ficha.</span><span class="sxs-lookup"><span data-stu-id="39789-122">Choose the **Options** tab.</span></span>  
  
5.  <span data-ttu-id="39789-123">Seleccione **permitir vales** y escriba el tiempo de espera de vale que desee.</span><span class="sxs-lookup"><span data-stu-id="39789-123">Select **Allow Tickets** and enter the ticket timeout you want.</span></span>  
  
## <a name="allow-and-validate-sso-system-level-tickets-using-the-command-line"></a><span data-ttu-id="39789-124">Permitir y validar vales de nivel de sistema SSO mediante la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="39789-124">Allow and validate SSO system-level tickets using the command line</span></span>  
  
1. <span data-ttu-id="39789-125">Abra un símbolo del sistema (menú Inicio > tipo **símbolo** > seleccione **símbolo**).</span><span class="sxs-lookup"><span data-stu-id="39789-125">Open a command prompt (Start menu > type **command prompt** > select **Command Prompt**).</span></span>

    > [!TIP]
    >  <span data-ttu-id="39789-126">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba abrir el símbolo del sistema con privilegios administrativos (haga clic en **símbolo** > \*\* Ejecutar como administrador).</span><span class="sxs-lookup"><span data-stu-id="39789-126">On a system that supports User Account Control (UAC), you may need to open the command prompt with Administrative privileges (right-click **Command Prompt** > \*\*Run as administrator).</span></span>
  
2. <span data-ttu-id="39789-127">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="39789-127">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="39789-128">El directorio de instalación predeterminado es `\Program Files\Common Files\Enterprise Single Sign-On`.</span><span class="sxs-lookup"><span data-stu-id="39789-128">The default installation directory is `\Program Files\Common Files\Enterprise Single Sign-On`.</span></span> <span data-ttu-id="39789-129">Por ejemplo, escriba:</span><span class="sxs-lookup"><span data-stu-id="39789-129">For example, enter:</span></span> 

    `cd C:\Program Files\Common Files\Enterprise Single Sign-On`
  
3. <span data-ttu-id="39789-130">Tipo `ssomanage -tickets <allowed yes/no> <validate yes/no>`, donde *\<sí/no de permiten\>* indica si se permiten los vales o no, y *\<validar sí/no\>* indica si se deben validar después de que se puede canjear vales.</span><span class="sxs-lookup"><span data-stu-id="39789-130">Type `ssomanage -tickets <allowed yes/no> <validate yes/no>`, where *\<allowed yes/no\>* indicates whether tickets are allowed or not, and *\<validate yes/no\>* indicates whether tickets need to be validated after they're redeemed.</span></span>  
  
    <span data-ttu-id="39789-131">Puede usar `yes`, `no`, `on`, o `off` para permitir o validar vales.</span><span class="sxs-lookup"><span data-stu-id="39789-131">You can use `yes`, `no`, `on`, or `off` to allow and/or validate tickets.</span></span> <span data-ttu-id="39789-132">El uso de mayúsculas y minúsculas en estas palabras carece de importancia y se deben utilizar independientemente de la configuración del idioma.</span><span class="sxs-lookup"><span data-stu-id="39789-132">These words are case independent, and must be used regardless of your language settings.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="39789-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="39789-133">See Also</span></span>

<span data-ttu-id="39789-134">[Descripción de SSO](../core/understanding-sso.md) </span><span class="sxs-lookup"><span data-stu-id="39789-134">[Understanding SSO](../core/understanding-sso.md) </span></span>  
[<span data-ttu-id="39789-135">Uso de SSO</span><span class="sxs-lookup"><span data-stu-id="39789-135">Using SSO</span></span>](../core/using-sso.md)
