---
title: Problemas conocidos y solución de problemas | Documentos de Microsoft
description: Errores conocidos, zombies, solucionar problemas de rendimiento, solución de problemas de adaptadores, solucionar problemas de permisos, solucionar problemas de EDI y AS2 y mucho más en BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ecb934c6-3efa-40b6-949b-a04a73e60b07
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df13438e641d55de91096b690a8e5e95e26cbfa4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286692"
---
# <a name="troubleshooting"></a><span data-ttu-id="f0ff1-103">Solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="f0ff1-103">Troubleshooting</span></span>

## <a name="overview"></a><span data-ttu-id="f0ff1-104">Información general</span><span class="sxs-lookup"><span data-stu-id="f0ff1-104">Overview</span></span>
<span data-ttu-id="f0ff1-105">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa distintas tecnologías de Microsoft, o puede depender de ellas, incluidas, sin limitaciones, Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], Microsoft [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)], Internet Information Services (IIS), clúster de servidores de Microsoft Windows Server, inicio de sesión único (SSO) empresarial y Windows [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0ff1-105">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] makes use of or may depend on several different Microsoft technologies including but not limited to Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], the Microsoft [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)], Internet Information Services (IIS), Microsoft Windows Server Cluster, Enterprise Single Sign-On, and Windows [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].</span></span> <span data-ttu-id="f0ff1-106">Puesto que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se usa con otras muchas tecnologías, solucionar un problema con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] conlleva a menudo solucionar el problema en la tecnología o dependencia subyacente que se esté empleando.</span><span class="sxs-lookup"><span data-stu-id="f0ff1-106">Because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is used with so many other technologies, troubleshooting a problem with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] often involves troubleshooting the underlying technology or dependency that is being used.</span></span> <span data-ttu-id="f0ff1-107">En esta sección se proporciona información sobre cómo solucionar problemas específicos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], así como los problemas que puedan surgir en el software del que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] depende.</span><span class="sxs-lookup"><span data-stu-id="f0ff1-107">This section provides information about troubleshooting specific [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] problems and information about troubleshooting problems that can occur in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] dependency software.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f0ff1-108">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="f0ff1-108">Next steps</span></span> 
  
-   [<span data-ttu-id="f0ff1-109">Problemas conocidos con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f0ff1-109">Known Issues with BizTalk Server</span></span>](../core/known-issues-with-biztalk-server.md)  

-   [<span data-ttu-id="f0ff1-110">Zombies en BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f0ff1-110">Zombies in BizTalk Server</span></span>](zombies-in-biztalk-server.md)
  
-   [<span data-ttu-id="f0ff1-111">Solucionar problemas de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f0ff1-111">Troubleshoot BizTalk Server Administration</span></span>](../core/troubleshooting-biztalk-server-administration.md)  
  
-   [<span data-ttu-id="f0ff1-112">Habilitar el registro de System.Net</span><span class="sxs-lookup"><span data-stu-id="f0ff1-112">Enabling System.Net Logging</span></span>](../core/enabling-system-net-logging.md)  
  
-   [<span data-ttu-id="f0ff1-113">Solucionar problemas de permisos de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f0ff1-113">Troubleshoot BizTalk Server Permissions</span></span>](../core/troubleshooting-biztalk-server-permissions.md)  
  
-   [<span data-ttu-id="f0ff1-114">Solucionar problemas de rendimiento de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f0ff1-114">Troubleshoot BizTalk Server Performance</span></span>](../core/troubleshooting-biztalk-server-performance.md)  
  
-   [<span data-ttu-id="f0ff1-115">Solucionar problemas de adaptadores de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f0ff1-115">Troubleshoot BizTalk Server Adapters</span></span>](../core/troubleshooting-biztalk-server-adapters.md)  
  
-   [<span data-ttu-id="f0ff1-116">Solucionar problemas de soluciones EDI y AS2</span><span class="sxs-lookup"><span data-stu-id="f0ff1-116">Troubleshoot EDI and AS2 Solutions</span></span>](../core/troubleshooting-edi-and-as2-solutions.md)  
  
-   [<span data-ttu-id="f0ff1-117">Solucionar problemas de dependencias de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f0ff1-117">Troubleshoot BizTalk Server Dependencies</span></span>](../core/troubleshooting-biztalk-server-dependencies.md)  
  
-   [<span data-ttu-id="f0ff1-118">Solucionar problemas de configuración</span><span class="sxs-lookup"><span data-stu-id="f0ff1-118">Troubleshoot Configuration</span></span>](../core/troubleshooting-configuration.md)  
  
-   [<span data-ttu-id="f0ff1-119">Obtener un volcado de memoria de un proceso de BizTalk</span><span class="sxs-lookup"><span data-stu-id="f0ff1-119">Get a Memory Dump of a BizTalk Process</span></span>](../core/how-to-capture-a-memory-dump-of-a-biztalk-process.md)  
  
-   [<span data-ttu-id="f0ff1-120">Herramientas y utilidades</span><span class="sxs-lookup"><span data-stu-id="f0ff1-120">Tools and Utilities</span></span>](../core/tools-and-utilities-to-use-for-troubleshooting.md)  
  
-   [<span data-ttu-id="f0ff1-121">Solucionar problemas de errores de validación de mensaje con el contenido Hexadecimal de mensajes suspendidos</span><span class="sxs-lookup"><span data-stu-id="f0ff1-121">Troubleshoot Message Validation Failures using the Hexadecimal Contents of Suspended Messages</span></span>](../core/troubleshoot-message-validation-failures-using-the-hexadecimal-contents.md)

- [<span data-ttu-id="f0ff1-122">Eventos y errores</span><span class="sxs-lookup"><span data-stu-id="f0ff1-122">Events and Errors</span></span>](events-and-errors2.md)