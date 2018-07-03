---
title: Cómo habilitar el inicio de sesión único | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications [SSO], creating
- SSO, enabling
- maps [SSO], creating
- managing [SSO], enabling
- SSO, maps
- SSO, applications
- creating, applications [SSO]
- managing [SSO], creating affiliate applications
ms.assetid: dda89d15-6b70-4c40-b658-2f6cbdd545c8
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6bb2c6e5349a74fb212bdf7011fb294cb1810e67
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966261"
---
# <a name="how-to-enable-sso"></a><span data-ttu-id="5f4cb-102">Cómo habilitar el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="5f4cb-102">How to Enable SSO</span></span>
<span data-ttu-id="5f4cb-103">Puede habilitar todo el sistema de inicio de sesión único (SSO) empresarial mediante el Complemento MMC o la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="5f4cb-103">You can enable the entire Enterprise Single Sign-On (SSO) system by using either the MMC Snap-In or the command line.</span></span>  
  
 <span data-ttu-id="5f4cb-104">Tras ejecutar el comando de habilitación, se produce un pequeño retraso antes de que se habiliten todos los servidores de inicio de sesión único, ya que cada uno sondea la base de datos de SSO en busca de la información global más actualizada.</span><span class="sxs-lookup"><span data-stu-id="5f4cb-104">After you run the enabling command, there is a short delay before all Single Sign-On Servers are enabled, as each polls the SSO database for the latest global information.</span></span>  
  
 <span data-ttu-id="5f4cb-105">Si desea configurar las asignaciones y aplicaciones afiliadas en el sistema de SSO, debe crear una aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="5f4cb-105">If you want to configure affiliate applications and mappings in the SSO system, you must also create an affiliate application.</span></span> <span data-ttu-id="5f4cb-106">Cuando el administrador afiliado de SSO crea una aplicación afiliada, un administrador de aplicación puede realizar cambios en ella, y los usuarios de la aplicación (usuarios finales) pueden crear sus propias asignaciones.</span><span class="sxs-lookup"><span data-stu-id="5f4cb-106">After an SSO affiliate administrator creates an affiliate application, an application administrator can make changes to it, and application users (end-users) can create their own mappings.</span></span> <span data-ttu-id="5f4cb-107">Para obtener más información, consulte [administrar aplicaciones afiliadas](../core/managing-affiliate-applications.md) y [administración de asignaciones de usuario](../core/managing-user-mappings.md).</span><span class="sxs-lookup"><span data-stu-id="5f4cb-107">For more information, see [Managing Affiliate Applications](../core/managing-affiliate-applications.md) and [Managing User Mappings](../core/managing-user-mappings.md).</span></span>  
  
### <a name="to-enable-the-sso-system-using-the-mmc-snap-in"></a><span data-ttu-id="5f4cb-108">Para habilitar el sistema de SSO con el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="5f4cb-108">To enable the SSO system using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="5f4cb-109">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="5f4cb-109">Click **Start**, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="5f4cb-110">En el panel de ámbito del complemento MMC de ENTSSO, expanda el **Enterprise Single Sign-On** nodo.</span><span class="sxs-lookup"><span data-stu-id="5f4cb-110">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="5f4cb-111">Haga clic en **sistema**y, a continuación, haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="5f4cb-111">Right-click **System**, and then click **Enable**.</span></span>  
  
### <a name="to-enable-the-sso-system-using-the-command-line"></a><span data-ttu-id="5f4cb-112">Para habilitar el sistema de SSO con la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="5f4cb-112">To enable the SSO system using the command line</span></span>  
  
1.  <span data-ttu-id="5f4cb-113">Haga clic en **iniciar**, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="5f4cb-113">Click **Start**, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="5f4cb-114">En el símbolo del sistema, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="5f4cb-114">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="5f4cb-115">El directorio de instalación predeterminado es  **\<unidad\>**: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="5f4cb-115">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="5f4cb-116">Tipo **ssomanage – enablesso**.</span><span class="sxs-lookup"><span data-stu-id="5f4cb-116">Type **ssomanage –enablesso**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5f4cb-117">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="5f4cb-117">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-enable-sso-to-create-affiliate-applications-and-mappings"></a><span data-ttu-id="5f4cb-118">Para habilitar SSO para crear aplicaciones afiliadas y asignaciones</span><span class="sxs-lookup"><span data-stu-id="5f4cb-118">To enable SSO to create affiliate applications and mappings</span></span>  
  
1. <span data-ttu-id="5f4cb-119">Inicie sesión como administrador de SSO o administrador afiliado de SSO en el servidor de SSO o en un equipo que posea los subservicios de administración SSO de SSO.</span><span class="sxs-lookup"><span data-stu-id="5f4cb-119">Log on as an SSO administrator or SSO affiliate administrator to the SSO Server, or on a computer that has the SSO administration sub services of SSO.</span></span>  
  
2. <span data-ttu-id="5f4cb-120">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="5f4cb-120">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
3. <span data-ttu-id="5f4cb-121">En el símbolo del sistema, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="5f4cb-121">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="5f4cb-122">El directorio de instalación predeterminado es  *\<unidad\>*: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="5f4cb-122">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4. <span data-ttu-id="5f4cb-123">Tipo **ssomanage - enablesso** para habilitar el servicio Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="5f4cb-123">Type **ssomanage -enablesso** to enable the Enterprise Single Sign-On service.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5f4cb-124">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="5f4cb-124">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
5. <span data-ttu-id="5f4cb-125">Inicie sesión como administrador afiliado de SSO</span><span class="sxs-lookup"><span data-stu-id="5f4cb-125">Log on as an SSO affiliate administrator.</span></span>  
  
6. <span data-ttu-id="5f4cb-126">Tipo **ssomanage - createapps *\<archivo aplicación\>***  para crear una aplicación afiliada, donde \<archivo aplicación\> es el archivo XML que contiene las definiciones de las aplicaciones afiliadas.</span><span class="sxs-lookup"><span data-stu-id="5f4cb-126">Type **ssomanage -createapps *\<application file\>*** to create an affiliate application, where \<application file\> is the XML file that contains definitions for the affiliate applications.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5f4cb-127">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="5f4cb-127">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f4cb-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f4cb-128">See Also</span></span>  
 <span data-ttu-id="5f4cb-129">[Cómo establecer el servidor de SSO](../core/how-to-set-the-sso-server.md) </span><span class="sxs-lookup"><span data-stu-id="5f4cb-129">[How to Set the SSO Server](../core/how-to-set-the-sso-server.md) </span></span>  
 <span data-ttu-id="5f4cb-130">[Cómo deshabilitar SSO](../core/how-to-disable-sso.md) </span><span class="sxs-lookup"><span data-stu-id="5f4cb-130">[How to Disable SSO](../core/how-to-disable-sso.md) </span></span>  
 <span data-ttu-id="5f4cb-131">[Cómo actualizar la base de datos SSO](../core/how-to-update-the-sso-database.md) </span><span class="sxs-lookup"><span data-stu-id="5f4cb-131">[How to Update the SSO Database](../core/how-to-update-the-sso-database.md) </span></span>  
 [<span data-ttu-id="5f4cb-132">Uso de SSO</span><span class="sxs-lookup"><span data-stu-id="5f4cb-132">Using SSO</span></span>](../core/using-sso.md)