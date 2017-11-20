---
title: "Registro operativo, el procesamiento por lotes de mensajes, configuración de validación y asknowledgment | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BTAHL7, administering
- managing
- BTAHL7, managing
- administering
ms.assetid: c7376de4-4e1d-47e2-acf7-0a32e7a4b073
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3282d69fc572c4aa32888f9a3ed8a806deef5c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="operational-logging-message-batching-validation-and-asknowledgment-settings"></a><span data-ttu-id="1c5d2-102">Registro operativo, el procesamiento por lotes de mensajes, validación y configuración de asknowledgment</span><span class="sxs-lookup"><span data-stu-id="1c5d2-102">Operational logging, message batching, validation and asknowledgment settings</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="1c5d2-103">[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] incluye un servidor y una serie de herramientas de integración de aplicaciones empresariales (EAI), la automatización de procesos de negocio y facilitar las interacciones con los socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="1c5d2-103"> [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] encompasses a server and series of tools for enterprise application integration (EAI), automating business processes, and facilitating interactions with business partners.</span></span> <span data-ttu-id="1c5d2-104">Basado en la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] BTAHL7 de plataforma, promociona la integración de aplicaciones médicas para cualquier instalación utilizando el estándar HL7.</span><span class="sxs-lookup"><span data-stu-id="1c5d2-104">Built on the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] platform, BTAHL7 promotes medical application integration for any facility using the HL7 standard.</span></span> <span data-ttu-id="1c5d2-105">HL7 contiene estándares para intercambiar, integración y recuperar la información electrónica en práctica clínica y administración.</span><span class="sxs-lookup"><span data-stu-id="1c5d2-105">HL7 contains standards for exchanging, integrating, and retrieving electronic information in clinical practice and management.</span></span>  
  
 <span data-ttu-id="1c5d2-106">Los analistas de usuario de interfaz configurar socios comerciales, las confirmaciones de mensaje, el procesamiento por lotes de mensajes y otros detalles que requiera el proceso de negocio.</span><span class="sxs-lookup"><span data-stu-id="1c5d2-106">Interface user analysts configure trading partners, message acknowledgments, message batching, and other details that your business process requires.</span></span>  
  
 <span data-ttu-id="1c5d2-107">Esta sección proporciona información conceptual y procedimientos que le permite supervisar y mantener el entorno de aplicación de BTAHL7 eficazmente.</span><span class="sxs-lookup"><span data-stu-id="1c5d2-107">This section provides conceptual and procedural information that enables you to effectively monitor and maintain your BTAHL7 application environment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1c5d2-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1c5d2-108">In This Section</span></span>  
  
-   [<span data-ttu-id="1c5d2-109">Configuración de registro</span><span class="sxs-lookup"><span data-stu-id="1c5d2-109">Logging Configuration</span></span>](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md)  
  
-   [<span data-ttu-id="1c5d2-110">Procesamiento por lotes de mensajes</span><span class="sxs-lookup"><span data-stu-id="1c5d2-110">Message Batching</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)  
  
-   [<span data-ttu-id="1c5d2-111">Configuración de la validación</span><span class="sxs-lookup"><span data-stu-id="1c5d2-111">Validation Settings</span></span>](../../adapters-and-accelerators/accelerator-hl7/validation-settings.md)  
  
-   [<span data-ttu-id="1c5d2-112">Invalidaciones de campo de MSH</span><span class="sxs-lookup"><span data-stu-id="1c5d2-112">MSH Field Overrides</span></span>](../../adapters-and-accelerators/accelerator-hl7/msh-field-overrides.md)  
  
-   [<span data-ttu-id="1c5d2-113">Configuración de confirmación</span><span class="sxs-lookup"><span data-stu-id="1c5d2-113">Acknowledgment Settings</span></span>](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-settings.md)  
  
-   [<span data-ttu-id="1c5d2-114">Soporte extendido de codificación</span><span class="sxs-lookup"><span data-stu-id="1c5d2-114">Extended Encoding Support</span></span>](../../adapters-and-accelerators/accelerator-hl7/extended-encoding-support.md)