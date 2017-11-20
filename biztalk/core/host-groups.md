---
title: Los grupos host | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- host groups, privileges
- Windows groups, host groups
- host groups, Windows groups
- host groups, about host groups
- host groups
ms.assetid: 0d92478b-b3a2-4c5a-925e-5495ee481e82
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d5e7782dd2e98822d6fc9e51ca08dac2d31f166
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="host-groups"></a><span data-ttu-id="3f46b-102">Grupos de hosts</span><span class="sxs-lookup"><span data-stu-id="3f46b-102">Host Groups</span></span>
<span data-ttu-id="3f46b-103">El grupo de hosts es el grupo de Windows (denominado de forma predeterminada grupo de usuarios de la aplicación de BizTalk) que se utiliza para cuentas con acceso a los hosts de BizTalk de tipo En curso (procesos de host en el servidor BizTalk Server).</span><span class="sxs-lookup"><span data-stu-id="3f46b-103">The host group is the Windows group (named the BizTalk Application Users group by default) that you use for accounts with access to the in-process BizTalk hosts (host processes in BizTalk Server).</span></span> <span data-ttu-id="3f46b-104">Se recomienda que utilice un grupo de hosts para cada host de tipo En curso del entorno.</span><span class="sxs-lookup"><span data-stu-id="3f46b-104">It is recommended that you use one host group for each in-process host in your environment.</span></span>  
  
 <span data-ttu-id="3f46b-105">Sólo se puede asociar un host con un grupo de Windows (denominado un *grupo host*).</span><span class="sxs-lookup"><span data-stu-id="3f46b-105">You can only associate a host with one Windows group (called a *host group*).</span></span> <span data-ttu-id="3f46b-106">El grupo de hosts debe disponer de un inicio de sesión de SQL Server y de privilegios en todas las bases de datos de BizTalk Server correspondientes.</span><span class="sxs-lookup"><span data-stu-id="3f46b-106">The host group must have a SQL Server login and privileges in all relevant BizTalk Server databases.</span></span> <span data-ttu-id="3f46b-107">Cuando asocia un host con el grupo de hosts, le asigna al host los privilegios del grupo de hosts.</span><span class="sxs-lookup"><span data-stu-id="3f46b-107">When you associate a host with the host group, you grant the host the privileges of the host group.</span></span>  
  
 <span data-ttu-id="3f46b-108">Si utiliza el Asistente para configuración para crear hosts y especifica un grupo de Windows local para utilizarlo con hosts, el Asistente para configuración crea dos grupos de Windows de forma automática.</span><span class="sxs-lookup"><span data-stu-id="3f46b-108">If you use the Configuration Wizard to create hosts, and you specify a local Windows group to use for hosts, the Configuration Wizard automatically creates two Windows groups.</span></span> <span data-ttu-id="3f46b-109">Los nombres predeterminados de estos grupos son el Grupo de usuarios de la aplicación de BizTalk y el Grupo de usuarios de hosts aislados de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="3f46b-109">The default names of these groups are the BizTalk Application Users group and the BizTalk Isolated Host Users group.</span></span>  
  
 <span data-ttu-id="3f46b-110">Al crear una instancia de host de un host asociado con el grupo de hosts, la instancia de host hereda los privilegios de la base de datos del grupo de hosts.</span><span class="sxs-lookup"><span data-stu-id="3f46b-110">When you create a host instance of a host associated with the host group, the host instance inherits the database privileges of the host group.</span></span>  
  
 <span data-ttu-id="3f46b-111">El grupo de hosts en una propiedad del objeto Instrumental de administración de Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="3f46b-111">The host group is a property of the host Windows Management Instrumentation (WMI) object.</span></span> <span data-ttu-id="3f46b-112">Es posible cambiar el grupo de Windows al que pertenece un host si no hay instancias de host de ese host.</span><span class="sxs-lookup"><span data-stu-id="3f46b-112">You can change the Windows group that a host belongs to if there are no host instances of the host.</span></span>  
  
 <span data-ttu-id="3f46b-113">El grupo de hosts al que pertenece un host se especifica al crear el host.</span><span class="sxs-lookup"><span data-stu-id="3f46b-113">You specify the host group a host belongs to when you create the host.</span></span> <span data-ttu-id="3f46b-114">El proveedor WMI de BizTalk concede los privilegios que el grupo de hosts tiene con respecto al host (por ejemplo, los privilegios de BizTalk Server requeridos para la funcionalidad en tiempo de ejecución, incluidos los inicios de sesión de SQL Server y los accesos de usuario a la base de datos).</span><span class="sxs-lookup"><span data-stu-id="3f46b-114">The BizTalk WMI provider grants the privileges that the host group has (for example, the BizTalk Server privileges required for runtime functionality, including SQL Server logins and database user access) to the host.</span></span> <span data-ttu-id="3f46b-115">Debe especificar la cuenta de servicio correcta (host) al crear una instancia de host para que el proveedor WMI de BizTalk Server conceda los privilegios del grupo de hosts a la instancia de host.</span><span class="sxs-lookup"><span data-stu-id="3f46b-115">You must specify the correct service account (host) when you create a host instance, so that the BizTalk Server WMI provider grants the privileges of the host group to the host instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f46b-116">Si desea crear un grupo de hosts local, puede crear un grupo de Windows local y asignar un usuario de dominio como miembro del grupo.</span><span class="sxs-lookup"><span data-stu-id="3f46b-116">If you want to create a local host group, you can create a local Windows group and assign a domain user as a member of the group.</span></span> <span data-ttu-id="3f46b-117">Si especifica un grupo de Windows local para el host, el miembro del grupo de Windows, sea un usuario local o de dominio, se puede utilizar como el usuario de inicio de sesión de instancia de host.</span><span class="sxs-lookup"><span data-stu-id="3f46b-117">If you specify a local Windows group for the Host, the Windows group member, whether it is a domain or local user, can be used as the host instance log-on user.</span></span>  
  
 <span data-ttu-id="3f46b-118">El grupo de hosts requiere los privilegios siguientes:</span><span class="sxs-lookup"><span data-stu-id="3f46b-118">The host group requires the following privileges:</span></span>  
  
