---
title: Administrar la seguridad de servidor BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Server, security
- security, user accounts
- security, passwords
- certificates, security
- security, certificates
- security, BizTalk Server
- passwords, security
- user accounts, security
ms.assetid: adc89b0a-9846-4c99-b0fc-a32fc56ed769
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f31ef3483661b20ff62cadb0ec601282a05af9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262860"
---
# <a name="managing-biztalk-server-security"></a><span data-ttu-id="8ed35-102">Administrar la seguridad de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="8ed35-102">Managing BizTalk Server Security</span></span>
<span data-ttu-id="8ed35-103">El mantenimiento de un entorno seguro de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] requiere la administración de cuentas, certificados y contraseñas.</span><span class="sxs-lookup"><span data-stu-id="8ed35-103">Maintaining a secure Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment requires that you manage accounts, certificates, and passwords.</span></span> <span data-ttu-id="8ed35-104">Para ayudar a garantizar la seguridad de los documentos empresariales que controla BizTalk Server, los administradores de BizTalk Server administran las siguientes cuentas y certificados:</span><span class="sxs-lookup"><span data-stu-id="8ed35-104">To help ensure the security of the business documents handled by BizTalk Server, BizTalk Server administrators manage the following accounts and certificates:</span></span>  
  
-   <span data-ttu-id="8ed35-105">**Grupo de administradores de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="8ed35-105">**BizTalk Server Administrators group**.</span></span> <span data-ttu-id="8ed35-106">Los usuarios que van a realizar tareas administrativas mediante la consola de administración de BizTalk Server o el Instrumental de administración de Microsoft Windows (Windows Management Instrumentation, WMI) deben tener concedidos los privilegios adecuados en Microsoft SQL Server y en Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="8ed35-106">For users to perform administrative tasks either through the BizTalk Administration console or by using the Microsoft Windows Management Instrumentation (WMI) provider, they must be granted the proper privileges in Microsoft SQL Server and Microsoft Windows.</span></span> <span data-ttu-id="8ed35-107">Para obtener más información acerca de los privilegios para las tareas administrativas, consulte [derechos de usuario mínimos de seguridad](../core/minimum-security-user-rights.md).</span><span class="sxs-lookup"><span data-stu-id="8ed35-107">For more information about the privileges for administrative tasks, see [Minimum Security User Rights](../core/minimum-security-user-rights.md).</span></span>  
  
     <span data-ttu-id="8ed35-108">Para obtener información sobre cómo agregar usuarios al grupo de administradores de BizTalk Server o quitar usuarios del grupo Administradores de BizTalk Server, vea [cómo administrar el grupo de administradores de BizTalk Server](../core/how-to-manage-the-biztalk-server-administrators-group.md).</span><span class="sxs-lookup"><span data-stu-id="8ed35-108">For information about adding users to the BizTalk Server Administrators group or removing users from the BizTalk Server Administrators group, see [How to Manage the BizTalk Server Administrators Group](../core/how-to-manage-the-biztalk-server-administrators-group.md).</span></span>  
  
     <span data-ttu-id="8ed35-109">Para obtener más información acerca de Enterprise Single Sign-On, vea [mediante SSO](../core/using-sso.md).</span><span class="sxs-lookup"><span data-stu-id="8ed35-109">For more information about Enterprise Single Sign-On, see [Using SSO](../core/using-sso.md).</span></span>  
  
