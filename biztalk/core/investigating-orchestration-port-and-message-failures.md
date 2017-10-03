---
title: "Investigación de orquestación, puerto y mensaje errores | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Administration Console [BizTalk Server], Group Hub page
- orchestrations, errors
- errors, ports
- errors, orchestrations
- Group Hub page [Administration Console]
- ports, errors
- MessageBox database, accessing data
- errors, messages
- messages, errors
- data, MessageBox database
ms.assetid: 50b0d272-2d48-4e0f-82ce-6ecc7a65b064
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94417135f707d77377686745e35e6fb1f02087b9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="investigating-orchestration-port-and-message-failures"></a><span data-ttu-id="cf4a6-102">Investigar errores de mensaje, orquestación y puerto</span><span class="sxs-lookup"><span data-stu-id="cf4a6-102">Investigating Orchestration, Port, and Message Failures</span></span>
<span data-ttu-id="cf4a6-103">Puede utilizar la página Concentrador de grupo de la consola de administración de BizTalk Server para investigar errores de mensaje, orquestación y puerto.</span><span class="sxs-lookup"><span data-stu-id="cf4a6-103">You can use the Group Hub page in the BizTalk Server Administration Console to investigate orchestration, port, and message failures.</span></span> <span data-ttu-id="cf4a6-104">La página Concentrador de grupo proporciona acceso al estado actual en tiempo real del sistema, que obtiene acceso a los datos de la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="cf4a6-104">The Group Hub page provides access to the current real-time state of the system, accessing data in the MessageBox database.</span></span> <span data-ttu-id="cf4a6-105">Puede ver todas las instancias de servicio, como orquestaciones, puertos y mensajería, junto con sus mensajes asociados.</span><span class="sxs-lookup"><span data-stu-id="cf4a6-105">You can view all service instances such as orchestrations, ports, and messaging, along with their associated messages.</span></span> <span data-ttu-id="cf4a6-106">Con la página Concentrador de grupo puede:</span><span class="sxs-lookup"><span data-stu-id="cf4a6-106">Using the Group Hub page you can:</span></span>  
  
-   <span data-ttu-id="cf4a6-107">Ver las instancias de servicio que se estén ejecutando en ese momento, como orquestaciones y mensajería, y sus mensajes asociados.</span><span class="sxs-lookup"><span data-stu-id="cf4a6-107">See currently running service instances such as orchestrations and messaging, and their associated messages.</span></span>  
  
-   <span data-ttu-id="cf4a6-108">Buscar una vista de los datos actuales y el estado en tiempo real del sistema en la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="cf4a6-108">Look into the MessageBox database for a view of the current data and the real-time state of the system.</span></span>  
  
-   <span data-ttu-id="cf4a6-109">Suspender, finalizar y reanudar instancias de servicio.</span><span class="sxs-lookup"><span data-stu-id="cf4a6-109">Suspend, terminate, and resume service instances.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cf4a6-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="cf4a6-110">In This Section</span></span>  
  
-   [<span data-ttu-id="cf4a6-111">Errores de orquestación</span><span class="sxs-lookup"><span data-stu-id="cf4a6-111">Orchestration Failures</span></span>](../core/orchestration-failures.md)  
  
-   [<span data-ttu-id="cf4a6-112">Tipos de errores de mensaje</span><span class="sxs-lookup"><span data-stu-id="cf4a6-112">Types of Message Failures</span></span>](../core/types-of-message-failures.md)  
  
-   [<span data-ttu-id="cf4a6-113">Cómo suspender puertos o instancias de orquestación</span><span class="sxs-lookup"><span data-stu-id="cf4a6-113">How to Suspend Orchestration Instances or Ports</span></span>](../core/how-to-suspend-orchestration-instances-or-ports.md)  
  
-   [<span data-ttu-id="cf4a6-114">Cómo finalizar instancias de orquestación suspendidas</span><span class="sxs-lookup"><span data-stu-id="cf4a6-114">How to Terminate Suspended Orchestration Instances</span></span>](../core/how-to-terminate-suspended-orchestration-instances.md)  
  
-   [<span data-ttu-id="cf4a6-115">Cómo reanudar instancias de orquestación suspendidas</span><span class="sxs-lookup"><span data-stu-id="cf4a6-115">How to Resume Suspended Orchestration Instances</span></span>](../core/how-to-resume-suspended-orchestration-instances.md)