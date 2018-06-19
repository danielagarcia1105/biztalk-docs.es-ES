---
title: Cómo crear servicio cuentas para nuevos Hosts e instancias de Host | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Configuration Manager, service accounts
- Windows groups, service accounts
- Configuration Manager
- service accounts, Windows groups
- hosts, service accounts
- service accounts, hosts
- service accounts, Configuration Manager
- service accounts, creating
- creating, service accounts
ms.assetid: cef97f4a-8db1-41b6-9614-608c2fbf59a9
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d4887d78466340b12b95ed43d27523955ab0689
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969379"
---
# <a name="how-to-create-service-accounts-for-new-hosts-and-host-instances"></a><span data-ttu-id="d3a7f-102">Cómo crear cuentas de servicio para nuevos hosts y nuevas instancias de host</span><span class="sxs-lookup"><span data-stu-id="d3a7f-102">How to Create Service Accounts for New Hosts and Host Instances</span></span>
<span data-ttu-id="d3a7f-103">El administrador de configuración configura los grupos de Windows y las cuentas de usuario necesarios al instalar y configurar BizTalk Server en un único equipo.</span><span class="sxs-lookup"><span data-stu-id="d3a7f-103">The Configuration Manager configures the necessary Windows groups and user accounts when you install and configure BizTalk Server on a single computer.</span></span>  
  
 <span data-ttu-id="d3a7f-104">Es necesario crear manualmente cuentas de usuario y grupos de Windows, y agregar aquéllas a éstas en un entorno de dominio antes de ejecutar al administrador de configuración.</span><span class="sxs-lookup"><span data-stu-id="d3a7f-104">You must manually create Windows groups and user accounts, and add the user accounts to the Windows groups in a domain environment before running the Configuration Manager.</span></span> <span data-ttu-id="d3a7f-105">Para obtener más información, consulte [grupos de dominio](../core/domain-groups.md).</span><span class="sxs-lookup"><span data-stu-id="d3a7f-105">For more information, see [Domain Groups](../core/domain-groups.md).</span></span>  
  
 <span data-ttu-id="d3a7f-106">Debe realizar el siguiente procedimiento antes de crear un nuevo host o una nueva instancia de host.</span><span class="sxs-lookup"><span data-stu-id="d3a7f-106">You must perform the following procedure before creating a new host or host instance.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d3a7f-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d3a7f-107">Prerequisites</span></span>  
 <span data-ttu-id="d3a7f-108">Para llevar a cabo este procedimiento, debe haber iniciado sesión como miembro del grupo de administradores de dominio o del grupo de administradores.</span><span class="sxs-lookup"><span data-stu-id="d3a7f-108">You must be logged on as a member of Administrators or Domain Admins group to perform this procedure.</span></span>  
  
### <a name="to-create-service-accounts-for-new-hosts-or-host-instances"></a><span data-ttu-id="d3a7f-109">Para crear cuentas de servicio para nuevos hosts y nuevas instancias de host</span><span class="sxs-lookup"><span data-stu-id="d3a7f-109">To create service accounts for new hosts or host instances</span></span>  
  
1.  <span data-ttu-id="d3a7f-110">Cree un grupo de Windows de host para el nuevo host que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="d3a7f-110">Create a host Windows group for the new host that you will create.</span></span> <span data-ttu-id="d3a7f-111">Para obtener más información acerca de cómo crear un nuevo host, consulte [cómo crear un nuevo Host](../core/how-to-create-a-new-host.md).</span><span class="sxs-lookup"><span data-stu-id="d3a7f-111">For more information about creating a new host, see [How to Create a New Host](../core/how-to-create-a-new-host.md).</span></span>  
  
2.  <span data-ttu-id="d3a7f-112">Cree cuentas de servicio para cada una de las instancias de host que se van a agregar al nuevo host.</span><span class="sxs-lookup"><span data-stu-id="d3a7f-112">Create service accounts for each host instance that will be added to the new host.</span></span> <span data-ttu-id="d3a7f-113">Para obtener más información acerca de cómo crear una nueva instancia de host, consulte [cómo agregar una instancia de Host](../core/how-to-add-a-host-instance.md).</span><span class="sxs-lookup"><span data-stu-id="d3a7f-113">For more information about creating a new host instance, see [How to Add a Host Instance](../core/how-to-add-a-host-instance.md).</span></span>  
  
3.  <span data-ttu-id="d3a7f-114">Agregue cuentas de servicio al grupo de Windows de host según resulte necesario.</span><span class="sxs-lookup"><span data-stu-id="d3a7f-114">Add the service accounts to the host Windows group as needed.</span></span> <span data-ttu-id="d3a7f-115">Para obtener información acerca de los grupos de Windows a la que debe agregar la cuenta de servicio, consulte [grupos de Windows y cuentas de usuario en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="d3a7f-115">For information about the Windows groups to which you must add the service account, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
4.  <span data-ttu-id="d3a7f-116">Utilice el grupo de Windows y la cuenta de servicio al crear el host y la instancia de host.</span><span class="sxs-lookup"><span data-stu-id="d3a7f-116">Use the Windows group and service account when creating the host and host instances.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d3a7f-117">No se especifica \< *nombre_equipo*\>\ como el prefijo en el programa de instalación de un único equipo con los grupos locales.</span><span class="sxs-lookup"><span data-stu-id="d3a7f-117">Do not specify \<*computer name*\>\ as the prefix in a single computer setup with local groups.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d3a7f-118">Si se utiliza un grupo de dominio, debe especificar \< *nombre NetBIOS del dominio*\>\ como el prefijo para el nombre de grupo de Windows de host.</span><span class="sxs-lookup"><span data-stu-id="d3a7f-118">If you are using a Domain group, you must specify \<*Domain NetBIOS Name*\>\ as the prefix for the host Windows Group name.</span></span> <span data-ttu-id="d3a7f-119">Por ejemplo, CONTOSO\btssvc.</span><span class="sxs-lookup"><span data-stu-id="d3a7f-119">For example, CONTOSO\btssvc.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3a7f-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3a7f-120">See Also</span></span>  
 <span data-ttu-id="d3a7f-121">[Administración de Hosts y las cuentas de servicio](../core/managing-hosts-and-service-accounts.md) </span><span class="sxs-lookup"><span data-stu-id="d3a7f-121">[Managing Hosts and Service Accounts](../core/managing-hosts-and-service-accounts.md) </span></span>  
 <span data-ttu-id="d3a7f-122">[Administrar la seguridad de servidor BizTalk Server](../core/managing-biztalk-server-security.md) </span><span class="sxs-lookup"><span data-stu-id="d3a7f-122">[Managing BizTalk Server Security](../core/managing-biztalk-server-security.md) </span></span>  
 <span data-ttu-id="d3a7f-123">[Cómo administrar el grupo de administradores de BizTalk Server](../core/how-to-manage-the-biztalk-server-administrators-group.md) </span><span class="sxs-lookup"><span data-stu-id="d3a7f-123">[How to Manage the BizTalk Server Administrators Group](../core/how-to-manage-the-biztalk-server-administrators-group.md) </span></span>  
 [<span data-ttu-id="d3a7f-124">Procedimientos recomendados para administrar grupos y cuentas de usuario de Windows</span><span class="sxs-lookup"><span data-stu-id="d3a7f-124">Best Practices for Managing Windows Groups and User Accounts</span></span>](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)