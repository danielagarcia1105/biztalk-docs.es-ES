---
title: Cómo deshabilitar una asignación de usuario | Microsoft Docs
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
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e49f524337fffde9261af4aa2cd64c75e307ccb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972637"
---
# <a name="how-to-disable-a-user-mapping"></a><span data-ttu-id="e26e0-102">Cómo deshabilitar una asignación de usuarios</span><span class="sxs-lookup"><span data-stu-id="e26e0-102">How to Disable a User Mapping</span></span>
<span data-ttu-id="e26e0-103">Puede deshabilitar una asignación de usuarios cuando desee desactivar todas las operaciones que están asociadas a una asignación determinada.</span><span class="sxs-lookup"><span data-stu-id="e26e0-103">You can disable a user mapping when you want to turn off all operations associated with a given mapping.</span></span> <span data-ttu-id="e26e0-104">Debe deshabilitar una asignación de usuarios antes de que pueda quitarla.</span><span class="sxs-lookup"><span data-stu-id="e26e0-104">You must disable a user mapping before you can remove it.</span></span>  
  
 <span data-ttu-id="e26e0-105">Cuando se deshabilita una asignación de usuario, aparecerá como (D) *\<dominio\>\\< nombre de usuario\>* al enumerar las asignaciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="e26e0-105">When you disable a user mapping, it will appear as (D) *\<domain\>\\<username\>* when you list the user mappings.</span></span>  
  
### <a name="to-disable-a-user-mapping-using-the-administration-utility"></a><span data-ttu-id="e26e0-106">Para deshabilitar una asignación de usuarios con la utilidad de administración</span><span class="sxs-lookup"><span data-stu-id="e26e0-106">To disable a user mapping using the administration utility</span></span>  
  
1. <span data-ttu-id="e26e0-107">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="e26e0-107">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="e26e0-108">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="e26e0-108">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="e26e0-109">El directorio de instalación predeterminado es  *\<unidad\>*: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="e26e0-109">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="e26e0-110">Tipo **ssomanage-disablemapping  *\<dominio\>*\\*\<username\> \<nombre de la aplicación\>**  <em>, donde *\<dominio\></em>  es el dominio de Windows para la cuenta de usuario y *\<username\>* es el Nombre de usuario de Windows para el que desea deshabilitar las credenciales, y *\<nombre de la aplicación\>* es el nombre de la aplicación afiliada que desea quitar la asignación de usuario.</span><span class="sxs-lookup"><span data-stu-id="e26e0-110">Type **ssomanage –disablemapping *\<domain\>*\\*\<username\> \<application name\>**<em>, where *\<domain\></em> is the Windows domain for the user account, and *\<username\>* is the Windows user name for which you want to disable the credentials, and *\<application name\>* is the name of the affiliate application you want to remove the user mapping for.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="e26e0-111">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="e26e0-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-disable-a-user-mapping-using-the-client-utility"></a><span data-ttu-id="e26e0-112">Para deshabilitar una asignación de usuarios con la utilidad de cliente</span><span class="sxs-lookup"><span data-stu-id="e26e0-112">To disable a user mapping using the client utility</span></span>  
  
1. <span data-ttu-id="e26e0-113">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="e26e0-113">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="e26e0-114">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="e26e0-114">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="e26e0-115">El directorio de instalación predeterminado es  *\<unidad\>*: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="e26e0-115">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="e26e0-116">Tipo ** ssoclient-disablemapping *\<nombre de la aplicación\>**<em>, donde *\<nombre de la aplicación\></em>  es el nombre de la aplicación afiliada que desea quitar el asignación de usuario.</span><span class="sxs-lookup"><span data-stu-id="e26e0-116">Type **ssoclient –disablemapping *\<application name\>**<em>, where *\<application name\></em> is the name of the affiliate application you want to remove the user mapping for.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="e26e0-117">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="e26e0-117">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e26e0-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e26e0-118">See Also</span></span>  
 <span data-ttu-id="e26e0-119">[Asignaciones de inicio de sesión único](../core/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="e26e0-119">[SSO Mappings](../core/sso-mappings.md) </span></span>  
 <span data-ttu-id="e26e0-120">[Administrar aplicaciones afiliadas](../core/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="e26e0-120">[Managing Affiliate Applications](../core/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="e26e0-121">Administración de asignaciones de usuarios</span><span class="sxs-lookup"><span data-stu-id="e26e0-121">Managing User Mappings</span></span>](../core/managing-user-mappings.md)