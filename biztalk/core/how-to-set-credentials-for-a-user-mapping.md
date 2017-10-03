---
title: "Cómo establecer las credenciales para una asignación de usuario | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maps [SSO], credentials
- managing [SSO maps], configuring credentials
ms.assetid: 75b29114-56b6-4db0-8666-61cf6c675401
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc5947b13d9ffcc3721f460ccbcd5bd25701be07
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-credentials-for-a-user-mapping"></a><span data-ttu-id="d69e4-102">Cómo establecer las credenciales para una asignación de usuario</span><span class="sxs-lookup"><span data-stu-id="d69e4-102">How to Set Credentials for a User Mapping</span></span>
<span data-ttu-id="d69e4-103">Utilice este comando para establecer credenciales para que un usuario tenga acceso a una aplicación específica.</span><span class="sxs-lookup"><span data-stu-id="d69e4-103">Use this command to set the credentials for a user to access a specific application.</span></span>  
  
 <span data-ttu-id="d69e4-104">Este comando no muestra la contraseña conforme la escribe.</span><span class="sxs-lookup"><span data-stu-id="d69e4-104">This command does not display the password as you type it.</span></span>  
  
 <span data-ttu-id="d69e4-105">Si la asignación de usuario existe ya, este comando establece las credenciales para esa asignación.</span><span class="sxs-lookup"><span data-stu-id="d69e4-105">If the user mapping already exists, this command sets the credentials for that existing mapping.</span></span> <span data-ttu-id="d69e4-106">Si no ha creado la asignación de usuario, el sistema SSO le preguntará el Id. de usuario para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d69e4-106">If you have not created the user mapping, the SSO system will prompt you for the user ID for the application.</span></span>  
  
### <a name="to-set-credentials-for-a-user-mapping"></a><span data-ttu-id="d69e4-107">Para establecer credenciales para una asignación de usuario</span><span class="sxs-lookup"><span data-stu-id="d69e4-107">To set credentials for a user mapping</span></span>  
  
1.  <span data-ttu-id="d69e4-108">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="d69e4-108">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="d69e4-109">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="d69e4-109">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="d69e4-110">El directorio de instalación predeterminado es  **\<unidad >**: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="d69e4-110">The default installation directory is **\<drive>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="d69e4-111">Tipo de **ssomanage – setcredentials \<dominio >\\< nombre de usuario\> \<applicationname >**, donde  **\<dominio >** es el dominio de Windows para la cuenta de usuario  **\<nombre de usuario >** es el nombre de usuario de Windows, y  **\<applicationname >** es la aplicación específica para el que desea establecer las credenciales.</span><span class="sxs-lookup"><span data-stu-id="d69e4-111">Type **ssomanage –setcredentials \<domain>\\<username\> \<applicationname>**, where **\<domain>** is the Windows domain for the user account, **\<username>** is the Windows user name, and **\<applicationname>** is the specific application for which you want to set the credentials for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d69e4-112">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="d69e4-112">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="d69e4-113">Cuando el sistema SSO le pida las credenciales de usuario, escriba la contraseña de usuario para esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="d69e4-113">When the SSO system prompts you for the user credentials, enter the user password for this application.</span></span>  
  
5.  <span data-ttu-id="d69e4-114">Si no ha creado la asignación de usuario, el sistema SSO le preguntará el Id. de usuario para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d69e4-114">If you have not created the user mapping, the SSO system will prompt you for the user ID for the application.</span></span>  
  
### <a name="to-set-credentials-for-a-user-mapping-from-the-client-utility"></a><span data-ttu-id="d69e4-115">Para establecer credenciales para una asignación de usuario desde la utilidad de cliente</span><span class="sxs-lookup"><span data-stu-id="d69e4-115">To set credentials for a user mapping from the client utility</span></span>  
  
1.  <span data-ttu-id="d69e4-116">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="d69e4-116">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="d69e4-117">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="d69e4-117">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="d69e4-118">El directorio de instalación predeterminado es  **\<unidad >**: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="d69e4-118">The default installation directory is **\<drive>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="d69e4-119">Tipo de **ssoclient - setcredentials \<nombre de aplicación >**, donde  **\<nombre de aplicación >** es el nombre de la aplicación afiliada que desea quitar la asignación de usuario .</span><span class="sxs-lookup"><span data-stu-id="d69e4-119">Type **ssoclient -setcredentials \<application name>**, where **\<application name>** is the name of the affiliate application you want to remove the user mapping for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d69e4-120">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="d69e4-120">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d69e4-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="d69e4-121">See Also</span></span>  
 <span data-ttu-id="d69e4-122">[Cómo crear asignaciones de usuario](../core/how-to-create-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="d69e4-122">[How to Create User Mappings](../core/how-to-create-user-mappings.md) </span></span>  
 <span data-ttu-id="d69e4-123">[Asignaciones de SSO](../core/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="d69e4-123">[SSO Mappings](../core/sso-mappings.md) </span></span>  
 <span data-ttu-id="d69e4-124">[Administrar aplicaciones afiliadas](../core/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="d69e4-124">[Managing Affiliate Applications](../core/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="d69e4-125">Administrar asignaciones de usuario</span><span class="sxs-lookup"><span data-stu-id="d69e4-125">Managing User Mappings</span></span>](../core/managing-user-mappings.md)