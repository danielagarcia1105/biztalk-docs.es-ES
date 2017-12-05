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
ms.openlocfilehash: 8fc3da3798e78e9b5fcf1ce09180c43e10417997
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="deploying-your-servers"></a><span data-ttu-id="482be-102">Implementar los servidores</span><span class="sxs-lookup"><span data-stu-id="482be-102">Deploying Your Servers</span></span>
<span data-ttu-id="482be-103">Esta sección proporciona instrucciones para configurar cada uno de los servidores de su [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] implementación.</span><span class="sxs-lookup"><span data-stu-id="482be-103">This section provides instructions for configuring each of the servers in your [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] deployment.</span></span> <span data-ttu-id="482be-104">Después de configurar la red al implementar el software en cada servidor mediante los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="482be-104">After you configure the network you deploy the software on each server by using the following steps.</span></span>  
  
 <span data-ttu-id="482be-105">Antes de iniciar la implementación del servidor, asegúrese de leer y realizar los pasos descritos en la preparación de la implementación [preparar para la implementación](../../adapters-and-accelerators/accelerator-swift/preparing-for-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="482be-105">Before starting server deployment, make sure that you read and perform the deployment preparation steps described in [Preparing for Deployment](../../adapters-and-accelerators/accelerator-swift/preparing-for-deployment.md).</span></span> <span data-ttu-id="482be-106">Si no se adhiere a las instrucciones en la sección anterior podría resultado en una configuración desconocida y no compatible de la implementación (y podrían producir un error en pasos posteriores).</span><span class="sxs-lookup"><span data-stu-id="482be-106">Failing to adhere to the prescriptive guidance in the previous section might result in an unknown and unsupported configuration of the deployment (and subsequent steps might fail).</span></span>  
  
 <span data-ttu-id="482be-107">Para obtener más información, consulte a la Guía de implementación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="482be-107">For more information, see the BizTalk Server Deployment Guide.</span></span>  
  
 <span data-ttu-id="482be-108">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="482be-108">This section contains:</span></span>  
  
-   [<span data-ttu-id="482be-109">Paso 1: Instalación de la plataforma base</span><span class="sxs-lookup"><span data-stu-id="482be-109">Step 1: Installing the Base Platform</span></span>](../../adapters-and-accelerators/accelerator-swift/step-1-installing-the-base-platform.md)  
  
-   [<span data-ttu-id="482be-110">Paso 2: Configuración de NLB en los servidores</span><span class="sxs-lookup"><span data-stu-id="482be-110">Step 2: Configuring NLB on the Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/step-2-configuring-nlb-on-the-servers.md)  
  
-   [<span data-ttu-id="482be-111">Paso 3: Configuración del controlador de dominio</span><span class="sxs-lookup"><span data-stu-id="482be-111">Step 3: Configuring the Domain Controller</span></span>](../../adapters-and-accelerators/accelerator-swift/step-3-configuring-the-domain-controller.md)  
  
-   [<span data-ttu-id="482be-112">Paso 4: Configuración de los servidores de base de datos</span><span class="sxs-lookup"><span data-stu-id="482be-112">Step 4: Configuring the Database Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/step-4-configuring-the-database-servers.md)  
  
-   [<span data-ttu-id="482be-113">Paso 5: Configuración de los servidores de mensajería de BizTalk</span><span class="sxs-lookup"><span data-stu-id="482be-113">Step 5: Configuring the BizTalk Messaging Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/step-5-configuring-the-biztalk-messaging-servers.md)  
  
-   [<span data-ttu-id="482be-114">Paso 6: Configuración de los servidores de orquestación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="482be-114">Step 6: Configuring the BizTalk Orchestration Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/step-6-configuring-the-biztalk-orchestration-servers.md)  
  
-   [<span data-ttu-id="482be-115">Paso 7: Configuración de los servidores front-end HTTP de BizTalk</span><span class="sxs-lookup"><span data-stu-id="482be-115">Step 7: Configuring the BizTalk HTTP Front-End Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/step-7-configuring-the-biztalk-http-front-end-servers.md)  
  
-   [<span data-ttu-id="482be-116">Paso 8: Cambios posteriores a la configuración</span><span class="sxs-lookup"><span data-stu-id="482be-116">Step 8: Post-Configuration Changes</span></span>](../../adapters-and-accelerators/accelerator-swift/step-8-post-configuration-changes.md)