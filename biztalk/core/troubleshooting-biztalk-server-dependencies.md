---
title: Solución de problemas de dependencias de BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 677b7ef3-9a91-4f1e-bfc5-926bfab23a0f
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a75cf1986c9c7bf66aa48370704ca3569d0db87
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279252"
---
# <a name="troubleshooting-biztalk-server-dependencies"></a><span data-ttu-id="546d4-102">Solucionar problemas de dependencias de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="546d4-102">Troubleshooting BizTalk Server Dependencies</span></span>
<span data-ttu-id="546d4-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] hace uso masivo de varios otros productos de Microsoft para operaciones de tiempo de ejecución y tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="546d4-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] makes extensive use of several other Microsoft products for design time and run-time operations.</span></span> <span data-ttu-id="546d4-104">Esta sección incluye pautas para la solución de problemas que pueden producirse en estas tecnologías subyacentes.</span><span class="sxs-lookup"><span data-stu-id="546d4-104">This section contains troubleshooting guidelines for resolving problems that can occur in these underlying technologies.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="546d4-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="546d4-105">In This Section</span></span>  
  
-   [<span data-ttu-id="546d4-106">Solucionar problemas con MSDTC</span><span class="sxs-lookup"><span data-stu-id="546d4-106">Troubleshooting Problems with MSDTC</span></span>](../core/troubleshooting-problems-with-msdtc.md)  
  
-   [<span data-ttu-id="546d4-107">Solución de problemas de certificados</span><span class="sxs-lookup"><span data-stu-id="546d4-107">Troubleshooting Certificates</span></span>](../core/troubleshooting-certificates.md)  
  
-   [<span data-ttu-id="546d4-108">Solución de problemas de Enterprise Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="546d4-108">Troubleshooting Enterprise Single Sign-On</span></span>](../core/troubleshooting-enterprise-single-sign-on.md)  
  
-   [<span data-ttu-id="546d4-109">Solucionar problemas de SQL Server</span><span class="sxs-lookup"><span data-stu-id="546d4-109">Troubleshooting SQL Server</span></span>](../core/troubleshooting-sql-server.md)  
  
-   [<span data-ttu-id="546d4-110">Solución de problemas de servicios Web</span><span class="sxs-lookup"><span data-stu-id="546d4-110">Troubleshooting Web Services</span></span>](../core/troubleshooting-web-services.md)  
  
-   [<span data-ttu-id="546d4-111">Solución de problemas de un clúster de servidores de Windows</span><span class="sxs-lookup"><span data-stu-id="546d4-111">Troubleshooting a Windows Server Cluster</span></span>](../core/troubleshooting-a-windows-server-cluster.md)  
  
-   [<span data-ttu-id="546d4-112">Solución de problemas de servicios de Internet Information Server</span><span class="sxs-lookup"><span data-stu-id="546d4-112">Troubleshooting Internet Information Services</span></span>](../core/troubleshooting-internet-information-services.md)  
  
-   [<span data-ttu-id="546d4-113">Solucionar problemas de Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="546d4-113">Troubleshooting Windows SharePoint Services</span></span>](../core/troubleshooting-windows-sharepoint-services.md)