---
title: Control de acceso de grupos y cuentas de servicio | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- access control, service accounts
- user accounts, default accounts
- service accounts, security
- user accounts, unsupported
- access control, groups
- service accounts, access control
- groups, access control
- groups, security
ms.assetid: 411a7bfa-6675-4d09-9e37-83e2941df3c6
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67bc5799d88c0dca876df463eb37d4af65ec84d3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="access-control-for-groups-and-service-accounts"></a><span data-ttu-id="e5778-102">Control de acceso para grupos y cuentas de servicio</span><span class="sxs-lookup"><span data-stu-id="e5778-102">Access Control for Groups and Service Accounts</span></span>
<span data-ttu-id="e5778-103">Cada instancia de host de BizTalk se ejecuta bajo una cuenta de servicio creada por el usuario.</span><span class="sxs-lookup"><span data-stu-id="e5778-103">Each BizTalk Host instance runs under a user-created service account.</span></span> <span data-ttu-id="e5778-104">Las cuentas de servicio y sus contraseñas deben proporcionarse en el momento de crear la instancia de host en un equipo.</span><span class="sxs-lookup"><span data-stu-id="e5778-104">You must provide the service accounts and their passwords at the time you create the host instance on a computer.</span></span> <span data-ttu-id="e5778-105">A continuación, BizTalk Server verifica que esas cuentas tienen los derechos de usuario mínimos necesarios para realizar sus tareas agregando cada una de ellas a un grupo de Windows local o de dominio que, a su vez, la agrega a la función de base de datos de SQL Server específica de ese host.</span><span class="sxs-lookup"><span data-stu-id="e5778-105">BizTalk Server then ensures that the accounts have the minimum user rights needed to do their jobs by adding each of these service accounts to a local or domain Windows group that, in turn, it adds to the SQL Server Database role specific to that host.</span></span>  
  
 <span data-ttu-id="e5778-106">Este procedimiento ofrece las siguientes ventajas:</span><span class="sxs-lookup"><span data-stu-id="e5778-106">This approach offers the following benefits:</span></span>  
  
-   <span data-ttu-id="e5778-107">Puede darse una cuenta de servicio distinta a cada instancia de host, lo que permite cambiar las contraseñas de cada instancia de host sin desconectar servidores.</span><span class="sxs-lookup"><span data-stu-id="e5778-107">You can give each host instance a distinct service account, making it possible to change the passwords for each host instance without having to take servers offline.</span></span> <span data-ttu-id="e5778-108">Pueden realizarse actualizaciones sucesivas de contraseñas sin interrumpir el servicio.</span><span class="sxs-lookup"><span data-stu-id="e5778-108">You can perform rolling password updates without interrupting service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e5778-109">No puede utilizar la misma cuenta de servicio para hosts con autenticación de confianza y para hosts sin dicha autenticación.</span><span class="sxs-lookup"><span data-stu-id="e5778-109">You cannot use the same service account for hosts that are authentication trusted and hosts that are not authentication trusted.</span></span>  
  
