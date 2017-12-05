---
title: "Cómo habilitar una asignación de usuario | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- enabling, user maps [SSO]
- maps [SSO], enabling
- managing [SSO maps], enabling
ms.assetid: 0f6448c9-944e-45f6-9436-87a4f3743498
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dfd87d300314616fe05a033360d84f5d2eb8b8cd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-enable-a-user-mapping"></a><span data-ttu-id="3f6e4-102">Cómo habilitar una asignación de usuario</span><span class="sxs-lookup"><span data-stu-id="3f6e4-102">How to Enable a User Mapping</span></span>
<span data-ttu-id="3f6e4-103">Es necesario habilitar una asignación de usuarios antes de que se pueda utilizar la asignación en el sistema de inicio de sesión único.</span><span class="sxs-lookup"><span data-stu-id="3f6e4-103">You must enable a user mapping before it you can use the mapping in the Single Sign-On system.</span></span>  
  
 <span data-ttu-id="3f6e4-104">Cuando se habilita una asignación de usuarios, aparecerá como (E)  **\<dominio\>\\< nombre de usuario\>**  al enumerar las asignaciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="3f6e4-104">When you enable a user mapping, it will appear as (E) **\<domain\>\\<username\>** when you list the user mappings.</span></span>  
  
 <span data-ttu-id="3f6e4-105">Tenga en cuenta que, si se han establecido credenciales utilizando el comando -setcredentials, la asignación ya se habrá habilitado.</span><span class="sxs-lookup"><span data-stu-id="3f6e4-105">Note that if you have set the credentials using the -setcredentials command, the mapping will already be enabled.</span></span>  
  
### <a name="to-enable-a-user-mapping-using-the-administration-utility"></a><span data-ttu-id="3f6e4-106">Para habilitar una asignación de usuarios con la utilidad de administración</span><span class="sxs-lookup"><span data-stu-id="3f6e4-106">To enable a user mapping using the administration utility</span></span>  
  
1.  <span data-ttu-id="3f6e4-107">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="3f6e4-107">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="3f6e4-108">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="3f6e4-108">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="3f6e4-109">El directorio de instalación predeterminado es  **\<unidad\>**: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="3f6e4-109">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="3f6e4-110">Tipo de **ssomanage-enablemapping \<dominio\>\\< nombre de usuario\>\<nombre de la aplicación\>**, donde  **\< dominio\>**  es el dominio de Windows para la cuenta de usuario  **\<nombre de usuario\>**  es el nombre de usuario de Windows para el que desea habilitar las credenciales y  **\<nombre de la aplicación\>**  es el nombre de la aplicación afiliada que desea quitar la asignación de usuario y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="3f6e4-110">Type **ssomanage –enablemapping \<domain\>\\<username\>\<application name\>**, where **\<domain\>** is the Windows domain for the user account, **\<username\>** is the Windows user name for which you want to enable the credentials, and **\<application name\>** is the name of the affiliate application you want to remove the user mapping for and then press ENTER.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3f6e4-111">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="3f6e4-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-enable-a-user-mapping-using-the-client-utility"></a><span data-ttu-id="3f6e4-112">Para habilitar una asignación de usuarios con la utilidad de cliente</span><span class="sxs-lookup"><span data-stu-id="3f6e4-112">To enable a user mapping using the client utility</span></span>  
  
1.  <span data-ttu-id="3f6e4-113">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="3f6e4-113">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="3f6e4-114">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="3f6e4-114">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="3f6e4-115">El directorio de instalación predeterminado es  **\<unidad\>**: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="3f6e4-115">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="3f6e4-116">Tipo de **ssoclient – enablemapping \<nombre de la aplicación\>**, donde  **\<nombre de la aplicación\>**  es el nombre de la aplicación afiliada que desee Para quitar la asignación de usuario.</span><span class="sxs-lookup"><span data-stu-id="3f6e4-116">Type **ssoclient –enablemapping \<application name\>**, where **\<application name\>** is the name of the affiliate application you want to remove the user mapping for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3f6e4-117">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="3f6e4-117">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f6e4-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f6e4-118">See Also</span></span>  
 <span data-ttu-id="3f6e4-119">[Cómo crear asignaciones de usuario](../core/how-to-create-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="3f6e4-119">[How to Create User Mappings](../core/how-to-create-user-mappings.md) </span></span>  
 <span data-ttu-id="3f6e4-120">[Asignaciones de SSO](../core/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="3f6e4-120">[SSO Mappings](../core/sso-mappings.md) </span></span>  
 <span data-ttu-id="3f6e4-121">[Administrar aplicaciones afiliadas](../core/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="3f6e4-121">[Managing Affiliate Applications](../core/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="3f6e4-122">Administración de asignaciones de usuarios</span><span class="sxs-lookup"><span data-stu-id="3f6e4-122">Managing User Mappings</span></span>](../core/managing-user-mappings.md)