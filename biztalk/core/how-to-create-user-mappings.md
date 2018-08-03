---
title: Cómo crear asignaciones de usuario | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps [SSO], creating
- managing [SSO maps], creating user maps
ms.assetid: c2e9f0db-920b-4d89-8e1e-5dc92805fd23
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 493f9b505288ea10e48eb0cf8607a870b5509425
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009893"
---
# <a name="how-to-create-user-mappings"></a><span data-ttu-id="adc58-102">Cómo crear asignaciones de usuario</span><span class="sxs-lookup"><span data-stu-id="adc58-102">How to Create User Mappings</span></span>
<span data-ttu-id="adc58-103">Utilice este comando para crear una o más asignaciones de usuarios, según se especifica en el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="adc58-103">Use this command to create one or more user mappings, as specified in the XML file.</span></span> <span data-ttu-id="adc58-104">A continuación, se muestra un archivo XML de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="adc58-104">The following is an example XML file.</span></span>  
  
```  
<sso>  
<mapping>  
<windowsDomain>domain</windowsDomain>   
<windowsUserId>WindowsUserName</windowsUserId>   
<externalApplication>Application name1</externalApplication>   
<externalUserId>App1UserName</externalUserId>   
</mapping>  
<mapping>  
<windowsDomain>domain</windowsDomain>   
<windowsUserId>WindowsUserName</windowsUserId>   
<externalApplication>Application name2</externalApplication>   
<externalUserId>App2UserName</externalUserId>   
</mapping>  
</sso>  
  
```  
  
 <span data-ttu-id="adc58-105">Si se ha cambiado la cuenta de usuario, deberá utilizar este comando para crear una asignación para la nueva cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="adc58-105">If a user account is changed, you must use this command to create a mapping for the new user account.</span></span> <span data-ttu-id="adc58-106">También debería quitar la asignación de usuarios antigua.</span><span class="sxs-lookup"><span data-stu-id="adc58-106">You should also remove the old user mapping.</span></span> <span data-ttu-id="adc58-107">Para obtener más información acerca de cómo quitar una asignación, vea [cómo eliminar asignaciones de usuario](../core/how-to-delete-user-mappings.md).</span><span class="sxs-lookup"><span data-stu-id="adc58-107">For more information about removing a mapping, see [How to Delete User Mappings](../core/how-to-delete-user-mappings.md).</span></span>  
  
 <span data-ttu-id="adc58-108">Si ha creado una asignación de usuarios y desea utilizarla en el sistema de SSO, primero deberá habilitarla.</span><span class="sxs-lookup"><span data-stu-id="adc58-108">After you create a user mapping, you must enable it before you can use this mapping in the SSO system.</span></span> <span data-ttu-id="adc58-109">Para obtener más información, consulte [cómo habilitar una asignación de usuarios](../core/how-to-enable-a-user-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="adc58-109">For more information, see [How to Enable a User Mapping](../core/how-to-enable-a-user-mapping.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="adc58-110">Las asignaciones de usuarios solo admiten grupos de dominio.</span><span class="sxs-lookup"><span data-stu-id="adc58-110">Only domain groups are supported for user mappings.</span></span>  
  
### <a name="to-create-user-mappings-using-the-administration-utility"></a><span data-ttu-id="adc58-111">Para crear asignaciones de usuarios con la utilidad de administración</span><span class="sxs-lookup"><span data-stu-id="adc58-111">To create user mappings using the administration utility</span></span>  
  
1. <span data-ttu-id="adc58-112">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="adc58-112">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="adc58-113">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="adc58-113">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="adc58-114">El directorio de instalación predeterminado es \< *unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="adc58-114">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="adc58-115">Tipo ** ssomanage – createmappings *\<nombre del archivo de asignaciones\>**<em>, donde *\<nombre del archivo de asignaciones\></em>  es el nombre del archivo que contiene las asignaciones de usuarios que desee Para crear.</span><span class="sxs-lookup"><span data-stu-id="adc58-115">Type **ssomanage –createmappings *\<mappings file name\>**<em>, where *\<mappings file name\></em> is the name of file that contains the user mapping(s) you want to create.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="adc58-116">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="adc58-116">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-create-user-mappings-using-the-client-utility"></a><span data-ttu-id="adc58-117">Para crear asignaciones de usuarios con la utilidad de cliente</span><span class="sxs-lookup"><span data-stu-id="adc58-117">To create user mappings using the client utility</span></span>  
  
1. <span data-ttu-id="adc58-118">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="adc58-118">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="adc58-119">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="adc58-119">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="adc58-120">El directorio de instalación predeterminado es \< *unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="adc58-120">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="adc58-121">Tipo ** ssoclient – setcredentials *\<nombre de la aplicación \> ** <em>, donde *\<nombre de la aplicación \></em>  es el nombre de la aplicación afiliada que el usuario desea crear una asignación.</span><span class="sxs-lookup"><span data-stu-id="adc58-121">Type **ssoclient –setcredentials *\<application name \>**<em>, where *\<application name \></em> is the name of affiliate application that the user wants to create a mapping for.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="adc58-122">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="adc58-122">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adc58-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="adc58-123">See Also</span></span>  
 <span data-ttu-id="adc58-124">[Asignaciones de inicio de sesión único](../core/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="adc58-124">[SSO Mappings](../core/sso-mappings.md) </span></span>  
 <span data-ttu-id="adc58-125">[Administrar aplicaciones afiliadas](../core/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="adc58-125">[Managing Affiliate Applications](../core/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="adc58-126">Administración de asignaciones de usuarios</span><span class="sxs-lookup"><span data-stu-id="adc58-126">Managing User Mappings</span></span>](../core/managing-user-mappings.md)