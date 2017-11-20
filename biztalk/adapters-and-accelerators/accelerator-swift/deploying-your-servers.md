---
title: Implementar los servidores | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, servers
- servers, deploying
ms.assetid: 6036e42b-59b8-4092-addd-288e9c4b91d6
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0c158e3c14a5a695e7c1e042cd3dfb0277260b7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-your-servers"></a><span data-ttu-id="63b05-102">Implementar los servidores</span><span class="sxs-lookup"><span data-stu-id="63b05-102">Deploying Your Servers</span></span>
<span data-ttu-id="63b05-103">Esta sección proporciona instrucciones para configurar cada uno de los servidores de su [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] implementación.</span><span class="sxs-lookup"><span data-stu-id="63b05-103">This section provides instructions for configuring each of the servers in your [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] deployment.</span></span> <span data-ttu-id="63b05-104">Después de configurar la red al implementar el software en cada servidor mediante los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="63b05-104">After you configure the network you deploy the software on each server by using the following steps.</span></span>  
  
 <span data-ttu-id="63b05-105">Antes de iniciar la implementación del servidor, asegúrese de leer y realizar los pasos descritos en la preparación de la implementación [preparar para la implementación](../../adapters-and-accelerators/accelerator-swift/preparing-for-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="63b05-105">Before starting server deployment, make sure that you read and perform the deployment preparation steps described in [Preparing for Deployment](../../adapters-and-accelerators/accelerator-swift/preparing-for-deployment.md).</span></span> <span data-ttu-id="63b05-106">Si no se adhiere a las instrucciones en la sección anterior podría resultado en una configuración desconocida y no compatible de la implementación (y podrían producir un error en pasos posteriores).</span><span class="sxs-lookup"><span data-stu-id="63b05-106">Failing to adhere to the prescriptive guidance in the previous section might result in an unknown and unsupported configuration of the deployment (and subsequent steps might fail).</span></span>  
  
 <span data-ttu-id="63b05-107">Para obtener más información, consulte el [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Guía de implementación.</span><span class="sxs-lookup"><span data-stu-id="63b05-107">For more information, see the [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Deployment Guide.</span></span>  
  
 <span data-ttu-id="63b05-108">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="63b05-108">This section contains:</span></span>  
  
-   [<span data-ttu-id="63b05-109">Paso 1: Instalar la plataforma Base</span><span class="sxs-lookup"><span data-stu-id="63b05-109">Step 1: Installing the Base Platform</span></span>](../../adapters-and-accelerators/accelerator-swift/step-1-installing-the-base-platform.md)  
  
-   [<span data-ttu-id="63b05-110">Paso 2: Configurar NLB en los servidores</span><span class="sxs-lookup"><span data-stu-id="63b05-110">Step 2: Configuring NLB on the Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/step-2-configuring-nlb-on-the-servers.md)  
  
-   [<span data-ttu-id="63b05-111">Paso 3: Configurar el controlador de dominio</span><span class="sxs-lookup"><span data-stu-id="63b05-111">Step 3: Configuring the Domain Controller</span></span>](../../adapters-and-accelerators/accelerator-swift/step-3-configuring-the-domain-controller.md)  
  
-   [<span data-ttu-id="63b05-112">Paso 4: Configurar los servidores de base de datos</span><span class="sxs-lookup"><span data-stu-id="63b05-112">Step 4: Configuring the Database Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/step-4-configuring-the-database-servers.md)  
  
-   [<span data-ttu-id="63b05-113">Paso 5: Configurar lo servidores de mensajería de BizTalk</span><span class="sxs-lookup"><span data-stu-id="63b05-113">Step 5: Configuring the BizTalk Messaging Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/step-5-configuring-the-biztalk-messaging-servers.md)  
  
-   [<span data-ttu-id="63b05-114">Paso 6: Configurar los servidores de orquestación de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="63b05-114">Step 6: Configuring the BizTalk Orchestration Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/step-6-configuring-the-biztalk-orchestration-servers.md)  
  
-   [<span data-ttu-id="63b05-115">Paso 7: Configurar los servidores front-end HTTP de BizTalk</span><span class="sxs-lookup"><span data-stu-id="63b05-115">Step 7: Configuring the BizTalk HTTP Front-End Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/step-7-configuring-the-biztalk-http-front-end-servers.md)  
  
-   [<span data-ttu-id="63b05-116">Paso 8: Cambios de configuración posterior a la</span><span class="sxs-lookup"><span data-stu-id="63b05-116">Step 8: Post-Configuration Changes</span></span>](../../adapters-and-accelerators/accelerator-swift/step-8-post-configuration-changes.md)