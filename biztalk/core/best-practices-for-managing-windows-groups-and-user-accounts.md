---
title: Procedimientos recomendados para administrar las cuentas de usuario y grupos de Windows | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- best practices, Windows groups
- authenticating, best practices
- Windows groups, security
- best practices, user accounts
- best practices, security
- security, best practices
- user accounts, security
- authenticating, security
- Windows groups, best practices
- best practices, authenticating
- user accounts, best practices
- hosts, security
- hosts, best practices
- best practices, hosts
ms.assetid: 0c4a141e-97ce-434a-8e45-a56c634bbd6c
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 71f7560e3867bf290f20e0f2f49a740d7298131b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-for-managing-windows-groups-and-user-accounts"></a><span data-ttu-id="aa6e8-102">Prácticas recomendadas para administrar grupos de Windows y cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="aa6e8-102">Best Practices for Managing Windows Groups and User Accounts</span></span>
<span data-ttu-id="aa6e8-103">En esta sección, se detallan prácticas recomendadas y sugerencias para administrar la seguridad de grupos de Windows y de cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="aa6e8-103">This section contains best practices and tips for managing security for Windows groups and user accounts.</span></span>  
  
-   <span data-ttu-id="aa6e8-104">**Utilice las cuentas de servicio con privilegios mínimos necesarios para las instancias de host**</span><span class="sxs-lookup"><span data-stu-id="aa6e8-104">**Use service accounts with minimum privileges necessary for host instances**</span></span>  
  
     <span data-ttu-id="aa6e8-105">Para garantizar la seguridad del entorno de BizTalk Server, se recomienda utilizar cuentas de servicio con los privilegios mínimos necesarios para ejecutar instancias de host.</span><span class="sxs-lookup"><span data-stu-id="aa6e8-105">To help ensure the security of your BizTalk Server environment, we recommend that you use service accounts with the minimum privileges necessary to run host instances.</span></span> <span data-ttu-id="aa6e8-106">Para obtener más información acerca de los privilegios mínimos requeridos por las cuentas de servicio, consulte [Control de acceso y seguridad de los datos](../core/access-control-and-data-security.md).</span><span class="sxs-lookup"><span data-stu-id="aa6e8-106">For more information about the minimum privileges that service accounts require, see [Access Control and Data Security](../core/access-control-and-data-security.md).</span></span>  
  
-   <span data-ttu-id="aa6e8-107">**Use grupos de usuarios diferentes para la autenticación de confianza y hosts que no son de confianza**</span><span class="sxs-lookup"><span data-stu-id="aa6e8-107">**Use different user groups for authentication trusted and non-trusted hosts**</span></span>  
  
     <span data-ttu-id="aa6e8-108">Para garantizar que los hosts con autenticación que no es de confianza tengan menos privilegios que los hosts con autenticación de confianza, se deben utilizar cuentas de servicio distintas para cada host.</span><span class="sxs-lookup"><span data-stu-id="aa6e8-108">To ensure that non-authentication trusted hosts have fewer privileges than authentication trusted hosts, you must use different service accounts for each host.</span></span>  
  
-   <span data-ttu-id="aa6e8-109">**Usar un grupo de usuario diferente para cada Host de BizTalk**</span><span class="sxs-lookup"><span data-stu-id="aa6e8-109">**Use a different user group for each BizTalk Host**</span></span>  
  
     <span data-ttu-id="aa6e8-110">Para maximizar el límite de seguridad entre hosts, se recomienda utilizar un grupo de usuarios de Windows diferente para cada uno de los hosts de BizTalk del grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="aa6e8-110">To maximize the security boundary between hosts, we recommend that you use a different Windows user group for each BizTalk Host in your BizTalk group.</span></span>  
  
-   <span data-ttu-id="aa6e8-111">**Quite el usuario de instalación desde el grupo de administradores de BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="aa6e8-111">**Remove the installation user from the BizTalk Server Administrators group**</span></span>  
  
     <span data-ttu-id="aa6e8-112">Al instalar BizTalk Server en un equipo único con grupos locales, el usuario que lleva a cabo una instalación interactiva de BizTalk Server se agrega automáticamente al grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="aa6e8-112">When you install BizTalk Server on a single computer with local groups, the user performing an interactive installation of BizTalk Server is automatically added to the BizTalk Server Administrators group.</span></span> <span data-ttu-id="aa6e8-113">Con ello, se permite al usuario configurar BizTalk Server con el administrador de configuración.</span><span class="sxs-lookup"><span data-stu-id="aa6e8-113">This allows that user to configure BizTalk Server with the Configuration Manager.</span></span>  
  
     <span data-ttu-id="aa6e8-114">Si el usuario que instala BizTalk Server no va a encargarse de su administración, se recomienda quitar a este usuario del grupo de administradores de BizTalk Server una vez configurada la aplicación.</span><span class="sxs-lookup"><span data-stu-id="aa6e8-114">If the user who installs BizTalk Server will not be administering BizTalk Server, we recommend that you remove this user from the BizTalk Server Administrators group after BizTalk Server is configured.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa6e8-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa6e8-115">See Also</span></span>  
 [<span data-ttu-id="aa6e8-116">Administrar la seguridad de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="aa6e8-116">Managing BizTalk Server Security</span></span>](../core/managing-biztalk-server-security.md)