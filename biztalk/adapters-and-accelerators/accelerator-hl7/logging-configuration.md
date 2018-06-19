---
title: Configuración de registro | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, auditing
- configuring, logging
- logging, configuring
- auditing, configuring
ms.assetid: 5cd7aec1-bd38-4d37-9a79-b01eeb89337d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb9a8cfb173881b3ec6c6e346bcd9f2d3ec54b87
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26004541"
---
# <a name="logging-configuration"></a><span data-ttu-id="20277-102">Configuración de registro</span><span class="sxs-lookup"><span data-stu-id="20277-102">Logging Configuration</span></span>
<span data-ttu-id="20277-103">Juntos, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Server y [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] ofrecer comunicaciones seguras de integración de aplicaciones empresariales (EAI) de transaccional y digitales para proveedores de atención médica como hospitales, las sesiones y convalecientes.</span><span class="sxs-lookup"><span data-stu-id="20277-103">Together, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Server and [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] offer secure transactional and digital Enterprise Application Integration (EAI) communications for health care providers such as hospitals, clinics, and nursing homes.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="20277-104">proporciona la capacidad para coordinar la actividad de la aplicación y el procesamiento de transacciones, enrutar los mensajes de forma dinámica, validar y transformar datos y el transporte a través de una variedad de adaptadores.</span><span class="sxs-lookup"><span data-stu-id="20277-104"> provides the ability to coordinate application activity and transaction processing, dynamically route messages, validate and transform data, and transport over a variety of adapters.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="20277-105">admite el American National Standards Institute ANSI-accredited mantenimiento nivel siete (HL7) estándar utilizado por aplicaciones clínicas y administrativas en redes de proveedores para intercambiar datos médicos en tiempo real de mensajería.</span><span class="sxs-lookup"><span data-stu-id="20277-105"> supports the American National Standards Institute (ANSI)-accredited Health Level Seven (HL7) messaging standard used by clinical and administrative applications in provider networks to exchange medical data in real-time.</span></span>  
  
 <span data-ttu-id="20277-106">Los mensajes HL7 que pasan a través del sistema de acelerador pueden ser muy importantes.</span><span class="sxs-lookup"><span data-stu-id="20277-106">The HL7 messages that pass through the accelerator system can be very critical.</span></span> <span data-ttu-id="20277-107">Por ejemplo, los datos pudieron ser una transacción financiera o historial médico del paciente.</span><span class="sxs-lookup"><span data-stu-id="20277-107">For example, the data could be a patient's medical record or a financial transaction.</span></span> <span data-ttu-id="20277-108">Para garantizar el cumplimiento con las normativas de privacidad y seguridad de HL7, los administradores del sistema deben poder hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="20277-108">To ensure compliance with HL7 security and privacy regulations, system administrators must be able to do the following:</span></span>  
  
-   <span data-ttu-id="20277-109">Depurar mensajes suspendidos</span><span class="sxs-lookup"><span data-stu-id="20277-109">Debug suspended messages</span></span>  
  
-   <span data-ttu-id="20277-110">Supervisar el acceso de sistema y archivos de forma continuada para detectar posibles intrusos y reducir el riesgo de infracciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="20277-110">Monitor system and file access on an ongoing basis to detect potential intruders and reduce the risk of security breaches</span></span>  
  
 <span data-ttu-id="20277-111">Esta sección proporciona información conceptual y procedimientos para permitirle configurar la auditoría y registro, examinar e interpretar los datos de auditoría y registros de eventos y ejecutar consultas en los datos registrados.</span><span class="sxs-lookup"><span data-stu-id="20277-111">This section provides conceptual and procedural information to enable you to configure auditing and logging, examine and interpret audit data and event logs, and run queries against the logged data.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="20277-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="20277-112">In This Section</span></span>  
  
-   [<span data-ttu-id="20277-113">Acerca del proceso de registro</span><span class="sxs-lookup"><span data-stu-id="20277-113">About the Logging Process</span></span>](../../adapters-and-accelerators/accelerator-hl7/about-the-logging-process.md)  
  
-   [<span data-ttu-id="20277-114">Configuración del registro</span><span class="sxs-lookup"><span data-stu-id="20277-114">Configuring Logging</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-logging.md)