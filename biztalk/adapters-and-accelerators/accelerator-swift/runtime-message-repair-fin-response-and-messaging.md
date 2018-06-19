---
title: Tiempo de ejecución, reparación, la respuesta FIN y la mensajería de mensajes | Documentos de Microsoft
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
ms.openlocfilehash: 539d6f6d7a2b84262750f8b3c6da3c16a67f0de9
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
ms.locfileid: "22214108"
---
# <a name="runtime-message-repair-fin-response-and-messaging"></a><span data-ttu-id="f80ed-102">En tiempo de ejecución, reparación de mensajes, respuesta FIN y de mensajería</span><span class="sxs-lookup"><span data-stu-id="f80ed-102">Runtime, message repair, FIN response, and messaging</span></span>

## <a name="overview"></a><span data-ttu-id="f80ed-103">Información general</span><span class="sxs-lookup"><span data-stu-id="f80ed-103">Overview</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="f80ed-104"> [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] proporciona a los clientes y los socios financieros específicos del sector de mensajería y la conectividad de funcionalidad, lo que ayuda a acelera la implementación de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] como middleware para organizaciones financieras.</span><span class="sxs-lookup"><span data-stu-id="f80ed-104"> [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] provides customers and partners with financial-industry-specific messaging and connectivity functionality, which helps accelerate implementation of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] as middleware for financial organizations.</span></span>  
  
 <span data-ttu-id="f80ed-105">Mediante el aprovechamiento de los estándares abiertos en la función herramientas y funciones en tiempo de ejecución de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para implementar la compatibilidad con formatos de mensaje como SWIFT, A4SWIFT reduce la barrera para la adopción de estándares SWIFT actualizados mediante el uso de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] como un uso general plataforma de integración de middleware.</span><span class="sxs-lookup"><span data-stu-id="f80ed-105">By leveraging the open-standards based tools and runtime facilities of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] to implement support for message formats like SWIFT, A4SWIFT reduces the barrier to adoption of updated SWIFT standards by employing [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] as a general-purpose middleware integration platform.</span></span>  
  
 <span data-ttu-id="f80ed-106">A4SWIFT y [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] reducir el tiempo de comercialización mientras también reduce el costo total de propiedad (TCO) mediante la reducción del costo general de soporte y mantenimiento de la entrega de los servidores de clases para el hospedaje de aplicaciones y la integración, así como flujo de trabajo de enterprise implementación en el sector de servicios financieros.</span><span class="sxs-lookup"><span data-stu-id="f80ed-106">A4SWIFT and [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] reduce the time-to-market while also decreasing the total cost of ownership (TCO) by reducing the overall maintenance and support cost of delivering enterprise class servers for application hosting and integration as well as workflow implementation in the financial services industry.</span></span>  
  
 <span data-ttu-id="f80ed-107">Puede categorizar funcionalidad de A4SWIFT como SWIFT mensajería y la conectividad de SWIFT.</span><span class="sxs-lookup"><span data-stu-id="f80ed-107">You can broadly categorize A4SWIFT functionality as SWIFT messaging and SWIFT connectivity.</span></span> <span data-ttu-id="f80ed-108">Mensajería de A4SWIFT completa incluye análisis del mensaje SWIFT y validación (incluida la entrada/salida de procesamiento por lotes), reparación y entrada de mensaje (incluida la integración con [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] como la herramienta de usuario front-end) y otras aplicaciones de línea de negocio (LOB).</span><span class="sxs-lookup"><span data-stu-id="f80ed-108">Full A4SWIFT messaging encompasses SWIFT message parsing and validation (including inbound/outbound batching), message entry and repair (including integration with [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] as the front-end user tool), and other line-of-business (LOB) applications.</span></span>  
  
 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]<span data-ttu-id="f80ed-109"> proporciona esquemas XSD y validación completa, incluidas las reglas de red, para 358 todos los mensajes (FIN) financieros.</span><span class="sxs-lookup"><span data-stu-id="f80ed-109"> provides XSD schemas and full validation, including network rules, for all 358 of the financial (FIN) messages.</span></span> <span data-ttu-id="f80ed-110">También proporciona anulando entrante.</span><span class="sxs-lookup"><span data-stu-id="f80ed-110">It also provides inbound debatching.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="f80ed-111">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="f80ed-111">Next steps</span></span>  
 <span data-ttu-id="f80ed-112">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="f80ed-112">This section contains:</span></span>  
  
-   [<span data-ttu-id="f80ed-113">Components</span><span class="sxs-lookup"><span data-stu-id="f80ed-113">Components</span></span>](components.md)  
  
-   [<span data-ttu-id="f80ed-114">Acelerador de BizTalk para el tiempo de ejecución de SWIFT</span><span class="sxs-lookup"><span data-stu-id="f80ed-114">BizTalk Accelerator for SWIFT Runtime</span></span>](biztalk-accelerator-for-swift-runtime.md)  
  
-   [<span data-ttu-id="f80ed-115">Reparación de mensajes y Nuevo envío</span><span class="sxs-lookup"><span data-stu-id="f80ed-115">Message Repair and New Submission</span></span>](message-repair-and-new-submission.md)  
  
-   [<span data-ttu-id="f80ed-116">Conciliación de respuestas de FIN</span><span class="sxs-lookup"><span data-stu-id="f80ed-116">FIN Response Reconciliation</span></span>](fin-response-reconciliation.md)  
  
-   [<span data-ttu-id="f80ed-117">Mensajes de SWIFT</span><span class="sxs-lookup"><span data-stu-id="f80ed-117">SWIFT Messages</span></span>](swift-messages.md)

- [<span data-ttu-id="f80ed-118">Propiedades promocionadas A4SWIFT_\*</span><span class="sxs-lookup"><span data-stu-id="f80ed-118">A4SWIFT_\* Promoted Properties</span></span>](a4swift-promoted-properties.md)