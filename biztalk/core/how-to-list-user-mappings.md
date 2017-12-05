---
title: "Cómo enumerar las asignaciones de usuario | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [SSO maps], listing maps
- maps [SSO], listing maps
ms.assetid: f9b73785-3a59-45c8-9e88-d2d16b5a46aa
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04f988e9f63cccf27c42a33727d86452d34915aa
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-list-user-mappings"></a><span data-ttu-id="b3232-102">Cómo enumerar las asignaciones de usuario</span><span class="sxs-lookup"><span data-stu-id="b3232-102">How to List User Mappings</span></span>
<span data-ttu-id="b3232-103">Utilice este comando para listar todas las asignaciones existentes del usuario especificado.</span><span class="sxs-lookup"><span data-stu-id="b3232-103">Use this command to list all the existing mappings for the specified user.</span></span>  
  
 <span data-ttu-id="b3232-104">Para llevar a cabo esta tarea deberá ser administrador de SSO, administrador de aplicaciones, administrador afiliado de SSO o usuario.</span><span class="sxs-lookup"><span data-stu-id="b3232-104">You must be an SSO administrator, application administrator, SSO affiliate administrator, or user to do this task.</span></span>  
  
 <span data-ttu-id="b3232-105">Asignaciones de usuario habilitadas aparecen como (E) \< *dominio*\>\\*\<nombre de usuario\>*, mientras que deshabilita las asignaciones de usuario aparecen como (D) \< *dominio*\>\\*\<nombre de usuario\>*.</span><span class="sxs-lookup"><span data-stu-id="b3232-105">Enabled user mappings appear as (E) \<*domain*\>\\*\<username\>*, while disabled user mappings appear as (D) \<*domain*\>\\*\<username\>*.</span></span>  
  
### <a name="to-list-user-mappings-using-the-administration-utility"></a><span data-ttu-id="b3232-106">Para listar asignaciones de usuarios con la utilidad de administración</span><span class="sxs-lookup"><span data-stu-id="b3232-106">To list user mappings using the administration utility</span></span>  
  
1.  <span data-ttu-id="b3232-107">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="b3232-107">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="b3232-108">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="b3232-108">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="b3232-109">El directorio de instalación predeterminado es \< *unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="b3232-109">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="b3232-110">Realice una de las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="b3232-110">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="b3232-111">Tipo de **ssomanage – listmappings  *\<dominio\>\\< nombre de usuario\>***  para enumerar todas las asignaciones que un usuario determinado tiene en las aplicaciones afiliadas Si pertenece al lugar donde  *\<dominio\>*  es el dominio de Microsoft Windows para la cuenta de usuario y  *\<nombre de usuario\>*  es el Nombre de usuario de Windows para el que desea enumerar las asignaciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="b3232-111">Type **ssomanage –listmappings *\<domain\>\\<username\>*** to list all the mappings a given user has in the affiliate applications he/she belongs to, where *\<domain\>* is the Microsoft Windows domain for the user account, and *\<username\>* is the Windows user name for which you want to list the user mappings.</span></span> <span data-ttu-id="b3232-112">Si el usuario es un administrador afiliado o un administrador de SSO, este comando enumerará todas las asignaciones de ese usuario en todas las aplicaciones afiliadas.</span><span class="sxs-lookup"><span data-stu-id="b3232-112">If the user is an Affiliate Administrator or an SSO Administrator, this command will list all the mappings for that user in all the affiliate applications.</span></span>  
  
         <span data-ttu-id="b3232-113">O bien</span><span class="sxs-lookup"><span data-stu-id="b3232-113">Or</span></span>  
  
    -   <span data-ttu-id="b3232-114">Tipo de **ssomanage – listmappings  *\<nombre de la aplicación\>***  para enumerar todas las asignaciones de usuario para una aplicación determinada.</span><span class="sxs-lookup"><span data-stu-id="b3232-114">Type **ssomanage –listmappings *\<application name\>*** to list all the user mappings for a given application.</span></span>  
  
         <span data-ttu-id="b3232-115">O bien</span><span class="sxs-lookup"><span data-stu-id="b3232-115">Or</span></span>  
  
    -   <span data-ttu-id="b3232-116">Si eres un administrador de aplicaciones, escriba **ssomanage – listmappings  *\<dominio\>\\< nombre de usuario\>*   *\< nombre de la aplicación\>***  para enumerar todas las asignaciones de un usuario determinado tiene en las aplicaciones afiliadas que es un administrador.</span><span class="sxs-lookup"><span data-stu-id="b3232-116">If you are an application administrator, type **ssomanage –listmappings *\<domain\>\\<username\>* *\<application name\>*** to list all the mappings a given user has in the affiliate applications for which you are an administrator.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b3232-117">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="b3232-117">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-list-user-mappings-using-the-client-utility"></a><span data-ttu-id="b3232-118">Para listar asignaciones de usuarios con la utilidad de cliente</span><span class="sxs-lookup"><span data-stu-id="b3232-118">To list user mappings using the client utility</span></span>  
  
1.  <span data-ttu-id="b3232-119">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="b3232-119">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="b3232-120">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="b3232-120">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="b3232-121">El directorio de instalación predeterminado es \< *unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="b3232-121">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="b3232-122">Tipo de **ssoclient – listmappings** para enumerar todas las asignaciones.</span><span class="sxs-lookup"><span data-stu-id="b3232-122">Type **ssoclient –listmappings** to list all the mappings you have.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b3232-123">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="b3232-123">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3232-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3232-124">See Also</span></span>  
 <span data-ttu-id="b3232-125">[Cómo crear asignaciones de usuario](../core/how-to-create-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="b3232-125">[How to Create User Mappings](../core/how-to-create-user-mappings.md) </span></span>  
 <span data-ttu-id="b3232-126">[Asignaciones de SSO](../core/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="b3232-126">[SSO Mappings](../core/sso-mappings.md) </span></span>  
 <span data-ttu-id="b3232-127">[Administrar aplicaciones afiliadas](../core/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="b3232-127">[Managing Affiliate Applications](../core/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="b3232-128">Administración de asignaciones de usuarios</span><span class="sxs-lookup"><span data-stu-id="b3232-128">Managing User Mappings</span></span>](../core/managing-user-mappings.md)