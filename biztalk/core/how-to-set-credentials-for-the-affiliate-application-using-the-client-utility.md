---
title: "Cómo establecer las credenciales para la aplicación afiliada con la utilidad de cliente | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [SSO applications], configuring credentials
- SSOClient [SSO], configuring credentials
- applications [SSO], credentials
ms.assetid: 454b6257-3538-40be-840c-00172a2c1dce
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31ba167bc35d01907166bb6610720e03be654c4d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-credentials-for-the-affiliate-application-using-the-client-utility"></a><span data-ttu-id="d2ba7-102">Cómo establecer las credenciales para la aplicación afiliada con la utilidad de cliente</span><span class="sxs-lookup"><span data-stu-id="d2ba7-102">How to Set Credentials for the Affiliate Application Using the Client Utility</span></span>
<span data-ttu-id="d2ba7-103">Utilice este comando para establecer las credenciales para un usuario para que éste tenga acceso a una aplicación específica.</span><span class="sxs-lookup"><span data-stu-id="d2ba7-103">Use this command to set the credentials for a user so that the user is able to access a specific application.</span></span> <span data-ttu-id="d2ba7-104">Este comando también habilita automáticamente la asignación.</span><span class="sxs-lookup"><span data-stu-id="d2ba7-104">This command also automatically enables the mapping.</span></span>  
  
 <span data-ttu-id="d2ba7-105">Este comando no muestra la contraseña conforme la escribe.</span><span class="sxs-lookup"><span data-stu-id="d2ba7-105">This command does not display the password as you type it.</span></span>  
  
 <span data-ttu-id="d2ba7-106">Si ya existe la asignación de usuario, este comando establecerá las credenciales para la asignación existente.</span><span class="sxs-lookup"><span data-stu-id="d2ba7-106">If the user mapping already exists, this command will set the credentials for that existing mapping.</span></span> <span data-ttu-id="d2ba7-107">Si no ha creado la asignación de usuario, el sistema SSO le preguntará el Id. de usuario para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d2ba7-107">If you have not created the user mapping, the SSO system will prompt you for the user ID for the application.</span></span>  
  
### <a name="to-set-credentials-for-the-affiliate-application-using-the-client-utility"></a><span data-ttu-id="d2ba7-108">Para establecer las credenciales de la aplicación afiliada con la utilidad de cliente</span><span class="sxs-lookup"><span data-stu-id="d2ba7-108">To set credentials for the affiliate application using the client utility</span></span>  
  
1.  <span data-ttu-id="d2ba7-109">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="d2ba7-109">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="d2ba7-110">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="d2ba7-110">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="d2ba7-111">El directorio de instalación predeterminado es  *\<unidad >*: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="d2ba7-111">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="d2ba7-112">Tipo de **ssoclient – setcredentials \<nombre de aplicación >**, donde  **\<nombre de aplicación >** es la aplicación específica para el que desea establecer las credenciales.</span><span class="sxs-lookup"><span data-stu-id="d2ba7-112">Type **ssoclient –setcredentials \<application name>**, where **\<application name>** is the specific application for which you want to set the credentials for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d2ba7-113">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="d2ba7-113">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="d2ba7-114">Cuando se solicitan las credenciales de usuario, escriba la contraseña de usuario para esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="d2ba7-114">When prompted for the user credentials, enter the user password for this application.</span></span>  
  
5.  <span data-ttu-id="d2ba7-115">Si no ha creado la asignación de usuario, el sistema SSO le preguntará el Id. de usuario para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d2ba7-115">If you have not created the user mapping, the SSO system will prompt you for the user ID for the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2ba7-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2ba7-116">See Also</span></span>  
 <span data-ttu-id="d2ba7-117">[Aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="d2ba7-117">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="d2ba7-118">Administrar aplicaciones afiliadas</span><span class="sxs-lookup"><span data-stu-id="d2ba7-118">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)