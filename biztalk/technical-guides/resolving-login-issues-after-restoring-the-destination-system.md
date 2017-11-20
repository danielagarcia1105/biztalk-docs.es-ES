---
title: "Resolver problemas de inicio de sesión después de restaurar el sistema de destino | Documentos de Microsoft"
description: "Incluir inicios de sesión de SQL Server para resolver usuarios huérfanos en BizTalk Server trasvase de registros"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e9232ca3-dadb-4b3c-8ec4-4e307c32d2e5
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 559302718c9fe504c9c264de92f6a4af161d91f9
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="resolving-login-issues-after-restoring-the-destination-system"></a><span data-ttu-id="05efe-103">Resolver problemas de inicio de sesión después de restaurar el sistema de destino</span><span class="sxs-lookup"><span data-stu-id="05efe-103">Resolving Login Issues After Restoring the Destination System</span></span>

## <a name="orphaned-users"></a><span data-ttu-id="05efe-104">Usuarios huérfanos</span><span class="sxs-lookup"><span data-stu-id="05efe-104">Orphaned users</span></span>
<span data-ttu-id="05efe-105">Dependiendo de cómo se ha configurado el sistema de origen durante la implementación, los usuarios "huérfanos" que necesite resolver.</span><span class="sxs-lookup"><span data-stu-id="05efe-105">Depending on how the source system was configured during deployment, "orphaned" users may need to be resolved.</span></span> <span data-ttu-id="05efe-106">Un usuario huérfano de la base de datos es un usuario que no tiene una seguridad correspondiente inicio de sesión en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05efe-106">An orphaned database user is a user who does not have a corresponding security login in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="05efe-107">Crear inicios de sesión correspondientes para estos usuarios antes de poner el sistema en línea mediante el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] SQL Management Studio (en **seguridad**, **inicios de sesión**).</span><span class="sxs-lookup"><span data-stu-id="05efe-107">Create corresponding logins for these users before bringing the system online using the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] SQL Management Studio (in **Security**, **Logins**).</span></span> <span data-ttu-id="05efe-108">Puede crear estos inicios de sesión en cualquier momento, pero se recomienda que se crean cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se configura el trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="05efe-108">You can create these logins at any point, but we recommend that you create them when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping is configured.</span></span>  
  
 <span data-ttu-id="05efe-109">Los inicios de sesión que se crean deben corresponder a las cuentas de Windows y grupos que se usa cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se configura en el sistema de origen y los inicios de sesión que se crearon manualmente y se usa en ninguna [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-creó el rol.</span><span class="sxs-lookup"><span data-stu-id="05efe-109">The logins that are created should correspond to the Windows accounts and groups that were used when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] was configured on the source system and to any logins that were manually created and used in any [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-created role.</span></span> <span data-ttu-id="05efe-110">Si estos inicios de sesión corresponden a las cuentas de Windows locales o grupos, los grupos y cuentas deben crearse antes de que se puede agregar el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="05efe-110">If these logins correspond to local Windows accounts or groups, the accounts and groups must first be created before the login can be added.</span></span> <span data-ttu-id="05efe-111">Si no se cambia el nombre del equipo del servidor BizTalk Server, a continuación, resuelva los usuarios asociados con los inicios de sesión para los grupos y cuentas locales.</span><span class="sxs-lookup"><span data-stu-id="05efe-111">If the computer name for the BizTalk server is not changed, then resolve the users associated with the logins for the local accounts and groups.</span></span>  
  
 <span data-ttu-id="05efe-112">Al configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] envío, de registro puede [KB 918992: transferir los inicios de sesión y contraseñas entre instancias de SQL Server](https://support.microsoft.com/help/918992/how-to-transfer-logins-and-passwords-between-instances-of-sql-server) para crear una secuencia de comandos que agrega los inicios de sesión necesarios para el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="05efe-112">When configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping, you can [KB 918992: Transfer the logins and the passwords between instances of SQL Server](https://support.microsoft.com/help/918992/how-to-transfer-logins-and-passwords-between-instances-of-sql-server) to create a script that adds the necessary logins to the destination server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05efe-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="05efe-113">See Also</span></span>  
 [<span data-ttu-id="05efe-114">Solución de problemas de trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="05efe-114">Troubleshooting Log Shipping</span></span>](../technical-guides/troubleshooting-log-shipping.md)
