---
title: 'Paso 7: Configurar los servidores front-end HTTP de BizTalk | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, HTTP servers
- HTTP server, configuring
ms.assetid: 6b7e0b48-bb20-42f4-84a5-092ff3a02741
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5840099816149265711744373e08d3a9a9d91cd0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-7-configuring-the-biztalk-http-front-end-servers"></a><span data-ttu-id="4928d-102">Paso 7: Configurar los servidores front-end HTTP de BizTalk</span><span class="sxs-lookup"><span data-stu-id="4928d-102">Step 7: Configuring the BizTalk HTTP Front-End Servers</span></span>
<span data-ttu-id="4928d-103">Esta sección proporciona instrucciones sobre cómo configurar los servidores Web de su [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] implementación.</span><span class="sxs-lookup"><span data-stu-id="4928d-103">This section provides guidelines on configuring the Web servers in your [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] deployment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4928d-104">En la implementación de equipo único, este equipo es el mismo equipo que el que realiza la mensajería y procesamiento.</span><span class="sxs-lookup"><span data-stu-id="4928d-104">In the single-computer deployment, this computer is the same computer as the one that does the messaging and processing.</span></span>  
  
### <a name="to-configure-the-biztalk-http-front-end-servers"></a><span data-ttu-id="4928d-105">Para configurar los servidores front-end HTTP de BizTalk</span><span class="sxs-lookup"><span data-stu-id="4928d-105">To configure the BizTalk HTTP front-end servers</span></span>  
  
1.  <span data-ttu-id="4928d-106">Instale Internet Information Services (IIS) y ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="4928d-106">Install Internet Information Services (IIS) and ASP.NET.</span></span>  
  
2.  <span data-ttu-id="4928d-107">Abra el Administrador de IIS y seleccione **extensiones de servicio Web**.</span><span class="sxs-lookup"><span data-stu-id="4928d-107">Open IIS Manager and select **Web Service Extensions**.</span></span> <span data-ttu-id="4928d-108">Asegúrese de que ASP.NET versión 1.1 y versión 2.0 ASP.NET se establecen en **permitido**.</span><span class="sxs-lookup"><span data-stu-id="4928d-108">Ensure that ASP.NET v1.1 and ASP.NET v2.0 are set to **Allowed**.</span></span>  
  
3.  <span data-ttu-id="4928d-109">Asegúrese de que el **Message Queue Server** service (MSMQ) con **compatibilidad con enrutamiento** se instala desde Agregar o quitar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] componentes de aplicación de servidor/Message Queue Server.</span><span class="sxs-lookup"><span data-stu-id="4928d-109">Ensure that the **Message Queuing** service (MSMQ) with **Routing Support** is installed from the Add/Remove [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Components under Application Server/Message Queuing.</span></span>  
  
4.  <span data-ttu-id="4928d-110">Asegúrese de que está habilitado el acceso de red DTC en Agregar o quitar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] componentes en la categoría de servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="4928d-110">Ensure that Network DTC access is enabled in the Add/Remove [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Components under the Application Server category.</span></span> <span data-ttu-id="4928d-111">Acceso de cliente de red DTC se habilitó en el [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] equipo en un paso anterior.</span><span class="sxs-lookup"><span data-stu-id="4928d-111">Network DTC client access was enabled on the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] computer in an earlier step.</span></span>  
  
5.  <span data-ttu-id="4928d-112">Implementar el protocolo de capa de Sockets seguros (SSL) en la implementación, como se describe en [compatibilidad con capa de Sockets seguros (SSL)](../../adapters-and-accelerators/accelerator-swift/supporting-secure-sockets-layer-ssl.md).</span><span class="sxs-lookup"><span data-stu-id="4928d-112">Implement the Secure Sockets Layer (SSL) protocol in your deployment, as described in [Supporting Secure Sockets Layer (SSL)](../../adapters-and-accelerators/accelerator-swift/supporting-secure-sockets-layer-ssl.md).</span></span>  
  
6.  <span data-ttu-id="4928d-113">Instalar y configurar Windows SharePoint Services 3.0 SP1.</span><span class="sxs-lookup"><span data-stu-id="4928d-113">Install and configure Windows SharePoint Services 3.0 SP1.</span></span>  
  
7.  <span data-ttu-id="4928d-114">Instalar y configurar [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] tal y como se describe en [instalar y configurar el Acelerador de BizTalk para SWIFT en los servidores front-end HTTP](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-http-front-end-servers.md).</span><span class="sxs-lookup"><span data-stu-id="4928d-114">Install and configure [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] as described in [Installing and Configuring BizTalk Accelerator for SWIFT on HTTP Front-End Servers](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-http-front-end-servers.md).</span></span>  
  
 <span data-ttu-id="4928d-115">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="4928d-115">This section contains:</span></span>  
  
-   [<span data-ttu-id="4928d-116">Compatibilidad con capa de Sockets seguros (SSL)</span><span class="sxs-lookup"><span data-stu-id="4928d-116">Supporting Secure Sockets Layer (SSL)</span></span>](../../adapters-and-accelerators/accelerator-swift/supporting-secure-sockets-layer-ssl.md)  
  
-   [<span data-ttu-id="4928d-117">Instalar y configurar servidores front-end HTTP de BizTalk</span><span class="sxs-lookup"><span data-stu-id="4928d-117">Installing and Configuring BizTalk HTTP Front-End Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-http-front-end-servers.md)  
  
-   [<span data-ttu-id="4928d-118">Instalar y configurar el Acelerador de BizTalk para SWIFT en servidores front-end HTTP</span><span class="sxs-lookup"><span data-stu-id="4928d-118">Installing and Configuring BizTalk Accelerator for SWIFT on HTTP Front-End Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/install-and-configure-biztalk-accelerator-for-swift-on-http-front-end-servers.md)