-   <span data-ttu-id="e5778-110">Si concede derechos de usuario de recurso al grupo local o de dominio en el nivel de Microsoft SQL Server™, puede agregar y quitar cuentas de servicio sin tener que cambiar los derechos de usuario concedidos en SQL Server, lo que le ahorrará trabajo administrativo y reducirá su costo total de propiedad.</span><span class="sxs-lookup"><span data-stu-id="e5778-110">If you grant resource user rights to the local or domain group at the Microsoft SQL Server™ level, you can add and subtract service accounts without having to change the user rights granted in SQL Server, thus reducing your management burden and total cost of ownership.</span></span>  
  
 <span data-ttu-id="e5778-111">Con el fin de garantizar que las cuentas de servicio tienen los derechos de usuario mínimos necesarios para realizar sus tareas, las funciones de base de datos de SQL Server creadas por BizTalk Server para las cuentas de servicio no son idénticas en todas las bases de datos de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="e5778-111">To ensure that the service accounts have the minimum user rights they need to do their jobs, the SQL Server Database roles that BizTalk Server creates for the service accounts are not identical on all the BizTalk Server databases.</span></span> <span data-ttu-id="e5778-112">Para las bases de datos de seguimiento y administración, todas las cuentas de servicio de instancia de host necesitan tener acceso a los mismos objetos de SQL Server, por lo que BizTalk Server crea una sola función de base de datos de SQL Server denominada BTS_Host_User.</span><span class="sxs-lookup"><span data-stu-id="e5778-112">For the Management and Tracking databases, all of the host instance service accounts need access to the same SQL Server objects, so BizTalk Server created a single SQL Server Database role named BTS_Host_User.</span></span> <span data-ttu-id="e5778-113">BizTalk agrega todos los grupos de Windows creados para hosts de BizTalk a esa función de base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e5778-113">BizTalk adds all the Windows groups created for BizTalk hosts to this SQL Server Database role.</span></span>  
  
 <span data-ttu-id="e5778-114">Para la base de datos de cuadro de mensajes, cada host tiene ciertos recursos dedicados.</span><span class="sxs-lookup"><span data-stu-id="e5778-114">For the MessageBox database, each host has some resources dedicated to that host.</span></span> <span data-ttu-id="e5778-115">BizTalk Server crea un rol de base de datos de SQL Server por host, denominada BTS_\<*hostname*> _usuario, y agrega el grupo de Windows para cada host en sus respectivos roles de base de datos de SQL Server con el fin de bloquear el acceso de un host recursos por otro host.</span><span class="sxs-lookup"><span data-stu-id="e5778-115">BizTalk Server creates a SQL Server Database role per host, named BTS_\<*hostname*>_User, and adds the Windows group for each host to its respective SQL Server Database role in order to block access of one host resources by another host.</span></span>  
  
## <a name="accounts-not-supported-by-biztalk-server"></a><span data-ttu-id="e5778-116">Cuentas no admitidas por BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="e5778-116">Accounts not supported by BizTalk Server</span></span>  
 <span data-ttu-id="e5778-117">BizTalk Server no permite utilizar ninguna de las siguientes cuentas integradas de Windows:</span><span class="sxs-lookup"><span data-stu-id="e5778-117">BizTalk Server does not support using any of the following built-in Windows accounts:</span></span>  
  
-   <span data-ttu-id="e5778-118">NT_AUTHORITY\NetworkService</span><span class="sxs-lookup"><span data-stu-id="e5778-118">NT_AUTHORITY\NetworkService</span></span>  
  
-   <span data-ttu-id="e5778-119">LocalSystem (Sistema local)</span><span class="sxs-lookup"><span data-stu-id="e5778-119">LocalSystem</span></span>  
  
-   <span data-ttu-id="e5778-120">NT_AUTHORITY\LocalService</span><span class="sxs-lookup"><span data-stu-id="e5778-120">NT_AUTHORITY\LocalService</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5778-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5778-121">See Also</span></span>  
 <span data-ttu-id="e5778-122">[Control de acceso para los Roles administrativos](../core/access-control-for-administrative-roles.md) </span><span class="sxs-lookup"><span data-stu-id="e5778-122">[Access Control for Administrative Roles](../core/access-control-for-administrative-roles.md) </span></span>  
 <span data-ttu-id="e5778-123">[Derechos de usuario mínimos de seguridad](../core/minimum-security-user-rights.md) </span><span class="sxs-lookup"><span data-stu-id="e5778-123">[Minimum Security User Rights](../core/minimum-security-user-rights.md) </span></span>  
 <span data-ttu-id="e5778-124">[Grupos de Windows y cuentas de usuario en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="e5778-124">[Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md) </span></span>  
 [<span data-ttu-id="e5778-125">Control de acceso y seguridad de los datos</span><span class="sxs-lookup"><span data-stu-id="e5778-125">Access Control and Data Security</span></span>](../core/access-control-and-data-security.md)