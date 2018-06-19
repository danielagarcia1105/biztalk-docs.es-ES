---
title: Grupos de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Management database, groups
- groups
- groups, Management database
- groups, about groups
ms.assetid: 197cbcf6-c722-4cbb-9642-3cb8a34757e2
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b9cd38012f0e2a7ba5f4cfcb56ae63678aacbf8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231284"
---
# <a name="biztalk-groups"></a><span data-ttu-id="0534d-102">Grupos de BizTalk</span><span class="sxs-lookup"><span data-stu-id="0534d-102">BizTalk Groups</span></span>

## <a name="overview"></a><span data-ttu-id="0534d-103">Información general</span><span class="sxs-lookup"><span data-stu-id="0534d-103">Overview</span></span>
<span data-ttu-id="0534d-104">El *grupo de BizTalk* es una unidad de organización que normalmente representa una empresa, departamento, concentrador u otra unidad de negocio que requiere una implementación contenida de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="0534d-104">The *BizTalk group* is a unit of organization that usually represents an enterprise, department, hub, or other business unit that requires a contained BizTalk Server implementation.</span></span> <span data-ttu-id="0534d-105">El grupo de BizTalk tiene una relación uno a uno con una base de datos de administración de BizTalk Server (conocida como la base de datos de configuración de BizTalk Server en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="0534d-105">The BizTalk group has a one-to-one relationship with a BizTalk Server Management database (known as the BizTalk Server Configuration database in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0534d-106">Aunque los grupos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pueden contener varios equipos con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], cualquier equipo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] dado solo puede estar asociado con un único grupo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0534d-106">While [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] groups may contain multiple [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computers, any given [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer may only be associated with a single [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group.</span></span>  
  
 <span data-ttu-id="0534d-107">La base de datos de administración de BizTalk almacena información de configuración para el grupo de BizTalk y los equipos con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de ese grupo.</span><span class="sxs-lookup"><span data-stu-id="0534d-107">The BizTalk Management database stores configuration information for the BizTalk group and the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computers in that group.</span></span> <span data-ttu-id="0534d-108">Esta información de configuración especifica parte de la lógica de procesamiento de mensajes de los servidores y también dónde se ejecutará físicamente esta lógica.</span><span class="sxs-lookup"><span data-stu-id="0534d-108">This configuration information specifies part of the message-processing logic for the servers and where this logic will physically run.</span></span> <span data-ttu-id="0534d-109">Para obtener más información acerca de la base de datos de administración de BizTalk Server, vea [bases de datos de BizTalk Server](../core/databases-in-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="0534d-109">For more information about the BizTalk Server Management database, see [Databases in BizTalk Server](../core/databases-in-biztalk-server.md).</span></span>  
  
 <span data-ttu-id="0534d-110">Debe especificar la misma base de datos de administración de BizTalk Server para todas las instalaciones de servidor del grupo, de modo que pueda administrar todos los servidores desde la consola de administración.</span><span class="sxs-lookup"><span data-stu-id="0534d-110">You must specify the same BizTalk Server Management database for each server installation in the group so that you can administer each server from the administration console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0534d-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="0534d-111">See Also</span></span>  
 <span data-ttu-id="0534d-112">[Configuración de BizTalk Server](../install-and-config-guides/configure-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="0534d-112">[Configure BizTalk Server](../install-and-config-guides/configure-biztalk-server.md) </span></span>  
 <span data-ttu-id="0534d-113">[Administración de grupos](../core/managing-groups.md) </span><span class="sxs-lookup"><span data-stu-id="0534d-113">[Managing Groups](../core/managing-groups.md) </span></span>  
 [<span data-ttu-id="0534d-114">Entidades</span><span class="sxs-lookup"><span data-stu-id="0534d-114">Entities</span></span>](../core/entities.md)