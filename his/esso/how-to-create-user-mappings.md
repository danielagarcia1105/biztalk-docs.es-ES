---
title: Cómo crear asignaciones de usuario | Documentos de Microsoft
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb91879c-73f4-4e9e-9e5b-534f48cd5584
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 89fd7ab2ca83d23a37944447997becd2d3f008c2
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "30250968"
---
# <a name="how-to-create-user-mappings"></a><span data-ttu-id="07e06-102">Cómo crear asignaciones de usuario</span><span class="sxs-lookup"><span data-stu-id="07e06-102">How to Create User Mappings</span></span>
<span data-ttu-id="07e06-103">Use la **createmappings** comando para crear una o varias asignaciones de usuario, como se especifica en el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="07e06-103">Use the **createmappings** command to create one or more user mappings, as specified in the XML file.</span></span> <span data-ttu-id="07e06-104">A continuación, se muestra un archivo XML de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="07e06-104">The following is an example XML file.</span></span>  
  
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
  
 <span data-ttu-id="07e06-105">Si se ha cambiado la cuenta de usuario, deberá utilizar este comando para crear una asignación para la nueva cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="07e06-105">If a user account is changed, you must use this command to create a mapping for the new user account.</span></span> <span data-ttu-id="07e06-106">También debería quitar la asignación de usuarios antigua.</span><span class="sxs-lookup"><span data-stu-id="07e06-106">You should also remove the old user mapping.</span></span> <span data-ttu-id="07e06-107">Para obtener más información acerca de cómo quitar una asignación, vea [cómo eliminar asignaciones de usuario](../esso/how-to-delete-user-mappings.md).</span><span class="sxs-lookup"><span data-stu-id="07e06-107">For more information about removing a mapping, see [How to Delete User Mappings](../esso/how-to-delete-user-mappings.md).</span></span>  
  
 <span data-ttu-id="07e06-108">Después de crear una asignación de usuarios, debe habilitarla para poder usar esta asignación en el sistema de inicio de sesión único (SSO).</span><span class="sxs-lookup"><span data-stu-id="07e06-108">After you create a user mapping, you must enable it before you can use this mapping in the Single Sign-On (SSO) system.</span></span> <span data-ttu-id="07e06-109">Para obtener más información, consulte [cómo habilitar una asignación de usuarios](../esso/how-to-enable-a-user-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="07e06-109">For more information, see [How to Enable a User Mapping](../esso/how-to-enable-a-user-mapping.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="07e06-110">Las asignaciones de usuarios solo admiten grupos de dominio.</span><span class="sxs-lookup"><span data-stu-id="07e06-110">Only domain groups are supported for user mappings.</span></span>  
  
### <a name="to-create-user-mappings-using-the-administration-utility"></a><span data-ttu-id="07e06-111">Para crear asignaciones de usuarios con la utilidad de administración</span><span class="sxs-lookup"><span data-stu-id="07e06-111">To create user mappings using the administration utility</span></span>  
  
1.  <span data-ttu-id="07e06-112">Haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="07e06-112">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="07e06-113">En el símbolo del sistema, vaya al directorio de instalación Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="07e06-113">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="07e06-114">El directorio de instalación predeterminado es \< *unidad*>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="07e06-114">The default installation directory is \<*drive*>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="07e06-115">Tipo de `ssomanage –createmappings <mappings file name>`, donde  *\<asignaciones de nombre de archivo >* es el nombre del archivo que contiene las asignaciones de usuario que desea crear.</span><span class="sxs-lookup"><span data-stu-id="07e06-115">Type `ssomanage –createmappings <mappings file name>`, where *\<mappings file name>* is the name of the file that contains the user mappings that you want to create.</span></span>  
  
### <a name="to-create-user-mappings-using-the-client-utility"></a><span data-ttu-id="07e06-116">Para crear asignaciones de usuarios con la utilidad de cliente</span><span class="sxs-lookup"><span data-stu-id="07e06-116">To create user mappings using the client utility</span></span>  
  
1.  <span data-ttu-id="07e06-117">Haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="07e06-117">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="07e06-118">En el símbolo del sistema, vaya al directorio de instalación Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="07e06-118">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="07e06-119">El directorio de instalación predeterminado es \< *unidad*>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="07e06-119">The default installation directory is \<*drive*>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="07e06-120">Tipo de `ssoclient –setcredentials <application name >`, donde  *\<nombre de aplicación >* es el nombre de la aplicación afiliada que desea crear una asignación para el usuario.</span><span class="sxs-lookup"><span data-stu-id="07e06-120">Type `ssoclient –setcredentials <application name >`, where *\<application name >* is the name of the affiliate application that the user wants to create a mapping for.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07e06-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="07e06-121">See Also</span></span>  
 <span data-ttu-id="07e06-122">[Asignaciones de SSO](../esso/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="07e06-122">[SSO Mappings](../esso/sso-mappings.md) </span></span>  
 <span data-ttu-id="07e06-123">[Administrar aplicaciones afiliadas](../esso/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="07e06-123">[Managing Affiliate Applications](../esso/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="07e06-124">Administración de asignaciones de usuarios</span><span class="sxs-lookup"><span data-stu-id="07e06-124">Managing User Mappings</span></span>](../esso/managing-user-mappings.md)