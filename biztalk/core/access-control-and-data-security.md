---
title: Control de acceso y seguridad de los datos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- access control, BizTalk Server Operator role
- databases, SQL roles
- access control, about access control
- BizTalk Server Administrator role
- databases, access control
- access control
- access control, BizTalk Server Administrator role
- access control, SQL roles
- user accounts, access control
- BizTalk Server Operator role
ms.assetid: f04fd4a3-0f8c-4170-934a-9cc77edd7f34
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11cb00eabf6110de78e2d194e0a25bfac6a3b6b0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225644"
---
# <a name="access-control-and-data-security"></a><span data-ttu-id="20a29-102">Control de acceso y seguridad de los datos</span><span class="sxs-lookup"><span data-stu-id="20a29-102">Access Control and Data Security</span></span>
<span data-ttu-id="20a29-103">BizTalk Server limita el acceso a sus procesos y bases de datos concediendo derechos de usuario mínimos; se pueden proteger datos importantes del sistema empleando características de Microsoft Windows Server.</span><span class="sxs-lookup"><span data-stu-id="20a29-103">BizTalk Server limits access to its processes and databases by using minimum user rights; you can help secure important data in the system by using features from Microsoft Windows Server.</span></span> <span data-ttu-id="20a29-104">Por motivos de seguridad, los administradores de BizTalk Server y los hosts de BizTalk sólo deben tener los derechos de usuario necesarios para realizar sus tareas.</span><span class="sxs-lookup"><span data-stu-id="20a29-104">For security reasons, BizTalk Server Administrators and BizTalk Hosts should not have more user rights than necessary to perform their jobs.</span></span>  
  
 <span data-ttu-id="20a29-105">BizTalk controla el acceso administrativo a los datos mediante funciones SQL, con lo que controla el acceso a los datos tanto mediante herramientas como directamente por la base de datos.</span><span class="sxs-lookup"><span data-stu-id="20a29-105">BizTalk controls Administrative access to data using SQL roles, thereby controlling access to data both via tools and directly via the database.</span></span> <span data-ttu-id="20a29-106">El acceso de host de BizTalk a los datos se controla mediante la utilización de cuentas y grupos de usuarios de host.</span><span class="sxs-lookup"><span data-stu-id="20a29-106">BizTalk Host access to data is controlled using Host User groups and accounts.</span></span>  
  
 <span data-ttu-id="20a29-107">En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], hay dos funciones administrativas: el Administrador de BizTalk Server y el operador de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="20a29-107">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], there are two Administrative Roles: the BizTalk Server Administrator, and the BizTalk Server Operator.</span></span> <span data-ttu-id="20a29-108">Cada vez que se crea una base de datos de BizTalk Server mediante instalación o mediante la consola de administración de BizTalk Server, éste crea automáticamente funciones SQL para ambas funciones administrativas en esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="20a29-108">Anytime you create a BizTalk Server database through installation or the BizTalk Server Administration Console, BizTalk Server automatically creates SQL roles for both these administrative roles in that database.</span></span> <span data-ttu-id="20a29-109">BizTalk Server concede a cada función, así como a cualquier inicio de sesión de SQL Server asignado a ella, los derechos de usuario mínimos requeridos por los administradores de los objetos de SQL Server (tablas, vistas, procedimientos almacenados, etc.) para realizar tareas administrativas en esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="20a29-109">BizTalk Server grants each role, and any SQL Server login assigned to the role, the minimum user rights needed by administrators on the SQL Server objects (tables, views, stored procedures, etc) to perform administrative tasks on that database.</span></span>  
  
 <span data-ttu-id="20a29-110">El Administrador de BizTalk Server tiene una función de muchos privilegios, con acceso a los datos de configuración y de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="20a29-110">The BizTalk Server Administrator is a high privilege role with access to configuration and tracking data.</span></span> <span data-ttu-id="20a29-111">El Operador de BizTalk Server tiene una función de pocos privilegios, con acceso sólo para supervisar y solucionar problemas de acciones.</span><span class="sxs-lookup"><span data-stu-id="20a29-111">The BizTalk Server Operator is a low privilege role with access only to monitoring and troubleshooting actions.</span></span> <span data-ttu-id="20a29-112">Esta última función puede ver estados de servicio y flujos de mensajes, iniciar o detener aplicaciones y finalizar o reanudar instancias de servicio, pero no puede cambiar la configuración ni ver las propiedades ni el contenido de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="20a29-112">This latter role can view service state and message flow and can start or stop applications and terminate and resume service instances, but cannot change configuration or view message properties and content.</span></span>  
  
 <span data-ttu-id="20a29-113">Igualmente, BizTalk Server crea en cada base de datos una función SQL para el grupo de usuarios de cada host, y le concede los derechos de usuario mínimos para que el grupo de usuarios realice tareas para ese host.</span><span class="sxs-lookup"><span data-stu-id="20a29-113">Similarly, BizTalk Server creates in each database a SQL role for the user group for each host, and grants this role the minimum user rights it needs for the user group to perform tasks for that host.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="20a29-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="20a29-114">In This Section</span></span>  
  
-   [<span data-ttu-id="20a29-115">Cuentas de grupos y de usuario de Windows en BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="20a29-115">Windows Groups and User Accounts in BizTalk Server</span></span>](../core/windows-groups-and-user-accounts-in-biztalk-server.md)  
  
-   [<span data-ttu-id="20a29-116">Control de acceso para grupos y cuentas de servicio</span><span class="sxs-lookup"><span data-stu-id="20a29-116">Access Control for Groups and Service Accounts</span></span>](../core/access-control-for-groups-and-service-accounts.md)  
  
-   [<span data-ttu-id="20a29-117">Control de acceso para los Roles administrativos</span><span class="sxs-lookup"><span data-stu-id="20a29-117">Access Control for Administrative Roles</span></span>](../core/access-control-for-administrative-roles.md)  
  
-   [<span data-ttu-id="20a29-118">Control de acceso a información empresarial</span><span class="sxs-lookup"><span data-stu-id="20a29-118">Access Control to Business Information</span></span>](../core/access-control-to-business-information.md)  
  
-   [<span data-ttu-id="20a29-119">Derechos de usuario mínimos de seguridad</span><span class="sxs-lookup"><span data-stu-id="20a29-119">Minimum Security User Rights</span></span>](../core/minimum-security-user-rights.md)