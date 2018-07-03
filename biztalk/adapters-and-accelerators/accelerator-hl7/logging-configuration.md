---
title: Configuración de registro | Microsoft Docs
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
ms.openlocfilehash: 83e15247158dd21c237064692931a83f6885f05e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002461"
---
# <a name="logging-configuration"></a><span data-ttu-id="1bb1f-102">Configuración de registro</span><span class="sxs-lookup"><span data-stu-id="1bb1f-102">Logging Configuration</span></span>
<span data-ttu-id="1bb1f-103">Juntos, servidor MicrosoftBizTalk y [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] ofrecen transaccional y digitales Enterprise Application Integration (EAI) las comunicaciones seguras para los proveedores de atención médica, como hospitales, clínicas y las casas de pacientes.</span><span class="sxs-lookup"><span data-stu-id="1bb1f-103">Together, MicrosoftBizTalk Server and [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] offer secure transactional and digital Enterprise Application Integration (EAI) communications for health care providers such as hospitals, clinics, and nursing homes.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="1bb1f-104"> proporciona la capacidad para coordinar la actividad de la aplicación y el procesamiento de transacciones, enrutar los mensajes de forma dinámica, validar y transformar datos y el transporte a través de una variedad de adaptadores.</span><span class="sxs-lookup"><span data-stu-id="1bb1f-104"> provides the ability to coordinate application activity and transaction processing, dynamically route messages, validate and transform data, and transport over a variety of adapters.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="1bb1f-105"> admite el American National Standards Institute ANSI y acreditadas mantenimiento nivel siete (HL7) estándar que utilizan aplicaciones clínicas y administrativas en las redes del proveedor para intercambiar datos médicos en tiempo real de mensajería.</span><span class="sxs-lookup"><span data-stu-id="1bb1f-105"> supports the American National Standards Institute (ANSI)-accredited Health Level Seven (HL7) messaging standard used by clinical and administrative applications in provider networks to exchange medical data in real-time.</span></span>  
  
 <span data-ttu-id="1bb1f-106">Los mensajes de HL7 que pasan por el sistema de acelerador pueden ser muy críticos.</span><span class="sxs-lookup"><span data-stu-id="1bb1f-106">The HL7 messages that pass through the accelerator system can be very critical.</span></span> <span data-ttu-id="1bb1f-107">Por ejemplo, los datos podrían ser una transacción financiera o registros médicos del paciente.</span><span class="sxs-lookup"><span data-stu-id="1bb1f-107">For example, the data could be a patient's medical record or a financial transaction.</span></span> <span data-ttu-id="1bb1f-108">Para garantizar el cumplimiento de seguridad de HL7 y los Reglamentos de privacidad, los administradores del sistema deben poder hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1bb1f-108">To ensure compliance with HL7 security and privacy regulations, system administrators must be able to do the following:</span></span>  
  
- <span data-ttu-id="1bb1f-109">Depurar mensajes suspendidos</span><span class="sxs-lookup"><span data-stu-id="1bb1f-109">Debug suspended messages</span></span>  
  
- <span data-ttu-id="1bb1f-110">Supervisar el acceso del sistema y archivos de forma continuada para detectar posibles intrusos y reducir el riesgo de infracciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="1bb1f-110">Monitor system and file access on an ongoing basis to detect potential intruders and reduce the risk of security breaches</span></span>  
  
  <span data-ttu-id="1bb1f-111">Esta sección proporciona información conceptual y procedimientos para permitirle configurar la auditoría y registro, examinar e interpretar los datos de auditoría y registro de eventos y ejecutar consultas en los datos registrados.</span><span class="sxs-lookup"><span data-stu-id="1bb1f-111">This section provides conceptual and procedural information to enable you to configure auditing and logging, examine and interpret audit data and event logs, and run queries against the logged data.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1bb1f-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1bb1f-112">In This Section</span></span>  
  
-   [<span data-ttu-id="1bb1f-113">Acerca del proceso de registro</span><span class="sxs-lookup"><span data-stu-id="1bb1f-113">About the Logging Process</span></span>](../../adapters-and-accelerators/accelerator-hl7/about-the-logging-process.md)  
  
-   [<span data-ttu-id="1bb1f-114">Configuración del registro</span><span class="sxs-lookup"><span data-stu-id="1bb1f-114">Configuring Logging</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-logging.md)