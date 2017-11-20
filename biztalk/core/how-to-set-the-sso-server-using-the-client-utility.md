---
title: "Cómo establecer el servidor SSO con la utilidad de cliente | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications [SSO], selecting servers
- managing [SSO applications], selecting servers
- SSOClient [SSO], selecting servers
ms.assetid: a0f1038c-60c9-4e9d-a730-1ecfa036743b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d917114d21ceed37eb68ee4bb9503aac97735ffa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-the-sso-server-using-the-client-utility"></a><span data-ttu-id="c7873-102">Cómo establecer el servidor SSO con la utilidad de cliente</span><span class="sxs-lookup"><span data-stu-id="c7873-102">How to Set the SSO Server Using the Client Utility</span></span>
<span data-ttu-id="c7873-103">Cada vez que utilice el cliente de SSO, en primer lugar debe seleccionar al usuario para el servidor de inicio de sesión único adecuado que contenga la información de configuración.</span><span class="sxs-lookup"><span data-stu-id="c7873-103">Each time you use ssoclient, you must first point the user to the correct Single Sign-On server that contains their configuration information.</span></span>  
  
### <a name="to-set-the-sso-server-for-a-user-using-the-client-utility"></a><span data-ttu-id="c7873-104">Para establecer el servidor de SSO para un usuario con la utilidad de cliente</span><span class="sxs-lookup"><span data-stu-id="c7873-104">To set the SSO Server for a user using the client utility</span></span>  
  
1.  <span data-ttu-id="c7873-105">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="c7873-105">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="c7873-106">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="c7873-106">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="c7873-107">El directorio de instalación predeterminado es  *\<unidad >*: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="c7873-107">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="c7873-108">Tipo de **ssoclient – server  *\<Single Sign-On Server >***, donde \< *Single Sign-On Server >* es el nombre de la Single Sign-On el usuario de servidor que va a conectar.</span><span class="sxs-lookup"><span data-stu-id="c7873-108">Type **ssoclient –server *\<Single Sign-On Server>***, where \<*Single Sign-On Server>* is the name of the Single Sign-On server the user wants to connect to.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c7873-109">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="c7873-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7873-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7873-110">See Also</span></span>  
 <span data-ttu-id="c7873-111">[Aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="c7873-111">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="c7873-112">Administrar aplicaciones afiliadas</span><span class="sxs-lookup"><span data-stu-id="c7873-112">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)