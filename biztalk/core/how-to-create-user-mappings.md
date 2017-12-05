---
title: "Cómo crear asignaciones de usuario | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maps [SSO], creating
- managing [SSO maps], creating user maps
ms.assetid: c2e9f0db-920b-4d89-8e1e-5dc92805fd23
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 019adf0cd41c643ac77790c96a3450bb967ddd6b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-create-user-mappings"></a><span data-ttu-id="d3bc6-102">Cómo crear asignaciones de usuario</span><span class="sxs-lookup"><span data-stu-id="d3bc6-102">How to Create User Mappings</span></span>
<span data-ttu-id="d3bc6-103">Utilice este comando para crear una o más asignaciones de usuarios, según se especifica en el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="d3bc6-103">Use this command to create one or more user mappings, as specified in the XML file.</span></span> <span data-ttu-id="d3bc6-104">A continuación, se muestra un archivo XML de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d3bc6-104">The following is an example XML file.</span></span>  
  
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
  
 <span data-ttu-id="d3bc6-105">Si se ha cambiado la cuenta de usuario, deberá utilizar este comando para crear una asignación para la nueva cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="d3bc6-105">If a user account is changed, you must use this command to create a mapping for the new user account.</span></span> <span data-ttu-id="d3bc6-106">También debería quitar la asignación de usuarios antigua.</span><span class="sxs-lookup"><span data-stu-id="d3bc6-106">You should also remove the old user mapping.</span></span> <span data-ttu-id="d3bc6-107">Para obtener más información acerca de cómo quitar una asignación, vea [cómo eliminar asignaciones de usuario](../core/how-to-delete-user-mappings.md).</span><span class="sxs-lookup"><span data-stu-id="d3bc6-107">For more information about removing a mapping, see [How to Delete User Mappings](../core/how-to-delete-user-mappings.md).</span></span>  
  
 <span data-ttu-id="d3bc6-108">Si ha creado una asignación de usuarios y desea utilizarla en el sistema de SSO, primero deberá habilitarla.</span><span class="sxs-lookup"><span data-stu-id="d3bc6-108">After you create a user mapping, you must enable it before you can use this mapping in the SSO system.</span></span> <span data-ttu-id="d3bc6-109">Para obtener más información, consulte [cómo habilitar una asignación de usuarios](../core/how-to-enable-a-user-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="d3bc6-109">For more information, see [How to Enable a User Mapping](../core/how-to-enable-a-user-mapping.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d3bc6-110">Las asignaciones de usuarios solo admiten grupos de dominio.</span><span class="sxs-lookup"><span data-stu-id="d3bc6-110">Only domain groups are supported for user mappings.</span></span>  
  
### <a name="to-create-user-mappings-using-the-administration-utility"></a><span data-ttu-id="d3bc6-111">Para crear asignaciones de usuarios con la utilidad de administración</span><span class="sxs-lookup"><span data-stu-id="d3bc6-111">To create user mappings using the administration utility</span></span>  
  
1.  <span data-ttu-id="d3bc6-112">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="d3bc6-112">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="d3bc6-113">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="d3bc6-113">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="d3bc6-114">El directorio de instalación predeterminado es \< *unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="d3bc6-114">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="d3bc6-115">Tipo de **ssomanage – createmappings  *\<asignaciones de nombre de archivo\>***, donde  *\<asignaciones de nombre de archivo\>*  es el nombre del archivo que contiene las asignaciones de usuarios que desea crear.</span><span class="sxs-lookup"><span data-stu-id="d3bc6-115">Type **ssomanage –createmappings *\<mappings file name\>***, where *\<mappings file name\>* is the name of file that contains the user mapping(s) you want to create.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d3bc6-116">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="d3bc6-116">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-create-user-mappings-using-the-client-utility"></a><span data-ttu-id="d3bc6-117">Para crear asignaciones de usuarios con la utilidad de cliente</span><span class="sxs-lookup"><span data-stu-id="d3bc6-117">To create user mappings using the client utility</span></span>  
  
1.  <span data-ttu-id="d3bc6-118">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="d3bc6-118">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="d3bc6-119">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="d3bc6-119">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="d3bc6-120">El directorio de instalación predeterminado es \< *unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="d3bc6-120">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="d3bc6-121">Tipo de **ssoclient – setcredentials  *\<nombre de la aplicación \>*** , donde  *\<nombre de la aplicación \>*  es el nombre de aplicación afiliada que desea crear una asignación para el usuario.</span><span class="sxs-lookup"><span data-stu-id="d3bc6-121">Type **ssoclient –setcredentials *\<application name \>***, where *\<application name \>* is the name of affiliate application that the user wants to create a mapping for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d3bc6-122">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="d3bc6-122">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3bc6-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3bc6-123">See Also</span></span>  
 <span data-ttu-id="d3bc6-124">[Asignaciones de SSO](../core/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="d3bc6-124">[SSO Mappings](../core/sso-mappings.md) </span></span>  
 <span data-ttu-id="d3bc6-125">[Administrar aplicaciones afiliadas](../core/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="d3bc6-125">[Managing Affiliate Applications](../core/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="d3bc6-126">Administración de asignaciones de usuarios</span><span class="sxs-lookup"><span data-stu-id="d3bc6-126">Managing User Mappings</span></span>](../core/managing-user-mappings.md)