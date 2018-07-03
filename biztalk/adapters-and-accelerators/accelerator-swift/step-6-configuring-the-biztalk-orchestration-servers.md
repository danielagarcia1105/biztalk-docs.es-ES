---
title: 'Paso 6: Configuración de los servidores de orquestación de BizTalk | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestration server, configuring
- configuring, orchestration servers
ms.assetid: 1eb38fac-264d-4730-b16b-572dbb6fabd9
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51ca589433d945dfdc5acac0602151b9f7cf6374
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991725"
---
# <a name="step-6-configuring-the-biztalk-orchestration-servers"></a><span data-ttu-id="46ea8-102">Paso 6: Configuración de los servidores de orquestación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="46ea8-102">Step 6: Configuring the BizTalk Orchestration Servers</span></span>
<span data-ttu-id="46ea8-103">Esta sección proporciona instrucciones sobre cómo configurar los servidores de orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="46ea8-103">This section provides guidelines on configuring the BizTalk Orchestration servers.</span></span>  
  
### <a name="to-configure-the-biztalk-orchestration-servers"></a><span data-ttu-id="46ea8-104">Para configurar los servidores de orquestación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="46ea8-104">To configure the BizTalk Orchestration servers</span></span>  
  
1. <span data-ttu-id="46ea8-105">Habilitar el acceso de coordinador de transacciones distribuidas (DTC) de red seleccionando desde Agregar o quitar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] componentes en la categoría de servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="46ea8-105">Enable Network Distributed Transaction Coordinator (DTC) access by selecting it from the Add/Remove [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Components under the Application Server category.</span></span> <span data-ttu-id="46ea8-106">Se ha habilitado el acceso de cliente de red DTC en el [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] equipo en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="46ea8-106">Network DTC client access was enabled on the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] computer in an earlier step.</span></span> <span data-ttu-id="46ea8-107">Consulte los siguientes artículos de Knowledge Base en el sitio Web de soporte técnico y Microsoft Help para obtener información acerca de cómo solucionar problemas de DTC:</span><span class="sxs-lookup"><span data-stu-id="46ea8-107">See the following Knowledge Base articles on the Microsoft Help and Support Web site for information about troubleshooting DTC issues:</span></span>  
  
   - <span data-ttu-id="46ea8-108">Cómo To Troubleshoot MS DTC Firewall Issues, ubicado en [ http://go.microsoft.com/fwlink/?linkid=48870 ](http://go.microsoft.com/fwlink/?linkid=48870).</span><span class="sxs-lookup"><span data-stu-id="46ea8-108">How To Troubleshoot MS DTC Firewall Issues, located at [http://go.microsoft.com/fwlink/?linkid=48870](http://go.microsoft.com/fwlink/?linkid=48870).</span></span>  
  
   - <span data-ttu-id="46ea8-109">Cómo utilizar la herramienta DTCTester, ubicado en [ http://go.microsoft.com/fwlink/?linkid=48871 ](http://go.microsoft.com/fwlink/?linkid=48871).</span><span class="sxs-lookup"><span data-stu-id="46ea8-109">How To Use DTCTester Tool, located at [http://go.microsoft.com/fwlink/?linkid=48871](http://go.microsoft.com/fwlink/?linkid=48871).</span></span>  
  
   - <span data-ttu-id="46ea8-110">Si DTC está detrás de un firewall, consulte Configurar Microsoft distribuidas Coordinador de transacciones (DTC) para el trabajo a través de un Firewall, ubicado en [ http://go.microsoft.com/fwlink/?linkid=48872 ](http://go.microsoft.com/fwlink/?linkid=48872).</span><span class="sxs-lookup"><span data-stu-id="46ea8-110">If DTC is behind a firewall, see Configuring Microsoft Distributed Transaction Coordinator (DTC) to Work Through a Firewall, located at [http://go.microsoft.com/fwlink/?linkid=48872](http://go.microsoft.com/fwlink/?linkid=48872).</span></span>  
  
2. <span data-ttu-id="46ea8-111">Instalar requisitos previos de software adicional para BizTalk Server e instalar y configurar BizTalk Server, como se describe en [instalar y configurar BizTalk Server en los servidores de orquestación](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-orchestration-servers.md).</span><span class="sxs-lookup"><span data-stu-id="46ea8-111">Install additional software prerequisites for BizTalk Server, and install and configure BizTalk Server, as described in [Installing and Configuring BizTalk Server on the Orchestration Servers](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-orchestration-servers.md).</span></span>  
  
3. <span data-ttu-id="46ea8-112">Instalar y configurar [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] como se describe en la instalación y [instalar y configurar el Acelerador de BizTalk para SWIFT en servidores de mensajería](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md).</span><span class="sxs-lookup"><span data-stu-id="46ea8-112">Install and configure [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] as described in Installing and [Installing and Configuring BizTalk Accelerator for SWIFT on Messaging Servers](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md).</span></span>  
  
   <span data-ttu-id="46ea8-113">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="46ea8-113">This section contains:</span></span>  
  
-   [<span data-ttu-id="46ea8-114">Instalación y configuración de BizTalk Server en los servidores de orquestación</span><span class="sxs-lookup"><span data-stu-id="46ea8-114">Installing and Configuring BizTalk Server on the Orchestration Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-orchestration-servers.md)  
  
-   [<span data-ttu-id="46ea8-115">Instalación y configuración del Acelerador de BizTalk para SWIFT en los servidores de orquestación</span><span class="sxs-lookup"><span data-stu-id="46ea8-115">Installing and Configuring BizTalk Accelerator for SWIFT on Orchestration Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/install-and-configure-biztalk-accelerator-for-swift-on-orchestration-servers.md)