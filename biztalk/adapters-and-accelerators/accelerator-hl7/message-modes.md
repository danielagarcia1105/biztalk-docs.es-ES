---
title: Modos de mensaje | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message modes, about message modes
- messages, message modes
- message modes, HL7 messages
ms.assetid: 2d832b67-6f0e-45e1-95ac-cb80b74a7831
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfce63f527dbe9643228b3b47a509b404e78c510
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009141"
---
# <a name="message-modes"></a>Modos de mensaje
Hay dos conceptos básicos que subyacen a todos los mensajes de HL7. Estos conceptos de direcciones distintas formas en que pueden interactuar sistemas independientes que intercambiar datos y proporcionan una estructura que admita los requisitos de interoperabilidad con el tiempo dentro de un sistema distribuido de atención médica. Los conceptos descritos a continuación definen los temas subyacentes tras el diseño de HL7:  
  
- **Modo de mensajería**. El reconocimiento de los tres objetivos fundamentales para el intercambio de información: para difundir información (declarativo), para solicitar información (interrogative) y para solicitar que el sistema tome las acciones (imperativo). Cada uno de estos propósitos tiene sus requisitos específicos y el patrón de flujo de mensajes.  
  
- **Modo de confirmación**. La necesidad de admitir estrechamente y escasamente acoplado estilos de mensajería. Los modos de confirmación para HL7 habilitar una aplicación de envío para solicitar una respuesta desde el receptor, o para habilitar la red subyacente garantizar la entrega de mensajes.  
  
- **Localización**. La necesidad de admitir requisitos locales específicos al permitir que las entidades introducir material específica del sitio en las especificaciones del mensaje.  
  
- **Evolución**. La necesidad de admitir sitios con muchas interfaces y muchas aplicaciones habilitando la interoperabilidad entre versiones estándares. Esto permite que las entidades a las actualizaciones de interfaz de fase, en lugar de requerir actualizaciones simultáneas de todas las interfaces.  
  
  Las siguientes funciones del Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) admite los requisitos anteriores:  
  
- Modos de confirmación de HL7. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] admite el modo de confirmación original pasando las confirmaciones de la aplicación al remitente del mensaje original.  
  
- Diferentes modos de mensajes. Esto permite la difusión a varios destinos y une las consultas a la respuesta de consultas asociado.  
  
- Compatibilidad con varias versiones, incluido XML y las codificaciones están delimitados por canalización.  
  
- Asignación entre las versiones de HL7 para habilitar diversos entornos y las actualizaciones.  
  
- Localización (personalización) dentro de la orquestación.  
  
- Herramientas para admitir la depuración y la evaluación de las nuevas interfaces.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes de HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [Uso de esquemas de HL7 2.X](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [Uso de esquemas de HL7 2.Xml](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)   
 [Tipos de mensajes y eventos](../../adapters-and-accelerators/accelerator-hl7/message-types-and-events.md)   
 [Mensajería de HL7](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)