---
title: Tiempo de ejecución, reparación, respuesta FIN y mensajería de mensajes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, about architecture
- architecture
- BizTalk Accelerator for SWIFT, architecture
ms.assetid: c7f34517-6663-44a6-b6ea-6d55fdb08caf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 360a2e3974f1e4ea5858c583c5dc5fcc364e9756
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974637"
---
# <a name="runtime-message-repair-fin-response-and-messaging"></a><span data-ttu-id="30148-102">En tiempo de ejecución, reparación de mensajes, respuesta FIN y mensajería</span><span class="sxs-lookup"><span data-stu-id="30148-102">Runtime, message repair, FIN response, and messaging</span></span>

## <a name="overview"></a><span data-ttu-id="30148-103">Información general</span><span class="sxs-lookup"><span data-stu-id="30148-103">Overview</span></span>
<span data-ttu-id="30148-104">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] proporciona a los clientes y socios con financieros del sector-funcionalidad específica de conectividad y mensajería, lo que ayuda a acelerar la implementación de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] como middleware para que las organizaciones financieras.</span><span class="sxs-lookup"><span data-stu-id="30148-104">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] provides customers and partners with financial-industry-specific messaging and connectivity functionality, which helps accelerate implementation of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] as middleware for financial organizations.</span></span>  
  
 <span data-ttu-id="30148-105">Mediante el aprovechamiento de los estándares abiertos en la función de las herramientas y las funciones de tiempo de ejecución de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para implementar la compatibilidad con formatos de mensaje como SWIFT, A4SWIFT reduce la barrera para la adopción de estándares SWIFT actualizados mediante el empleo del [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] como un uso general plataforma de middleware de integración.</span><span class="sxs-lookup"><span data-stu-id="30148-105">By leveraging the open-standards based tools and runtime facilities of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] to implement support for message formats like SWIFT, A4SWIFT reduces the barrier to adoption of updated SWIFT standards by employing [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] as a general-purpose middleware integration platform.</span></span>  
  
 <span data-ttu-id="30148-106">A4SWIFT y [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] reducir el tiempo de comercialización mientras también reduce el costo total de propiedad (TCO) al reducir el costo general de mantenimiento y soporte técnico de la entrega de servidores de clases para el hospedaje de aplicaciones y la integración, así como flujo de trabajo de enterprise implementación de la industria de servicios financieros.</span><span class="sxs-lookup"><span data-stu-id="30148-106">A4SWIFT and [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] reduce the time-to-market while also decreasing the total cost of ownership (TCO) by reducing the overall maintenance and support cost of delivering enterprise class servers for application hosting and integration as well as workflow implementation in the financial services industry.</span></span>  
  
 <span data-ttu-id="30148-107">Puede categorizar A4SWIFT funcionalidad como la mensajería de SWIFT y conectividad SWIFT.</span><span class="sxs-lookup"><span data-stu-id="30148-107">You can broadly categorize A4SWIFT functionality as SWIFT messaging and SWIFT connectivity.</span></span> <span data-ttu-id="30148-108">Mensajería de A4SWIFT completa abarca mensaje SWIFT análisis y validación (incluido el procesamiento por lotes entrante y saliente), reparación y entrada de mensaje (incluida la integración con Microsoft [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] como la herramienta de usuario de front-end) y otros aplicaciones de línea de negocio (LOB).</span><span class="sxs-lookup"><span data-stu-id="30148-108">Full A4SWIFT messaging encompasses SWIFT message parsing and validation (including inbound/outbound batching), message entry and repair (including integration with Microsoft [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] as the front-end user tool), and other line-of-business (LOB) applications.</span></span>  
  
 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]<span data-ttu-id="30148-109"> proporciona esquemas XSD y validación completa, incluidas las reglas de red para 358 todos los mensajes (FIN) financieros.</span><span class="sxs-lookup"><span data-stu-id="30148-109"> provides XSD schemas and full validation, including network rules, for all 358 of the financial (FIN) messages.</span></span> <span data-ttu-id="30148-110">También proporciona la desagrupación entrante.</span><span class="sxs-lookup"><span data-stu-id="30148-110">It also provides inbound debatching.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="30148-111">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="30148-111">Next steps</span></span>  
 <span data-ttu-id="30148-112">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="30148-112">This section contains:</span></span>  
  
-   [<span data-ttu-id="30148-113">Components</span><span class="sxs-lookup"><span data-stu-id="30148-113">Components</span></span>](components.md)  
  
-   [<span data-ttu-id="30148-114">Acelerador de BizTalk para el tiempo de ejecución de SWIFT</span><span class="sxs-lookup"><span data-stu-id="30148-114">BizTalk Accelerator for SWIFT Runtime</span></span>](biztalk-accelerator-for-swift-runtime.md)  
  
-   [<span data-ttu-id="30148-115">Reparación de mensajes y Nuevo envío</span><span class="sxs-lookup"><span data-stu-id="30148-115">Message Repair and New Submission</span></span>](message-repair-and-new-submission.md)  
  
-   [<span data-ttu-id="30148-116">Conciliación de respuestas de FIN</span><span class="sxs-lookup"><span data-stu-id="30148-116">FIN Response Reconciliation</span></span>](fin-response-reconciliation.md)  
  
-   [<span data-ttu-id="30148-117">Mensajes de SWIFT</span><span class="sxs-lookup"><span data-stu-id="30148-117">SWIFT Messages</span></span>](swift-messages.md)

- [<span data-ttu-id="30148-118">Propiedades promocionadas A4SWIFT_\*</span><span class="sxs-lookup"><span data-stu-id="30148-118">A4SWIFT_\* Promoted Properties</span></span>](a4swift-promoted-properties.md)