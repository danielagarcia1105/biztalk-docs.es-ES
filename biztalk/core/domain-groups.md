---
title: Grupos de dominio | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: domain groups
ms.assetid: 9adc090e-e18c-46b6-b985-49b200d42966
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52fc5cc05718aa6d9e0ca89bc48467052fb916a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="domain-groups"></a><span data-ttu-id="ec054-102">Grupos de dominio</span><span class="sxs-lookup"><span data-stu-id="ec054-102">Domain Groups</span></span>
<span data-ttu-id="ec054-103">BizTalk Server admite cuentas de grupo de dominio y de usuario en configuraciones de uno y de varios equipos.</span><span class="sxs-lookup"><span data-stu-id="ec054-103">BizTalk Server supports domain group and user accounts in both single and multiple computer configurations.</span></span> <span data-ttu-id="ec054-104">Para configuraciones de varios equipos, debe observar los requisitos mencionados en esta sección y en el apartado Consideraciones para crear un entorno multiservidor de la Guía de instalación.</span><span class="sxs-lookup"><span data-stu-id="ec054-104">For multiple computer configurations, you must observe the requirements provided in this section and in the Considerations for Multiserver Environments in the Installation Guide.</span></span> <span data-ttu-id="ec054-105">Para obtener más información, consulte [Introducción a la instalación de BizTalk Server 2013 y 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5).</span><span class="sxs-lookup"><span data-stu-id="ec054-105">For more information, see [Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5).</span></span>  
  
-   <span data-ttu-id="ec054-106">Si utiliza grupos de dominio para la configuración de BizTalk Server, debe crear los grupos manualmente antes de configurar BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="ec054-106">If you use domain groups for your BizTalk Server configuration, you must manually create the groups before you configure BizTalk Server.</span></span> <span data-ttu-id="ec054-107">El Administrador de configuración no puede crear grupos de dominio.</span><span class="sxs-lookup"><span data-stu-id="ec054-107">The Configuration Manager cannot create domain groups.</span></span>  
  
-   <span data-ttu-id="ec054-108">Después de crear grupos de dominio o cuentas de usuario, agregar cuentas de usuario a los grupos adecuados según las afiliaciones de grupo en [grupos de Windows y cuentas de usuario en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="ec054-108">After creating domain groups and/or user accounts, add user accounts to the proper groups according to the group affiliations in [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="ec054-109">Use  **\<DomainName >\\< nombre de usuario\>**  al especificar la información de cuenta de dominio en el Administrador de configuración.</span><span class="sxs-lookup"><span data-stu-id="ec054-109">Use **\<DomainName>\\<UserName\>** when specifying domain account information in the Configuration Manager.</span></span>  
  
-   <span data-ttu-id="ec054-110">BizTalk Server necesita cuentas de dominio en todos los escenarios de clúster.</span><span class="sxs-lookup"><span data-stu-id="ec054-110">BizTalk Server requires domain accounts for all clustering scenarios.</span></span> <span data-ttu-id="ec054-111">No puede utilizar cuentas locales con un servidor SQL Server o un servidor de SSO (servidor secreto principal) agrupados.</span><span class="sxs-lookup"><span data-stu-id="ec054-111">You cannot use local accounts with clustered SQL Server or clustered SSO Server (master secret server).</span></span>  
  
-   <span data-ttu-id="ec054-112">El Administrador de instalación y configuración de BizTalk Server debe ser miembro de los siguientes grupos: los administradores de SSO (sólo al configurar el servidor secreto principal); Administradores locales; función de SQL Server sysadmin; Administradores OLAP.</span><span class="sxs-lookup"><span data-stu-id="ec054-112">The administrator installing and configuring BizTalk Server must be a member of the following groups: SSO Administrators (only when configuring the master secret server); local Administrators; sysadmin SQL Server role; OLAP Administrators.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec054-113">Puede crear el grupo de dominio automáticamente si especifica un grupo de dominio durante la configuración de los grupos de administradores de SSO y de administradores de aplicaciones afiliadas de SSO y tiene los privilegios suficientes para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="ec054-113">You can create the domain group automatically if you specify a domain group during configuration for the SSO Administrators and SSO Affiliate Administrators, and you have sufficient privileges.</span></span> <span data-ttu-id="ec054-114">Si no tiene privilegios suficientes, asegúrese de que esos grupos ya existen.</span><span class="sxs-lookup"><span data-stu-id="ec054-114">If you do not have sufficient privileges, ensure that these groups already exist.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec054-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec054-115">See Also</span></span>  
 <span data-ttu-id="ec054-116">[Grupos locales](../core/local-groups.md) </span><span class="sxs-lookup"><span data-stu-id="ec054-116">[Local Groups](../core/local-groups.md) </span></span>  
 <span data-ttu-id="ec054-117">[Información general sobre la instalación de BizTalk Server 2013 y 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5) </span><span class="sxs-lookup"><span data-stu-id="ec054-117">[Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5) </span></span>  
 [<span data-ttu-id="ec054-118">Cuentas de grupos y de usuario de Windows en BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ec054-118">Windows Groups and User Accounts in BizTalk Server</span></span>](../core/windows-groups-and-user-accounts-in-biztalk-server.md)