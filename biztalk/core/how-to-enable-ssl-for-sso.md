---
title: "Cómo habilitar SSL para SSO | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO, SSL
- managing [SSO], enabling SSL
- SSL
ms.assetid: 0d75962a-a0b0-4e69-8001-54e7df617006
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ae2f3840cd2620f9c03a5b207b32d8bbd4feee9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-enable-ssl-for-sso"></a><span data-ttu-id="678ea-102">Cómo habilitar SSL para SSO</span><span class="sxs-lookup"><span data-stu-id="678ea-102">How to Enable SSL for SSO</span></span>
<span data-ttu-id="678ea-103">Este comando se utiliza para habilitar Capa de sockets seguros (SSL) entre todos los servidores de inicio de sesión único (SSO) empresarial y la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="678ea-103">Use this command to enable Secure Sockets Layer (SSL) between all the Enterprise Single Sign-On (SSO) servers and the SSO database.</span></span>  
  
### <a name="to-enable-ssl-for-enterprise-single-sign-on"></a><span data-ttu-id="678ea-104">Para habilitar SSL para el inicio de sesión único empresarial</span><span class="sxs-lookup"><span data-stu-id="678ea-104">To enable SSL for Enterprise Single Sign-On</span></span>  
  
1.  <span data-ttu-id="678ea-105">Haga clic en **iniciar**, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="678ea-105">Click **Start**, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="678ea-106">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="678ea-106">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="678ea-107">El directorio de instalación predeterminado es  **\<unidad >**: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="678ea-107">The default installation directory is **\<drive>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="678ea-108">Tipo de **ssoconfig – setSSL \<sí/no >**, donde \< **sí/no**> indica si desea habilitar SSL en el sistema SSO.</span><span class="sxs-lookup"><span data-stu-id="678ea-108">Type **ssoconfig –setSSL \<yes/no>**, where \<**yes/no**> indicates whether you want to enable SSL in the SSO system.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="678ea-109">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="678ea-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="678ea-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="678ea-110">See Also</span></span>  
 [<span data-ttu-id="678ea-111">Uso de SSO</span><span class="sxs-lookup"><span data-stu-id="678ea-111">Using SSO</span></span>](../core/using-sso.md)