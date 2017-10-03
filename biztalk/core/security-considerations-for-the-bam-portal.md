---
title: Consideraciones de seguridad para el Portal de BAM | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM portal, security
- BAM portal, administrator accounts
- user accounts, BAM
- administrator accounts, BAM portal
- BAM portal, user accounts
- security, BAM portal
ms.assetid: 5c8e6034-dfb8-4dba-b040-0c19504abdb2
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b0f5220eba5b66daf41dffc7ab74f93df8bb509
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="security-considerations-for-the-bam-portal"></a><span data-ttu-id="7aacf-102">Consideraciones de seguridad para el portal de BAM</span><span class="sxs-lookup"><span data-stu-id="7aacf-102">Security Considerations for the BAM Portal</span></span>
<span data-ttu-id="7aacf-103">Con el principio de privilegios mínimos, las cuentas de usuario deben tener permisos restrictivos para realizar las tareas habituales en el portal de BAM.</span><span class="sxs-lookup"><span data-stu-id="7aacf-103">Using the principle of least privilege, user accounts should have restrictive permissions to perform routine tasks in the BAM portal.</span></span> <span data-ttu-id="7aacf-104">Tenga en cuenta las siguientes consideraciones cuando configure sus cuentas de usuario para BAM para equilibrar la seguridad con el acceso apropiado para usuarios.</span><span class="sxs-lookup"><span data-stu-id="7aacf-104">Keep the following points in mind as you set up your user accounts for BAM to balance security with appropriate access for users.</span></span>  
  
## <a name="user-accounts"></a><span data-ttu-id="7aacf-105">Cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="7aacf-105">User accounts</span></span>  
 <span data-ttu-id="7aacf-106">Cuentas de usuario con permisos mínimos no pueden usar el navigationfeature distribuida portal de BAM.</span><span class="sxs-lookup"><span data-stu-id="7aacf-106">User accounts with minimum permissions are not able to use the BAM portal distributed navigationfeature.</span></span> <span data-ttu-id="7aacf-107">Para poder utilizar esta característica, estas cuentas deben tener suficientes permisos para permitir el acceso a los servicios Web en el equipo remoto y en el local.</span><span class="sxs-lookup"><span data-stu-id="7aacf-107">To be able to use this feature, these accounts must have sufficient permissions to allow access to the Web services on the remote computer as well as on the local computer.</span></span>  
  
 <span data-ttu-id="7aacf-108">Es necesario que las cuentas de usuario para los servicios Web de BAM tengan permisos para obtener acceso a las bases de datos a las que se hace referencia y que sean miembro del rol BAM_ManagementWS de BAM en las bases de datos a las que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="7aacf-108">User accounts for the BAM Web services must have permissions to access all referenced databases and must be a member of the BAM_ManagementWS role in the referenced databases.</span></span>  
  
 <span data-ttu-id="7aacf-109">Deben tenerse en cuenta estas consideraciones para los siguientes tipos de usuario.</span><span class="sxs-lookup"><span data-stu-id="7aacf-109">For the following user types, you should be aware of these considerations:</span></span>  
  
-   <span data-ttu-id="7aacf-110">Los usuarios de dominio deben tener permisos de acceso a equipos remotos que alojan bases de datos de importación principal a las que se está obteniendo acceso.</span><span class="sxs-lookup"><span data-stu-id="7aacf-110">Domain Users, must have access permissions on remote computers that host Primary Import databases that are being accessed.</span></span>  
  
-   <span data-ttu-id="7aacf-111">Los usuarios que tienen asignados un rol de usuario local no pueden utilizar la exploración distribuida.</span><span class="sxs-lookup"><span data-stu-id="7aacf-111">Users who are assigned Local User role, cannot use distributed navigation.</span></span>  
  
## <a name="administrator-accounts"></a><span data-ttu-id="7aacf-112">Cuentas de administrador</span><span class="sxs-lookup"><span data-stu-id="7aacf-112">Administrator accounts</span></span>  
 <span data-ttu-id="7aacf-113">Los administradores tienen que ser miembros del grupo securityadmin o del sysadmin para conceder permisos a los usuarios de dominio.</span><span class="sxs-lookup"><span data-stu-id="7aacf-113">Administrators must be members of the securityadmin or sysadmin groups to grant permissions to domain users.</span></span>  
  
 <span data-ttu-id="7aacf-114">Para ejecutar la utilidad de administración de BAM, debe ser, al menos, operador de base de datos para las bases de datos de BAM.</span><span class="sxs-lookup"><span data-stu-id="7aacf-114">To run the BAM Management utility, you must be at least a database operator for the BAM databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aacf-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="7aacf-115">See Also</span></span>  
 [<span data-ttu-id="7aacf-116">Portal de BAM</span><span class="sxs-lookup"><span data-stu-id="7aacf-116">BAM Portal</span></span>](../core/bam-portal.md)