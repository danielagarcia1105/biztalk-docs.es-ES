---
title: Registro operativo, mensaje de procesamiento por lotes, configuración de validación y confirmaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTAHL7, administering
- managing
- BTAHL7, managing
- administering
ms.assetid: c7376de4-4e1d-47e2-acf7-0a32e7a4b073
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 015182a6b091ccbba7452df4c44ed4e4f45c336e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974685"
---
# <a name="operational-logging-message-batching-validation-and-asknowledgment-settings"></a><span data-ttu-id="ba480-102">Registro operativo, el procesamiento por lotes de mensajes, validación y configuración de confirmaciones</span><span class="sxs-lookup"><span data-stu-id="ba480-102">Operational logging, message batching, validation and asknowledgment settings</span></span>
<span data-ttu-id="ba480-103">Microsoft [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] abarca un servidor y una serie de herramientas para la integración de aplicaciones empresariales (EAI), automatización de procesos empresariales y al facilitar las interacciones con los socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="ba480-103">Microsoft [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] encompasses a server and series of tools for enterprise application integration (EAI), automating business processes, and facilitating interactions with business partners.</span></span> <span data-ttu-id="ba480-104">Basado en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] BTAHL7 promueve la plataforma de integración de aplicaciones médicas para cualquier instalación mediante el estándar HL7.</span><span class="sxs-lookup"><span data-stu-id="ba480-104">Built on the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] platform, BTAHL7 promotes medical application integration for any facility using the HL7 standard.</span></span> <span data-ttu-id="ba480-105">HL7 contiene estándares para intercambiar, integración y recuperar información electrónica en prácticas clínicas y administración.</span><span class="sxs-lookup"><span data-stu-id="ba480-105">HL7 contains standards for exchanging, integrating, and retrieving electronic information in clinical practice and management.</span></span>  
  
 <span data-ttu-id="ba480-106">Los analistas de interfaz usuario configuración socios comerciales, las confirmaciones de mensajes, procesamiento por lotes de mensajes y otros detalles que necesita el proceso de negocio.</span><span class="sxs-lookup"><span data-stu-id="ba480-106">Interface user analysts configure trading partners, message acknowledgments, message batching, and other details that your business process requires.</span></span>  
  
 <span data-ttu-id="ba480-107">Esta sección proporciona información conceptual y de procedimiento que permite supervisar y mantener el entorno de aplicación de BTAHL7 de manera eficaz.</span><span class="sxs-lookup"><span data-stu-id="ba480-107">This section provides conceptual and procedural information that enables you to effectively monitor and maintain your BTAHL7 application environment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ba480-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ba480-108">In This Section</span></span>  
  
-   [<span data-ttu-id="ba480-109">Configuración del registro</span><span class="sxs-lookup"><span data-stu-id="ba480-109">Logging Configuration</span></span>](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md)  
  
-   [<span data-ttu-id="ba480-110">Procesamiento de mensajes por lotes</span><span class="sxs-lookup"><span data-stu-id="ba480-110">Message Batching</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)  
  
-   [<span data-ttu-id="ba480-111">Configuración de la validación</span><span class="sxs-lookup"><span data-stu-id="ba480-111">Validation Settings</span></span>](../../adapters-and-accelerators/accelerator-hl7/validation-settings.md)  
  
-   [<span data-ttu-id="ba480-112">Invalidaciones de campos MSH</span><span class="sxs-lookup"><span data-stu-id="ba480-112">MSH Field Overrides</span></span>](../../adapters-and-accelerators/accelerator-hl7/msh-field-overrides.md)  
  
-   [<span data-ttu-id="ba480-113">Configuración de confirmación</span><span class="sxs-lookup"><span data-stu-id="ba480-113">Acknowledgment Settings</span></span>](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-settings.md)  
  
-   [<span data-ttu-id="ba480-114">Soporte extendido de codificación</span><span class="sxs-lookup"><span data-stu-id="ba480-114">Extended Encoding Support</span></span>](../../adapters-and-accelerators/accelerator-hl7/extended-encoding-support.md)