-   <span data-ttu-id="8ed35-110">**Grupo de operadores de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="8ed35-110">**BizTalk Server Operators group**.</span></span> <span data-ttu-id="8ed35-111">El operador de BizTalk Server tiene una función con pocos privilegios, ya que sólo tiene acceso para supervisar y solucionar problemas de acciones.</span><span class="sxs-lookup"><span data-stu-id="8ed35-111">The BizTalk Server Operator is a low privileged role that only has access to monitoring and troubleshooting actions.</span></span>  
  
     <span data-ttu-id="8ed35-112">Los miembros del grupo de operadores de BizTalk Server pueden realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="8ed35-112">Members of the BizTalk Server Operators group can do the following:</span></span>  
  
    -   <span data-ttu-id="8ed35-113">Ver el estado del servicio y el flujo de mensajes.</span><span class="sxs-lookup"><span data-stu-id="8ed35-113">View service state and message flow.</span></span>  
  
    -   <span data-ttu-id="8ed35-114">Iniciar o detener aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="8ed35-114">Start or stop applications.</span></span>  
  
    -   <span data-ttu-id="8ed35-115">Iniciar o detener orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="8ed35-115">Start or stop orchestrations.</span></span>  
  
    -   <span data-ttu-id="8ed35-116">Iniciar o detener puertos de envío o grupos de puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="8ed35-116">Start or stop send ports or send port groups.</span></span>  
  
    -   <span data-ttu-id="8ed35-117">Habilitar o deshabilitar ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="8ed35-117">Enable or disable receive locations.</span></span> <span data-ttu-id="8ed35-118">Los cambios no se hacen efectivos hasta el próximo intervalo de actualización de la caché de 60 segundos, que es el intervalo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8ed35-118">The changes do not take effect until the next cache refresh interval of 60 seconds, which is the default.</span></span> <span data-ttu-id="8ed35-119">El intervalo de actualización de la caché se establece en el nivel de grupo de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="8ed35-119">The cache refresh interval is set at the BizTalk Server group level.</span></span>  
  
    -   <span data-ttu-id="8ed35-120">Finalizar y reanudar las instancias de servicios.</span><span class="sxs-lookup"><span data-stu-id="8ed35-120">Terminate and resume service instances.</span></span>  
  
     <span data-ttu-id="8ed35-121">Los miembros del grupo de operadores de BizTalk Server no pueden realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="8ed35-121">Members of the BizTalk Server Operators group cannot do the following:</span></span>  
  
    -   <span data-ttu-id="8ed35-122">Modificar la configuración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="8ed35-122">Modify the configuration for BizTalk Server.</span></span>  
  
    -   <span data-ttu-id="8ed35-123">Ver las propiedades de contexto del mensaje que estén clasificadas como información que se pueda identificar personalmente o los cuerpos de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="8ed35-123">View message context properties classified as Personally Identifiable Information (PII) or message bodies.</span></span>  
  
    -   <span data-ttu-id="8ed35-124">Modificar el transcurso del enrutamiento de mensajes, como la eliminación de suscripciones del sistema en ejecución o la agregación de suscripciones nuevas a éste, así como la capacidad para publicar mensajes en el tiempo de ejecución de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="8ed35-124">Modify the course of message routing, such as removing or adding new subscriptions to the running system, including the ability to publish messages into the BizTalk Server runtime.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8ed35-125">Si un usuario que es miembro del grupo de operadores de BizTalk Server también es administrador local en los equipos que ejecutan BizTalk Server, puede obtener acceso a los datos más allá de la función del grupo de operadores en estos equipos.</span><span class="sxs-lookup"><span data-stu-id="8ed35-125">If a user who is a member of the BizTalk Server Operators group is also a local administrator on the computers running BizTalk Server, this user can access data beyond the role of the Operators group on these computers.</span></span> <span data-ttu-id="8ed35-126">Para obtener más información, consulte [derechos de usuario mínimos de seguridad](../core/minimum-security-user-rights.md).</span><span class="sxs-lookup"><span data-stu-id="8ed35-126">For more information, see [Minimum Security User Rights](../core/minimum-security-user-rights.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8ed35-127">Si desea permitir que un usuario miembro del grupo de operadores de BizTalk Server supervise servidores BizTalk remotos, éste debe ser miembro también del grupo local de administradores en los equipos remotos.</span><span class="sxs-lookup"><span data-stu-id="8ed35-127">If you want to allow a user who is a member of the BizTalk Server Operators group to monitor remote BizTalk servers, this user must also be a member of the local Administrators group on the remote computers.</span></span>  
  
-   <span data-ttu-id="8ed35-128">**Los hosts y las cuentas de servicio**.</span><span class="sxs-lookup"><span data-stu-id="8ed35-128">**Hosts and service accounts**.</span></span> <span data-ttu-id="8ed35-129">En la creación de un host y de las instancias de host asociadas, debe proporcionar el grupo de Windows del host y las credenciales de cuentas de servicio de cada instancia de host.</span><span class="sxs-lookup"><span data-stu-id="8ed35-129">When creating a host and its associated host instances, you must provide the Windows group for the host and the service account credentials for each host instance.</span></span> <span data-ttu-id="8ed35-130">Debe asegurarse de que las cuentas de servicio de instancia de host son miembros del grupo de Windows para el host.</span><span class="sxs-lookup"><span data-stu-id="8ed35-130">You must ensure that the host instance service accounts are members of the Windows group for the host.</span></span>  
  
-   <span data-ttu-id="8ed35-131">**Certificados de firma**.</span><span class="sxs-lookup"><span data-stu-id="8ed35-131">**Signing certificates**.</span></span> <span data-ttu-id="8ed35-132">Se especifican los certificados de firma (certificados de clave privada) para el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8ed35-132">Signing certificates (private key certificates) are specified for the BizTalk group.</span></span> <span data-ttu-id="8ed35-133">Son opcionales y un administrador de BizTalk Server puede cambiarlos en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="8ed35-133">These are optional and can be changed at any time by a BizTalk Server administrator.</span></span>  
  
 <span data-ttu-id="8ed35-134">Para obtener información más completa acerca de las cuentas de Windows que utiliza BizTalk Server, vea [grupos de Windows y cuentas de usuario en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="8ed35-134">For more complete information about Windows accounts that BizTalk Server uses, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8ed35-135">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8ed35-135">In This Section</span></span>  
  
-   [<span data-ttu-id="8ed35-136">Prácticas recomendadas para administrar las cuentas de usuario y grupos de Windows</span><span class="sxs-lookup"><span data-stu-id="8ed35-136">Best Practices for Managing Windows Groups and User Accounts</span></span>](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)  
  
-   [<span data-ttu-id="8ed35-137">Prácticas recomendadas para administrar certificados</span><span class="sxs-lookup"><span data-stu-id="8ed35-137">Best Practices for Managing Certificates</span></span>](../core/best-practices-for-managing-certificates1.md)  
  
-   [<span data-ttu-id="8ed35-138">Administrar cuentas de usuario y grupos de Windows</span><span class="sxs-lookup"><span data-stu-id="8ed35-138">Managing Windows Groups and User Accounts</span></span>](../core/managing-windows-groups-and-user-accounts.md)