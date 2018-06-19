---
title: Cómo eliminar asignaciones de usuario | Documentos de Microsoft
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82c4cdff-b82d-4cfd-8e20-220a2fe78656
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: a9d0a31c3dbc9d5980f59d9f30d20ec15f603a38
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "30251088"
---
# <a name="how-to-delete-user-mappings"></a><span data-ttu-id="1c7a3-102">Cómo eliminar asignaciones de usuario</span><span class="sxs-lookup"><span data-stu-id="1c7a3-102">How to Delete User Mappings</span></span>
<span data-ttu-id="1c7a3-103">Utilice estos comandos para eliminar una o varias asignaciones de usuario, como especificó en el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="1c7a3-103">Use these commands to delete one or more user mappings, as specified in the XML file.</span></span> <span data-ttu-id="1c7a3-104">A continuación, se muestra un archivo XML de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1c7a3-104">The following is an example XML file.</span></span>  
  
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
  
 <span data-ttu-id="1c7a3-105">Si un usuario no es un miembro de la cuenta de usuarios de la aplicación, o no existe en Active Directory, debe utilizar este comando para quitar la asignación de usuario de la base de datos de credenciales.</span><span class="sxs-lookup"><span data-stu-id="1c7a3-105">If a user is not a member of the Application Users account, or does not exist in Active Directory, you should use this command to remove the user mapping from the Credential database.</span></span>  
  
 <span data-ttu-id="1c7a3-106">Si la cuenta de usuario ha cambiado, debe utilizar este comando para quitar la asignación de usuario antigua y luego crear una asignación de usuario nueva para la cuenta de usuario nueva.</span><span class="sxs-lookup"><span data-stu-id="1c7a3-106">If a user account is changed, you must use this command to remove the old user mapping, and then create a new user mapping for the new user account.</span></span> <span data-ttu-id="1c7a3-107">Para obtener más información acerca de cómo crear una asignación, vea [cómo crear asignaciones de usuario](../esso/how-to-create-user-mappings.md).</span><span class="sxs-lookup"><span data-stu-id="1c7a3-107">For more information about creating a mapping, see [How to Create User Mappings](../esso/how-to-create-user-mappings.md).</span></span>  
  
### <a name="to-delete-user-mappings-using-the-administration-utility"></a><span data-ttu-id="1c7a3-108">Para eliminar asignaciones de usuarios con la utilidad de administración</span><span class="sxs-lookup"><span data-stu-id="1c7a3-108">To delete user mappings using the administration utility</span></span>  
  
1.  <span data-ttu-id="1c7a3-109">Haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="1c7a3-109">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="1c7a3-110">En el símbolo del sistema, vaya al directorio de instalación Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="1c7a3-110">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="1c7a3-111">El directorio de instalación predeterminado es \< *unidad*>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="1c7a3-111">The default installation directory is \<*drive*>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="1c7a3-112">Tipo de `ssomanage –deletemappings <mappings file name>`, donde \< *asignaciones de nombre de archivo*> es el nombre del archivo que contiene las asignaciones de usuario que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="1c7a3-112">Type `ssomanage –deletemappings <mappings file name>`, where \<*mappings file name*> is the name of the file that contains the user mappings that you want to delete.</span></span>  
  
### <a name="to-delete-a-specific-user-mapping-using-the-administration-utility"></a><span data-ttu-id="1c7a3-113">Para eliminar una asignación de usuario específica con la utilidad de administración</span><span class="sxs-lookup"><span data-stu-id="1c7a3-113">To delete a specific user mapping using the administration utility</span></span>  
  
1.  <span data-ttu-id="1c7a3-114">Haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="1c7a3-114">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="1c7a3-115">En el símbolo del sistema, vaya al directorio de instalación Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="1c7a3-115">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="1c7a3-116">El directorio de instalación predeterminado es  *\<unidad >*: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="1c7a3-116">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="1c7a3-117">Tipo de `ssomanage –deletemapping <domain>\<username> <application name>`, donde  *\<dominio >* es el dominio de Windows para la cuenta de usuario  *\<nombre de usuario >* es el nombre de usuario de Windows, y \< *nombre de la aplicación*> es la aplicación específica para la que desea quitar la asignación de usuario.</span><span class="sxs-lookup"><span data-stu-id="1c7a3-117">Type `ssomanage –deletemapping <domain>\<username> <application name>`, where *\<domain>* is the Windows domain for the user account, *\<username>* is the Windows user name, and \<*application name*> is the specific application for which you want to remove the user mapping.</span></span>  
  
### <a name="to-delete-a-user-mapping-using-the-client-utility"></a><span data-ttu-id="1c7a3-118">Para eliminar una asignación de usuario con la utilidad de cliente</span><span class="sxs-lookup"><span data-stu-id="1c7a3-118">To delete a user mapping using the client utility</span></span>  
  
1.  <span data-ttu-id="1c7a3-119">Haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="1c7a3-119">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="1c7a3-120">En el símbolo del sistema, vaya al directorio de instalación Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="1c7a3-120">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="1c7a3-121">El directorio de instalación predeterminado es  *\<unidad >*: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="1c7a3-121">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="1c7a3-122">Tipo de `ssoclient –deletemapping <application name>`, donde  *\<nombre de aplicación >* es el nombre de la aplicación afiliada para la que desea quitar la asignación de usuario.</span><span class="sxs-lookup"><span data-stu-id="1c7a3-122">Type `ssoclient –deletemapping <application name>`, where *\<application name>* is the name of the affiliate application for which you want to remove the user mapping.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c7a3-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c7a3-123">See Also</span></span>  
 <span data-ttu-id="1c7a3-124">[Asignaciones de SSO](../esso/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="1c7a3-124">[SSO Mappings](../esso/sso-mappings.md) </span></span>  
 <span data-ttu-id="1c7a3-125">[Administrar aplicaciones afiliadas](../esso/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="1c7a3-125">[Managing Affiliate Applications](../esso/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="1c7a3-126">Administración de asignaciones de usuarios</span><span class="sxs-lookup"><span data-stu-id="1c7a3-126">Managing User Mappings</span></span>](../esso/managing-user-mappings.md)