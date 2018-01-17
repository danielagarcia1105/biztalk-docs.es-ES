---
title: "Cómo eliminar asignaciones de usuario | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maps [SSO], deleting
- managing [SSO maps], deleting user maps
ms.assetid: de511113-b0b0-4920-91dc-4c9e380fda58
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03f7c1fa75b6fe7bb4c78e18c97fccd1404f89c9
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-delete-user-mappings"></a><span data-ttu-id="9444a-102">Cómo eliminar asignaciones de usuario</span><span class="sxs-lookup"><span data-stu-id="9444a-102">How to Delete User Mappings</span></span>
<span data-ttu-id="9444a-103">Utilice estos comandos para eliminar una o varias asignaciones de usuario, como especificó en el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="9444a-103">Use these commands to delete one or more user mappings, as specified in the XML file.</span></span> <span data-ttu-id="9444a-104">A continuación, se muestra un archivo XML de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9444a-104">The following is an example XML file.</span></span>  
  
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
  
 <span data-ttu-id="9444a-105">Si el usuario no es miembro de la cuenta Usuarios de aplicación o si no existe en Active Directory, debería utilizar este comando para quitar la asignación de usuario de la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="9444a-105">If a user is not a member of the Application Users account, or does not exist in Active Directory, you should use this command to remove the user mapping from the SSO database.</span></span>  
  
 <span data-ttu-id="9444a-106">Si la cuenta de usuario ha cambiado, debe utilizar este comando para quitar la asignación de usuario antigua y luego crear una asignación de usuario nueva para la cuenta de usuario nueva.</span><span class="sxs-lookup"><span data-stu-id="9444a-106">If a user account is changed, you must use this command to remove the old user mapping, and then create a new user mapping for the new user account.</span></span> <span data-ttu-id="9444a-107">Para obtener más información acerca de cómo crear una asignación, vea [cómo crear asignaciones de usuario](../core/how-to-create-user-mappings.md).</span><span class="sxs-lookup"><span data-stu-id="9444a-107">For more information about creating a mapping, see [How to Create User Mappings](../core/how-to-create-user-mappings.md).</span></span>  
  
### <a name="to-delete-user-mappings-using-the-administration-utility"></a><span data-ttu-id="9444a-108">Para eliminar asignaciones de usuarios con la utilidad de administración</span><span class="sxs-lookup"><span data-stu-id="9444a-108">To delete user mappings using the administration utility</span></span>  
  
1.  <span data-ttu-id="9444a-109">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="9444a-109">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="9444a-110">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="9444a-110">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="9444a-111">El directorio de instalación predeterminado es \< *unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="9444a-111">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="9444a-112">Tipo **ssomanage – deletemappings  *\<asignaciones de nombre de archivo\>***, donde \<* asignaciones de nombre de archivo* \> es el nombre del archivo que contiene el asignaciones de usuarios que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="9444a-112">Type **ssomanage –deletemappings *\<mappings file name\>***, where \<*mappings file name*\> is the name of the file that contains the user mapping(s) you want to delete.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9444a-113">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="9444a-113">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-delete-a-specific-user-mapping-using-the-administration-utility"></a><span data-ttu-id="9444a-114">Para eliminar una asignación de usuario específica con la utilidad de administración</span><span class="sxs-lookup"><span data-stu-id="9444a-114">To delete a specific user mapping using the administration utility</span></span>  
  
1.  <span data-ttu-id="9444a-115">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="9444a-115">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="9444a-116">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="9444a-116">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="9444a-117">El directorio de instalación predeterminado es  *\<unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="9444a-117">The default installation directory is *\<drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="9444a-118">Tipo de  **ssomanage-deletemapping  *\<dominio\>*\\*\<nombre de usuario\> *   *\<nombre de la aplicación\>***, donde  *\<dominio\>*  es el dominio de Windows para la cuenta de usuario  *\<denombredeusuario\>*  es el nombre de usuario de Windows, y \<* nombre de la aplicación* \> es la aplicación específica para la que desea quitar la asignación de usuario.</span><span class="sxs-lookup"><span data-stu-id="9444a-118">Type **ssomanage –deletemapping *\<domain\>*\\*\<username\>* *\<application name\>***, where *\<domain\>* is the Windows domain for the user account, *\<username\>* is the Windows user name, and \<*application name*\> is the specific application for which you want to remove the user mapping.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9444a-119">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="9444a-119">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-delete-a-user-mapping-using-the-client-utility"></a><span data-ttu-id="9444a-120">Para eliminar una asignación de usuario con la utilidad de cliente</span><span class="sxs-lookup"><span data-stu-id="9444a-120">To delete a user mapping using the client utility</span></span>  
  
1.  <span data-ttu-id="9444a-121">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="9444a-121">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="9444a-122">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="9444a-122">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="9444a-123">El directorio de instalación predeterminado es  *\<unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="9444a-123">The default installation directory is *\<drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="9444a-124">Tipo ** ssoclient – deletemapping *\<nombre de la aplicación\>***, donde  *\<nombre de la aplicación\>*  es el nombre de la aplicación afiliada que desea quitar la asignación de usuario.</span><span class="sxs-lookup"><span data-stu-id="9444a-124">Type **ssoclient –deletemapping *\<application name\>***, where *\<application name\>* is the name of the affiliate application you want to remove the user mapping for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9444a-125">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="9444a-125">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9444a-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="9444a-126">See Also</span></span>  
 <span data-ttu-id="9444a-127">[Asignaciones de SSO](../core/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="9444a-127">[SSO Mappings](../core/sso-mappings.md) </span></span>  
 <span data-ttu-id="9444a-128">[Administrar aplicaciones afiliadas](../core/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="9444a-128">[Managing Affiliate Applications](../core/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="9444a-129">Administración de asignaciones de usuarios</span><span class="sxs-lookup"><span data-stu-id="9444a-129">Managing User Mappings</span></span>](../core/managing-user-mappings.md)