---
title: Grupos de dominio | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9adc090e-e18c-46b6-b985-49b200d42966
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2944ce83df75ed724c9a7acafeee119b40cacafb
ms.sourcegitcommit: 7b64c823fa8d7fa8b10b163613311be69b861017
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2018
ms.locfileid: "39625872"
---
# <a name="domain-groups-in-biztalk"></a><span data-ttu-id="68797-102">Grupos de dominio de BizTalk</span><span class="sxs-lookup"><span data-stu-id="68797-102">Domain Groups in BizTalk</span></span>
<span data-ttu-id="68797-103">BizTalk Server admite cuentas de grupo de dominio y de usuario en configuraciones de uno y de varios equipos.</span><span class="sxs-lookup"><span data-stu-id="68797-103">BizTalk Server supports domain group and user accounts in both single and multiple computer configurations.</span></span> <span data-ttu-id="68797-104">Para configuraciones de varios equipos, debe observar los requisitos mencionados en esta sección y en el apartado Consideraciones para crear un entorno multiservidor de la Guía de instalación.</span><span class="sxs-lookup"><span data-stu-id="68797-104">For multiple computer configurations, you must observe the requirements provided in this section and in the Considerations for Multiserver Environments in the Installation Guide.</span></span> <span data-ttu-id="68797-105">Para obtener más información, consulte el [Introducción a la instalación](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="68797-105">For more information, see the [installation overview](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="68797-106">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="68797-106">Before you begin</span></span>
-   <span data-ttu-id="68797-107">Si utiliza grupos de dominio para la configuración de BizTalk Server, debe crear los grupos manualmente antes de configurar BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="68797-107">If you use domain groups for your BizTalk Server configuration, you must manually create the groups before you configure BizTalk Server.</span></span> <span data-ttu-id="68797-108">El Administrador de configuración no puede crear grupos de dominio.</span><span class="sxs-lookup"><span data-stu-id="68797-108">The Configuration Manager cannot create domain groups.</span></span>  
  
-   <span data-ttu-id="68797-109">Después de crear grupos de dominio o cuentas de usuario, agregue las cuentas de usuario a los grupos adecuados según las afiliaciones de grupo en [grupos de Windows y cuentas de usuario en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="68797-109">After creating domain groups and/or user accounts, add user accounts to the proper groups according to the group affiliations in [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="68797-110">Use **\<DomainName\>\\< nombre de usuario\>** al especificar la información de cuenta de dominio en el Administrador de configuración.</span><span class="sxs-lookup"><span data-stu-id="68797-110">Use **\<DomainName\>\\<UserName\>** when specifying domain account information in the Configuration Manager.</span></span>  
  
-   <span data-ttu-id="68797-111">BizTalk Server necesita cuentas de dominio en todos los escenarios de clúster.</span><span class="sxs-lookup"><span data-stu-id="68797-111">BizTalk Server requires domain accounts for all clustering scenarios.</span></span> <span data-ttu-id="68797-112">No puede utilizar cuentas locales con un servidor SQL Server o un servidor de SSO (servidor secreto principal) agrupados.</span><span class="sxs-lookup"><span data-stu-id="68797-112">You cannot use local accounts with clustered SQL Server or clustered SSO Server (master secret server).</span></span>  
  
-   <span data-ttu-id="68797-113">El Administrador de instalación y configuración de BizTalk Server debe ser miembro de los siguientes grupos: los administradores de SSO (sólo al configurar el servidor secreto principal); Administradores locales; rol de SQL Server sysadmin; Administradores de OLAP.</span><span class="sxs-lookup"><span data-stu-id="68797-113">The administrator installing and configuring BizTalk Server must be a member of the following groups: SSO Administrators (only when configuring the master secret server); local Administrators; sysadmin SQL Server role; OLAP Administrators.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="68797-114">Puede crear el grupo de dominio automáticamente si especifica un grupo de dominio durante la configuración de los grupos de administradores de SSO y de administradores de aplicaciones afiliadas de SSO y tiene los privilegios suficientes para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="68797-114">You can create the domain group automatically if you specify a domain group during configuration for the SSO Administrators and SSO Affiliate Administrators, and you have sufficient privileges.</span></span> <span data-ttu-id="68797-115">Si no tiene privilegios suficientes, asegúrese de que esos grupos ya existen.</span><span class="sxs-lookup"><span data-stu-id="68797-115">If you do not have sufficient privileges, ensure that these groups already exist.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68797-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="68797-116">See Also</span></span>  
 <span data-ttu-id="68797-117">[Grupos locales](../core/local-groups.md) </span><span class="sxs-lookup"><span data-stu-id="68797-117">[Local Groups](../core/local-groups.md) </span></span>  
 <span data-ttu-id="68797-118">[Introducción a la instalación](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md) </span><span class="sxs-lookup"><span data-stu-id="68797-118">[Installation Overview](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md) </span></span>  
 [<span data-ttu-id="68797-119">Cuentas de grupos y de usuario de Windows en BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="68797-119">Windows Groups and User Accounts in BizTalk Server</span></span>](../core/windows-groups-and-user-accounts-in-biztalk-server.md)
