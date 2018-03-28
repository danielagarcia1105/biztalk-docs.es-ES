---
title: Cómo deshabilitar una asignación de usuario | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disabling, maps
- managing [SSO maps], disabling
- maps [SSO], disabling
ms.assetid: 9b6eaff2-674b-49f7-8d5c-3e040a7dc7f8
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b17ab68356d5d39f3f839f736261d4a7ef79c78
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-disable-a-user-mapping"></a><span data-ttu-id="e37ca-102">Cómo deshabilitar una asignación de usuario</span><span class="sxs-lookup"><span data-stu-id="e37ca-102">How to Disable a User Mapping</span></span>
<span data-ttu-id="e37ca-103">Puede deshabilitar una asignación de usuarios cuando desee desactivar todas las operaciones que están asociadas a una asignación determinada.</span><span class="sxs-lookup"><span data-stu-id="e37ca-103">You can disable a user mapping when you want to turn off all operations associated with a given mapping.</span></span> <span data-ttu-id="e37ca-104">Debe deshabilitar una asignación de usuarios antes de que pueda quitarla.</span><span class="sxs-lookup"><span data-stu-id="e37ca-104">You must disable a user mapping before you can remove it.</span></span>  
  
 <span data-ttu-id="e37ca-105">Cuando se deshabilita una asignación de usuarios, aparecerá como (D) *\<dominio\>\\< nombre de usuario\>* al enumerar las asignaciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="e37ca-105">When you disable a user mapping, it will appear as (D) *\<domain\>\\<username\>* when you list the user mappings.</span></span>  
  
### <a name="to-disable-a-user-mapping-using-the-administration-utility"></a><span data-ttu-id="e37ca-106">Para deshabilitar una asignación de usuarios con la utilidad de administración</span><span class="sxs-lookup"><span data-stu-id="e37ca-106">To disable a user mapping using the administration utility</span></span>  
  
1.  <span data-ttu-id="e37ca-107">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="e37ca-107">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="e37ca-108">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="e37ca-108">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="e37ca-109">El directorio de instalación predeterminado es  *\<unidad\>*: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="e37ca-109">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="e37ca-110">Tipo **ssomanage-disablemapping  *\<dominio\>*\\*\<nombre de usuario\> \<nombre de la aplicación\>***, donde *\<dominio\>* es el dominio de Windows para la cuenta de usuario y *\<nombre de usuario\>* es el nombre de usuario de Windows para que desea deshabilitar las credenciales y *\<nombre de la aplicación\>* es el nombre de la aplicación afiliada que desea quitar la asignación de usuario.</span><span class="sxs-lookup"><span data-stu-id="e37ca-110">Type **ssomanage –disablemapping *\<domain\>*\\*\<username\> \<application name\>***, where *\<domain\>* is the Windows domain for the user account, and *\<username\>* is the Windows user name for which you want to disable the credentials, and *\<application name\>* is the name of the affiliate application you want to remove the user mapping for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e37ca-111">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="e37ca-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-disable-a-user-mapping-using-the-client-utility"></a><span data-ttu-id="e37ca-112">Para deshabilitar una asignación de usuarios con la utilidad de cliente</span><span class="sxs-lookup"><span data-stu-id="e37ca-112">To disable a user mapping using the client utility</span></span>  
  
1.  <span data-ttu-id="e37ca-113">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="e37ca-113">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="e37ca-114">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="e37ca-114">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="e37ca-115">El directorio de instalación predeterminado es  *\<unidad\>*: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="e37ca-115">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="e37ca-116">Tipo ** ssoclient – disablemapping *\<nombre de la aplicación\>***, donde *\<nombre de la aplicación\>* es el nombre de la aplicación afiliada que desea quitar la asignación de usuario.</span><span class="sxs-lookup"><span data-stu-id="e37ca-116">Type **ssoclient –disablemapping *\<application name\>***, where *\<application name\>* is the name of the affiliate application you want to remove the user mapping for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e37ca-117">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="e37ca-117">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e37ca-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e37ca-118">See Also</span></span>  
 <span data-ttu-id="e37ca-119">[Asignaciones de SSO](../core/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="e37ca-119">[SSO Mappings](../core/sso-mappings.md) </span></span>  
 <span data-ttu-id="e37ca-120">[Administrar aplicaciones afiliadas](../core/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="e37ca-120">[Managing Affiliate Applications](../core/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="e37ca-121">Administración de asignaciones de usuarios</span><span class="sxs-lookup"><span data-stu-id="e37ca-121">Managing User Mappings</span></span>](../core/managing-user-mappings.md)