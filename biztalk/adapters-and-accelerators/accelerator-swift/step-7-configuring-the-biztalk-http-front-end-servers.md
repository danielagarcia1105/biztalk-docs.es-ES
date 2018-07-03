---
title: 'Paso 7: Configurar los servidores front-end HTTP de BizTalk | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, HTTP servers
- HTTP server, configuring
ms.assetid: 6b7e0b48-bb20-42f4-84a5-092ff3a02741
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b6429ba6c753bac16874fd6fa81e13e91927b58
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989189"
---
# <a name="step-7-configuring-the-biztalk-http-front-end-servers"></a><span data-ttu-id="94a9e-102">Paso 7: Configurar los servidores front-end HTTP de BizTalk</span><span class="sxs-lookup"><span data-stu-id="94a9e-102">Step 7: Configuring the BizTalk HTTP Front-End Servers</span></span>
<span data-ttu-id="94a9e-103">Esta sección proporciona instrucciones sobre cómo configurar los servidores Web de su [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] implementación.</span><span class="sxs-lookup"><span data-stu-id="94a9e-103">This section provides guidelines on configuring the Web servers in your [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] deployment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="94a9e-104">En la implementación de equipo único, este equipo es el mismo equipo que el que realiza la mensajería y procesamiento.</span><span class="sxs-lookup"><span data-stu-id="94a9e-104">In the single-computer deployment, this computer is the same computer as the one that does the messaging and processing.</span></span>  
  
### <a name="to-configure-the-biztalk-http-front-end-servers"></a><span data-ttu-id="94a9e-105">Para configurar los servidores front-end HTTP de BizTalk</span><span class="sxs-lookup"><span data-stu-id="94a9e-105">To configure the BizTalk HTTP front-end servers</span></span>  
  
1. <span data-ttu-id="94a9e-106">Instalar Internet Information Services (IIS) y ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="94a9e-106">Install Internet Information Services (IIS) and ASP.NET.</span></span>  
  
2. <span data-ttu-id="94a9e-107">Abra el Administrador de IIS y seleccione **extensiones de servicio Web**.</span><span class="sxs-lookup"><span data-stu-id="94a9e-107">Open IIS Manager and select **Web Service Extensions**.</span></span> <span data-ttu-id="94a9e-108">Asegúrese de que la versión 1.1 de ASP.NET y ASP.NET 2.0 se establecen en **permitido**.</span><span class="sxs-lookup"><span data-stu-id="94a9e-108">Ensure that ASP.NET v1.1 and ASP.NET v2.0 are set to **Allowed**.</span></span>  
  
3. <span data-ttu-id="94a9e-109">Asegúrese de que el **Message Queue Server** service (MSMQ) con **compatibilidad con enrutamiento** se instala desde Agregar o quitar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] componentes en la aplicación de servidor/Message Queue Server.</span><span class="sxs-lookup"><span data-stu-id="94a9e-109">Ensure that the **Message Queuing** service (MSMQ) with **Routing Support** is installed from the Add/Remove [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Components under Application Server/Message Queuing.</span></span>  
  
4. <span data-ttu-id="94a9e-110">Asegúrese de que está habilitado el acceso de red DTC en Agregar o quitar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] componentes en la categoría de servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="94a9e-110">Ensure that Network DTC access is enabled in the Add/Remove [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Components under the Application Server category.</span></span> <span data-ttu-id="94a9e-111">Se ha habilitado el acceso de cliente de red DTC en el [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] equipo en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="94a9e-111">Network DTC client access was enabled on the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] computer in an earlier step.</span></span>  
  
5. <span data-ttu-id="94a9e-112">Implementar el protocolo de capa de Sockets seguros (SSL) en la implementación, como se describe en [compatibilidad con capa de Sockets seguros (SSL)](../../adapters-and-accelerators/accelerator-swift/supporting-secure-sockets-layer-ssl.md).</span><span class="sxs-lookup"><span data-stu-id="94a9e-112">Implement the Secure Sockets Layer (SSL) protocol in your deployment, as described in [Supporting Secure Sockets Layer (SSL)](../../adapters-and-accelerators/accelerator-swift/supporting-secure-sockets-layer-ssl.md).</span></span>  
  
6. <span data-ttu-id="94a9e-113">Instalar y configurar Windows SharePoint Services 3.0 SP1.</span><span class="sxs-lookup"><span data-stu-id="94a9e-113">Install and configure Windows SharePoint Services 3.0 SP1.</span></span>  
  
7. <span data-ttu-id="94a9e-114">Instalar y configurar [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] como se describe en [instalar y configurar el Acelerador de BizTalk para SWIFT en los servidores front-end HTTP](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-http-front-end-servers.md).</span><span class="sxs-lookup"><span data-stu-id="94a9e-114">Install and configure [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] as described in [Installing and Configuring BizTalk Accelerator for SWIFT on HTTP Front-End Servers](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-http-front-end-servers.md).</span></span>  
  
   <span data-ttu-id="94a9e-115">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="94a9e-115">This section contains:</span></span>  
  
-   [<span data-ttu-id="94a9e-116">Admitir la capa de sockets seguros (SSL)</span><span class="sxs-lookup"><span data-stu-id="94a9e-116">Supporting Secure Sockets Layer (SSL)</span></span>](../../adapters-and-accelerators/accelerator-swift/supporting-secure-sockets-layer-ssl.md)  
  
-   [<span data-ttu-id="94a9e-117">Instalación y configuración de servidores front-end HTTP de BizTalk</span><span class="sxs-lookup"><span data-stu-id="94a9e-117">Installing and Configuring BizTalk HTTP Front-End Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-http-front-end-servers.md)  
  
-   [<span data-ttu-id="94a9e-118">Instalación y configuración del Acelerador de BizTalk para SWIFT en los servidores front-end HTTP</span><span class="sxs-lookup"><span data-stu-id="94a9e-118">Installing and Configuring BizTalk Accelerator for SWIFT on HTTP Front-End Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/install-and-configure-biztalk-accelerator-for-swift-on-http-front-end-servers.md)