-   <span data-ttu-id="3f46b-119">Debe ser un miembro del rol BTS_HOST_USERS de SQL Server en las bases de datos siguientes:</span><span class="sxs-lookup"><span data-stu-id="3f46b-119">It must be a member of the BTS_HOST_USERS SQL Server role in the following databases:</span></span>  
  
    -   <span data-ttu-id="3f46b-120">Administración de BizTalk (conocida como la base de datos de configuración en [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)])</span><span class="sxs-lookup"><span data-stu-id="3f46b-120">BizTalk Management (known as the Configuration database in [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)])</span></span>  
  
    -   <span data-ttu-id="3f46b-121">Cuadro de mensajes</span><span class="sxs-lookup"><span data-stu-id="3f46b-121">MessageBox</span></span>  
  
    -   <span data-ttu-id="3f46b-122">Motor de reglas</span><span class="sxs-lookup"><span data-stu-id="3f46b-122">Rule Engine</span></span>  
  
    -   <span data-ttu-id="3f46b-123">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="3f46b-123">Tracking</span></span>  
  
    -   <span data-ttu-id="3f46b-124">Importación principal de SAE</span><span class="sxs-lookup"><span data-stu-id="3f46b-124">BAM Primary Import</span></span>  
  
-   <span data-ttu-id="3f46b-125">Debe ser miembro del rol BTS_\<nombre de host in-process > rol de SQL Server _USERS de la base de datos de cuadro de mensajes</span><span class="sxs-lookup"><span data-stu-id="3f46b-125">It must be a member of the BTS_\<in-process host name>_USERS SQL Server role for the MessageBox database</span></span>  
  
-   <span data-ttu-id="3f46b-126">Debe ser miembro del rol BAM_EVENT_WRITER de SQL Server en la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="3f46b-126">It must be a member of the BAM_EVENT_WRITER SQL Server role in the BAM Primary Import database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f46b-127">Si designa un host como host de seguimiento, la consola de administración de BizTalk Server quita automáticamente el grupo de hosts de BizTalk de los roles de SQL Server para la base de datos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3f46b-127">If you designate a host as a tracking host, BizTalk Server Administration automatically removes the BizTalk Host group from the SQL Server roles for the Tracking database.</span></span> <span data-ttu-id="3f46b-128">Debe quitar manualmente el grupo de hosts de BizTalk de los roles del servidor SQL Server para la base de datos de administración de BizTalk y la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="3f46b-128">You must manually remove the BizTalk Host group from the SQL Server roles for the BizTalk Management database and the MessageBox database.</span></span> <span data-ttu-id="3f46b-129">Para obtener información acerca de cómo designar un host como host de seguimiento, vea [cómo modificar propiedades de Host](../core/how-to-modify-host-properties.md).</span><span class="sxs-lookup"><span data-stu-id="3f46b-129">For information about designating a host as a tracking host, see [How to Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f46b-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f46b-130">See Also</span></span>  
 [<span data-ttu-id="3f46b-131">Entidades</span><span class="sxs-lookup"><span data-stu-id="3f46b-131">Entities</span></span>](../core/entities.md)