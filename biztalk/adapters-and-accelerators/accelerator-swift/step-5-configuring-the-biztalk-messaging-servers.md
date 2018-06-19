---
title: 'Paso 5: Configurar lo servidores de mensajería de BizTalk | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, BizTalk Messaging servers
- BizTalk Messaging servers, configuring
ms.assetid: 598d336d-b006-4d02-9249-e9d6d9b6b7b5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e1aea1187417b77071f0821547869a5b84549c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214012"
---
# <a name="step-5-configuring-the-biztalk-messaging-servers"></a><span data-ttu-id="6be8f-102">Paso 5: Configurar lo servidores de mensajería de BizTalk</span><span class="sxs-lookup"><span data-stu-id="6be8f-102">Step 5: Configuring the BizTalk Messaging Servers</span></span>
<span data-ttu-id="6be8f-103">Esta sección proporciona instrucciones sobre cómo configurar los servidores de mensajería de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="6be8f-103">This section provides guidelines on configuring the BizTalk Messaging servers.</span></span>  
  
### <a name="to-configure-the-biztalk-messaging-servers"></a><span data-ttu-id="6be8f-104">Para configurar los servidores de mensajería de BizTalk</span><span class="sxs-lookup"><span data-stu-id="6be8f-104">To configure the BizTalk Messaging servers</span></span>  
  
1.  <span data-ttu-id="6be8f-105">Habilitar el acceso de coordinador de transacciones distribuidas (DTC) de red mediante la selección de agregar o quitar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] componentes en la categoría de servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="6be8f-105">Enable Network Distributed Transaction Coordinator (DTC) access by selecting it from the Add/Remove [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Components under the Application Server category.</span></span> <span data-ttu-id="6be8f-106">Acceso de cliente de red DTC se habilitó en el [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] equipo en un paso anterior.</span><span class="sxs-lookup"><span data-stu-id="6be8f-106">Network DTC client access was enabled on the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] computer in an earlier step.</span></span> <span data-ttu-id="6be8f-107">Consulte los siguientes artículos de Knowledge Base en el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] sitio Web de ayuda y soporte técnico para obtener información acerca de cómo solucionar problemas de DTC:</span><span class="sxs-lookup"><span data-stu-id="6be8f-107">See the following Knowledge Base articles on the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Help and Support Web site for information about troubleshooting DTC issues:</span></span>  
  
    -   <span data-ttu-id="6be8f-108">Cómo To Troubleshoot MS DTC Firewall Issues, ubicado en [http://go.microsoft.com/fwlink/?linkid=48870](http://go.microsoft.com/fwlink/?linkid=48870).</span><span class="sxs-lookup"><span data-stu-id="6be8f-108">How To Troubleshoot MS DTC Firewall Issues, located at [http://go.microsoft.com/fwlink/?linkid=48870](http://go.microsoft.com/fwlink/?linkid=48870).</span></span>  
  
    -   <span data-ttu-id="6be8f-109">Cómo utilizar la herramienta DTCTester, ubicado en [http://go.microsoft.com/fwlink/?linkid=48871](http://go.microsoft.com/fwlink/?linkid=48871).</span><span class="sxs-lookup"><span data-stu-id="6be8f-109">How To Use DTCTester Tool, located at [http://go.microsoft.com/fwlink/?linkid=48871](http://go.microsoft.com/fwlink/?linkid=48871).</span></span>  
  
    -   <span data-ttu-id="6be8f-110">Si el DTC está detrás de un firewall, vea "configurar [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Coordinador de transacciones distribuidas (DTC) to Work Through un Firewall", que se encuentra en [http://go.microsoft.com/fwlink/?linkid=48872](http://go.microsoft.com/fwlink/?linkid=48872).</span><span class="sxs-lookup"><span data-stu-id="6be8f-110">If DTC is behind a firewall, see "Configuring [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Distributed Transaction Coordinator (DTC) to Work Through a Firewall", located at [http://go.microsoft.com/fwlink/?linkid=48872](http://go.microsoft.com/fwlink/?linkid=48872).</span></span>  
  
2.  <span data-ttu-id="6be8f-111">Configurar y comprobar el equilibrio de carga de red en el BizTalk reciben servidores como se describe en [paso 2: configurar NLB en los servidores](../../adapters-and-accelerators/accelerator-swift/step-2-configuring-nlb-on-the-servers.md).</span><span class="sxs-lookup"><span data-stu-id="6be8f-111">Configure and verify Network Load Balancing on the BizTalk receive servers as described in [Step 2: Configuring NLB on the Servers](../../adapters-and-accelerators/accelerator-swift/step-2-configuring-nlb-on-the-servers.md).</span></span>  
  
3.  <span data-ttu-id="6be8f-112">Instalar y configurar [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] tal y como se describe en [instalar y configurar el Acelerador de BizTalk para SWIFT en servidores de mensajería](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md).</span><span class="sxs-lookup"><span data-stu-id="6be8f-112">Install and configure [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] as described in [Installing and Configuring BizTalk Accelerator for SWIFT on Messaging Servers](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md).</span></span>  
  
 <span data-ttu-id="6be8f-113">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="6be8f-113">This section contains:</span></span>  
  
-   [<span data-ttu-id="6be8f-114">Instalar y configurar el servidor BizTalk Server en el servidor de mensajería</span><span class="sxs-lookup"><span data-stu-id="6be8f-114">Installing and Configuring BizTalk Server on the Messaging Server</span></span>](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-messaging-server.md)  
  
-   [<span data-ttu-id="6be8f-115">Instalar y configurar el Acelerador de BizTalk para SWIFT en servidores de mensajería</span><span class="sxs-lookup"><span data-stu-id="6be8f-115">Installing and Configuring BizTalk Accelerator for SWIFT on Messaging Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md)