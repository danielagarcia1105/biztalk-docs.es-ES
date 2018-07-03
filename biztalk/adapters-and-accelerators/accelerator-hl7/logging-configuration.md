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
# <a name="logging-configuration"></a>Configuración de registro
Juntos, servidor MicrosoftBizTalk y [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] ofrecen transaccional y digitales Enterprise Application Integration (EAI) las comunicaciones seguras para los proveedores de atención médica, como hospitales, clínicas y las casas de pacientes. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proporciona la capacidad para coordinar la actividad de la aplicación y el procesamiento de transacciones, enrutar los mensajes de forma dinámica, validar y transformar datos y el transporte a través de una variedad de adaptadores. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] admite el American National Standards Institute ANSI y acreditadas mantenimiento nivel siete (HL7) estándar que utilizan aplicaciones clínicas y administrativas en las redes del proveedor para intercambiar datos médicos en tiempo real de mensajería.  
  
 Los mensajes de HL7 que pasan por el sistema de acelerador pueden ser muy críticos. Por ejemplo, los datos podrían ser una transacción financiera o registros médicos del paciente. Para garantizar el cumplimiento de seguridad de HL7 y los Reglamentos de privacidad, los administradores del sistema deben poder hacer lo siguiente:  
  
- Depurar mensajes suspendidos  
  
- Supervisar el acceso del sistema y archivos de forma continuada para detectar posibles intrusos y reducir el riesgo de infracciones de seguridad  
  
  Esta sección proporciona información conceptual y procedimientos para permitirle configurar la auditoría y registro, examinar e interpretar los datos de auditoría y registro de eventos y ejecutar consultas en los datos registrados.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Acerca del proceso de registro](../../adapters-and-accelerators/accelerator-hl7/about-the-logging-process.md)  
  
-   [Configuración del registro](../../adapters-and-accelerators/accelerator-hl7/configuring-logging.md)