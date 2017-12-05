---
title: "Cómo establecer el servidor de SSO | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- servers, selecting [SSO]
- SSO, selecting servers
- managing [SSO], selecting servers
- SSOManage [SSO]
ms.assetid: a0b0176d-b426-4ab1-8a7e-1f96f4214683
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7dab9df7b5444b437f12737c37036b592a70aad
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-set-the-sso-server"></a><span data-ttu-id="b332b-102">Cómo establecer el servidor de SSO</span><span class="sxs-lookup"><span data-stu-id="b332b-102">How to Set the SSO Server</span></span>
<span data-ttu-id="b332b-103">Cada vez que utilice ssomanage, en primer lugar debe seleccionar al usuario para el servidor de inicio de sesión único con el que desea establecer la conexión.</span><span class="sxs-lookup"><span data-stu-id="b332b-103">Each time you use ssomanage, you must first point the user to the Single Sign-On server you want to connect to.</span></span>  
  
 <span data-ttu-id="b332b-104">Puede hacerlo de una de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="b332b-104">You can do this in one of two ways:</span></span>  
  
-   <span data-ttu-id="b332b-105">Los usuarios pueden seleccionarse a sí mismos para el servidor de inicio de sesión único correcto.</span><span class="sxs-lookup"><span data-stu-id="b332b-105">Individual users can point themselves to the correct Single Sign-On Server.</span></span>  
  
-   <span data-ttu-id="b332b-106">Un administrador de equipo local del servidor de inicio de sesión único puede seleccionar a todos los miembros de la cuenta de usuarios de inicio de sesión único en este servidor.</span><span class="sxs-lookup"><span data-stu-id="b332b-106">A local computer administrator for the Single Sign-On server can point all the members of the Single Sign-On Users account to this server.</span></span>  
  
### <a name="to-set-the-enterprise-single-sign-on-server-using-the-mmc-snap-in"></a><span data-ttu-id="b332b-107">Para establecer el servidor de inicio de sesión único empresarial con el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="b332b-107">To set the Enterprise Single Sign-On Server using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="b332b-108">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="b332b-108">Click **Start**, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="b332b-109">En el complemento MMC en el **raíz de consola**, haga clic en **Enterprise Single Sign-On**y haga clic en **seleccione**.</span><span class="sxs-lookup"><span data-stu-id="b332b-109">In the MMC Snap-In under the **Console Root**, right-click **Enterprise Single Sign-On**, and click **Select**.</span></span>  
  
3.  <span data-ttu-id="b332b-110">Desplácese al servidor correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b332b-110">Browse to the desired server.</span></span>  
  
4.  <span data-ttu-id="b332b-111">Si es necesario, seleccione la **establecer servidor de SSO para todos los usuarios** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="b332b-111">If appropriate, select the **Set SSO Server for all users** check box.</span></span>  
  
5.  <span data-ttu-id="b332b-112">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b332b-112">Click **OK**.</span></span>  
  
### <a name="to-set-the-enterprise-single-sign-on-server-for-a-single-user-using-the-command-line"></a><span data-ttu-id="b332b-113">Para establecer el servidor de inicio de sesión único empresarial para un solo usuario con la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="b332b-113">To set the Enterprise Single Sign-On Server for a single user using the command line</span></span>  
  
1.  <span data-ttu-id="b332b-114">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="b332b-114">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="b332b-115">En el símbolo del sistema, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="b332b-115">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="b332b-116">El directorio de instalación predeterminado es  **\<unidad\>**: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="b332b-116">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="b332b-117">Tipo de **ssomanage – server \<el nombre del servidor SSO\>**, donde  **\<el nombre del servidor SSO\>**  es el nombre del equipo del servidor de inicio de sesión único en el usuario va a conectar.</span><span class="sxs-lookup"><span data-stu-id="b332b-117">Type **ssomanage –server \<SSO server name\>**, where **\<SSO server name\>** is the computer name of the Single Sign-On Server the user wants to connect to.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b332b-118">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="b332b-118">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-set-the-enterprise-single-sign-on-server-for-all-users-using-the-command-line"></a><span data-ttu-id="b332b-119">Para establecer el servidor de inicio de sesión único empresarial para todos los usuarios con la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="b332b-119">To set the Enterprise Single Sign-On Server for all users using the command line</span></span>  
  
1.  <span data-ttu-id="b332b-120">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="b332b-120">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="b332b-121">En el símbolo del sistema, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="b332b-121">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="b332b-122">El directorio de instalación predeterminado es  **\<unidad\>**: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="b332b-122">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="b332b-123">Tipo de **ssomanage – serverall \<el nombre del servidor SSO\>**, donde  **\<el nombre del servidor SSO\>**  es el nombre de equipo único inicio de sesión del servidor de todos los señalarán a los miembros de la cuenta de usuarios de inicio de sesión único.</span><span class="sxs-lookup"><span data-stu-id="b332b-123">Type **ssomanage –serverall \<SSO server name\>**, where **\<SSO server name\>** is the computer name of the Single Sign-On Server all members of the Single Sign-On Users account will be pointed to.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b332b-124">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="b332b-124">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-determine-the-enterprise-single-sign-on-server-to-which-a-user-is-connected-using-the-command-line"></a><span data-ttu-id="b332b-125">Para determinar el servidor de inicio de sesión único empresarial al que se conecta un usuario con la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="b332b-125">To determine the Enterprise Single Sign-On Server to which a user is connected using the command line</span></span>  
  
1.  <span data-ttu-id="b332b-126">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="b332b-126">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="b332b-127">En el símbolo del sistema, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="b332b-127">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="b332b-128">El directorio de instalación predeterminado es  **\<unidad\>**: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="b332b-128">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="b332b-129">Tipo de **ssomanage – showserver**.</span><span class="sxs-lookup"><span data-stu-id="b332b-129">Type **ssomanage –showserver**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b332b-130">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="b332b-130">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b332b-131">Este comando muestra la configuración del usuario actual (y la de otros usuarios, si los hubiera).</span><span class="sxs-lookup"><span data-stu-id="b332b-131">This command displays the settings for the current user as well as for other users if they exist.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b332b-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="b332b-132">See Also</span></span>  
 <span data-ttu-id="b332b-133">[Cómo habilitar SSO](../core/how-to-enable-sso.md) </span><span class="sxs-lookup"><span data-stu-id="b332b-133">[How to Enable SSO](../core/how-to-enable-sso.md) </span></span>  
 <span data-ttu-id="b332b-134">[Cómo deshabilitar SSO](../core/how-to-disable-sso.md) </span><span class="sxs-lookup"><span data-stu-id="b332b-134">[How to Disable SSO](../core/how-to-disable-sso.md) </span></span>  
 <span data-ttu-id="b332b-135">[Cómo mostrar la información de la base de datos SSO](../core/how-to-display-the-sso-database-information.md) </span><span class="sxs-lookup"><span data-stu-id="b332b-135">[How to Display the SSO Database Information](../core/how-to-display-the-sso-database-information.md) </span></span>  
 [<span data-ttu-id="b332b-136">Uso de SSO</span><span class="sxs-lookup"><span data-stu-id="b332b-136">Using SSO</span></span>](../core/using-sso.md)