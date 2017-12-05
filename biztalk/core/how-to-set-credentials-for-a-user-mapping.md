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
ms.openlocfilehash: c4853499dbfd85cd5114212e37f4d22770d64a22
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-set-credentials-for-a-user-mapping"></a><span data-ttu-id="7361c-102">Cómo establecer las credenciales para una asignación de usuario</span><span class="sxs-lookup"><span data-stu-id="7361c-102">How to Set Credentials for a User Mapping</span></span>
<span data-ttu-id="7361c-103">Utilice este comando para establecer credenciales para que un usuario tenga acceso a una aplicación específica.</span><span class="sxs-lookup"><span data-stu-id="7361c-103">Use this command to set the credentials for a user to access a specific application.</span></span>  
  
 <span data-ttu-id="7361c-104">Este comando no muestra la contraseña conforme la escribe.</span><span class="sxs-lookup"><span data-stu-id="7361c-104">This command does not display the password as you type it.</span></span>  
  
 <span data-ttu-id="7361c-105">Si la asignación de usuario existe ya, este comando establece las credenciales para esa asignación.</span><span class="sxs-lookup"><span data-stu-id="7361c-105">If the user mapping already exists, this command sets the credentials for that existing mapping.</span></span> <span data-ttu-id="7361c-106">Si no ha creado la asignación de usuario, el sistema SSO le preguntará el Id. de usuario para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7361c-106">If you have not created the user mapping, the SSO system will prompt you for the user ID for the application.</span></span>  
  
### <a name="to-set-credentials-for-a-user-mapping"></a><span data-ttu-id="7361c-107">Para establecer credenciales para una asignación de usuario</span><span class="sxs-lookup"><span data-stu-id="7361c-107">To set credentials for a user mapping</span></span>  
  
1.  <span data-ttu-id="7361c-108">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="7361c-108">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="7361c-109">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="7361c-109">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="7361c-110">El directorio de instalación predeterminado es  **\<unidad\>**: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="7361c-110">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="7361c-111">Tipo de **ssomanage – setcredentials \<dominio\>\\< nombre de usuario\> \<applicationname\>**, donde  **\< dominio\>**  es el dominio de Windows para la cuenta de usuario  **\<nombre de usuario\>**  es el nombre de usuario de Windows, y  **\<applicationname \>**  es la aplicación específica para el que desea establecer las credenciales.</span><span class="sxs-lookup"><span data-stu-id="7361c-111">Type **ssomanage –setcredentials \<domain\>\\<username\> \<applicationname\>**, where **\<domain\>** is the Windows domain for the user account, **\<username\>** is the Windows user name, and **\<applicationname\>** is the specific application for which you want to set the credentials for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7361c-112">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="7361c-112">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="7361c-113">Cuando el sistema SSO le pida las credenciales de usuario, escriba la contraseña de usuario para esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="7361c-113">When the SSO system prompts you for the user credentials, enter the user password for this application.</span></span>  
  
5.  <span data-ttu-id="7361c-114">Si no ha creado la asignación de usuario, el sistema SSO le preguntará el Id. de usuario para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7361c-114">If you have not created the user mapping, the SSO system will prompt you for the user ID for the application.</span></span>  
  
### <a name="to-set-credentials-for-a-user-mapping-from-the-client-utility"></a><span data-ttu-id="7361c-115">Para establecer credenciales para una asignación de usuario desde la utilidad de cliente</span><span class="sxs-lookup"><span data-stu-id="7361c-115">To set credentials for a user mapping from the client utility</span></span>  
  
1.  <span data-ttu-id="7361c-116">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="7361c-116">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="7361c-117">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="7361c-117">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="7361c-118">El directorio de instalación predeterminado es  **\<unidad\>**: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="7361c-118">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="7361c-119">Tipo de **ssoclient - setcredentials \<nombre de la aplicación\>**, donde  **\<nombre de la aplicación\>**  es el nombre de la aplicación afiliada ¿desea quitar la asignación de usuario.</span><span class="sxs-lookup"><span data-stu-id="7361c-119">Type **ssoclient -setcredentials \<application name\>**, where **\<application name\>** is the name of the affiliate application you want to remove the user mapping for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7361c-120">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="7361c-120">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7361c-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="7361c-121">See Also</span></span>  
 <span data-ttu-id="7361c-122">[Cómo crear asignaciones de usuario](../core/how-to-create-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="7361c-122">[How to Create User Mappings](../core/how-to-create-user-mappings.md) </span></span>  
 <span data-ttu-id="7361c-123">[Asignaciones de SSO](../core/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="7361c-123">[SSO Mappings](../core/sso-mappings.md) </span></span>  
 <span data-ttu-id="7361c-124">[Administrar aplicaciones afiliadas](../core/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="7361c-124">[Managing Affiliate Applications](../core/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="7361c-125">Administración de asignaciones de usuarios</span><span class="sxs-lookup"><span data-stu-id="7361c-125">Managing User Mappings</span></span>](../core/managing-user-mappings.md)