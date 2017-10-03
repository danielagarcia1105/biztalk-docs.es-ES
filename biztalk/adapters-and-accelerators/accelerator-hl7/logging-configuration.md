---
title: "Configuración de registro | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, auditing
- configuring, logging
- logging, configuring
- auditing, configuring
ms.assetid: 5cd7aec1-bd38-4d37-9a79-b01eeb89337d
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 058a1fce8105a3147fb2e537a9182e7d886bb953
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="logging-configuration"></a>Configuración de registro
Juntos, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] y [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] ofrecer comunicaciones seguras de integración de aplicaciones empresariales (EAI) de transaccional y digitales para proveedores de atención médica como hospitales, las sesiones y convalecientes. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]proporciona la capacidad para coordinar la actividad de la aplicación y el procesamiento de transacciones, enrutar los mensajes de forma dinámica, validar y transformar datos y el transporte a través de una variedad de adaptadores. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]admite el American National Standards Institute ANSI-accredited mantenimiento nivel siete (HL7) estándar utilizado por aplicaciones clínicas y administrativas en redes de proveedores para intercambiar datos médicos en tiempo real de mensajería.  
  
 Los mensajes HL7 que pasan a través del sistema de acelerador pueden ser muy importantes. Por ejemplo, los datos pudieron ser una transacción financiera o historial médico del paciente. Para garantizar el cumplimiento con las normativas de privacidad y seguridad de HL7, los administradores del sistema deben poder hacer lo siguiente:  
  
-   Depurar mensajes suspendidos  
  
-   Supervisar el acceso de sistema y archivos de forma continuada para detectar posibles intrusos y reducir el riesgo de infracciones de seguridad  
  
 Esta sección proporciona información conceptual y procedimientos para permitirle configurar la auditoría y registro, examinar e interpretar los datos de auditoría y registros de eventos y ejecutar consultas en los datos registrados.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Acerca del proceso de registro](../../adapters-and-accelerators/accelerator-hl7/about-the-logging-process.md)  
  
-   [Configurar el registro](../../adapters-and-accelerators/accelerator-hl7/configuring-logging.md)