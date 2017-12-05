---
title: "Paso 6: Configurar los servidores de orquestación de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestration server, configuring
- configuring, orchestration servers
ms.assetid: 1eb38fac-264d-4730-b16b-572dbb6fabd9
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e495be91cc80e072f58a1e8149feb64773f1e51
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="step-6-configuring-the-biztalk-orchestration-servers"></a><span data-ttu-id="6bc84-102">Paso 6: Configurar los servidores de orquestación de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="6bc84-102">Step 6: Configuring the BizTalk Orchestration Servers</span></span>
<span data-ttu-id="6bc84-103">Esta sección proporciona instrucciones sobre cómo configurar los servidores de orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="6bc84-103">This section provides guidelines on configuring the BizTalk Orchestration servers.</span></span>  
  
### <a name="to-configure-the-biztalk-orchestration-servers"></a><span data-ttu-id="6bc84-104">Para configurar los servidores de orquestación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="6bc84-104">To configure the BizTalk Orchestration servers</span></span>  
  
1.  <span data-ttu-id="6bc84-105">Habilitar el acceso de coordinador de transacciones distribuidas (DTC) de red mediante la selección de agregar o quitar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] componentes en la categoría de servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="6bc84-105">Enable Network Distributed Transaction Coordinator (DTC) access by selecting it from the Add/Remove [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Components under the Application Server category.</span></span> <span data-ttu-id="6bc84-106">Acceso de cliente de red DTC se habilitó en el [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] equipo en un paso anterior.</span><span class="sxs-lookup"><span data-stu-id="6bc84-106">Network DTC client access was enabled on the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] computer in an earlier step.</span></span> <span data-ttu-id="6bc84-107">Consulte los siguientes artículos de Knowledge Base en el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] sitio Web de ayuda y soporte técnico para obtener información acerca de cómo solucionar problemas de DTC:</span><span class="sxs-lookup"><span data-stu-id="6bc84-107">See the following Knowledge Base articles on the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Help and Support Web site for information about troubleshooting DTC issues:</span></span>  
  
    -   <span data-ttu-id="6bc84-108">Cómo To Troubleshoot MS DTC Firewall Issues, ubicado en [http://go.microsoft.com/fwlink/?linkid=48870](http://go.microsoft.com/fwlink/?linkid=48870).</span><span class="sxs-lookup"><span data-stu-id="6bc84-108">How To Troubleshoot MS DTC Firewall Issues, located at [http://go.microsoft.com/fwlink/?linkid=48870](http://go.microsoft.com/fwlink/?linkid=48870).</span></span>  
  
    -   <span data-ttu-id="6bc84-109">Cómo utilizar la herramienta DTCTester, ubicado en [http://go.microsoft.com/fwlink/?linkid=48871](http://go.microsoft.com/fwlink/?linkid=48871).</span><span class="sxs-lookup"><span data-stu-id="6bc84-109">How To Use DTCTester Tool, located at [http://go.microsoft.com/fwlink/?linkid=48871](http://go.microsoft.com/fwlink/?linkid=48871).</span></span>  
  
    -   <span data-ttu-id="6bc84-110">Si el DTC está detrás de un firewall, vea Configurar [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Coordinador de transacciones distribuidas (DTC) para el trabajo a través de un Firewall, ubicado en [http://go.microsoft.com/fwlink/?linkid=48872](http://go.microsoft.com/fwlink/?linkid=48872).</span><span class="sxs-lookup"><span data-stu-id="6bc84-110">If DTC is behind a firewall, see Configuring [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Distributed Transaction Coordinator (DTC) to Work Through a Firewall, located at [http://go.microsoft.com/fwlink/?linkid=48872](http://go.microsoft.com/fwlink/?linkid=48872).</span></span>  
  
2.  <span data-ttu-id="6bc84-111">Instalar requisitos previos de software adicional para el servidor BizTalk Server e instalar y configurar BizTalk Server, como se describe en [instalar y configurar BizTalk Server en los servidores de orquestación](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-orchestration-servers.md).</span><span class="sxs-lookup"><span data-stu-id="6bc84-111">Install additional software prerequisites for BizTalk Server, and install and configure BizTalk Server, as described in [Installing and Configuring BizTalk Server on the Orchestration Servers](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-orchestration-servers.md).</span></span>  
  
3.  <span data-ttu-id="6bc84-112">Instalar y configurar [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] tal y como se describe en instalar y [instalar y configurar el Acelerador de BizTalk para SWIFT en servidores de mensajería](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md).</span><span class="sxs-lookup"><span data-stu-id="6bc84-112">Install and configure [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] as described in Installing and [Installing and Configuring BizTalk Accelerator for SWIFT on Messaging Servers](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md).</span></span>  
  
 <span data-ttu-id="6bc84-113">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="6bc84-113">This section contains:</span></span>  
  
-   [<span data-ttu-id="6bc84-114">Instalación y configuración de BizTalk Server en los servidores de orquestación</span><span class="sxs-lookup"><span data-stu-id="6bc84-114">Installing and Configuring BizTalk Server on the Orchestration Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-orchestration-servers.md)  
  
-   [<span data-ttu-id="6bc84-115">Instalación y configuración del Acelerador de BizTalk para SWIFT en los servidores de orquestación</span><span class="sxs-lookup"><span data-stu-id="6bc84-115">Installing and Configuring BizTalk Accelerator for SWIFT on Orchestration Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/install-and-configure-biztalk-accelerator-for-swift-on-orchestration-servers.md)