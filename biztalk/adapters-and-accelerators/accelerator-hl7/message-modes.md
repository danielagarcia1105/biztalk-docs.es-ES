---
title: Modos de mensaje | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message modes, about message modes
- messages, message modes
- message modes, HL7 messages
ms.assetid: 2d832b67-6f0e-45e1-95ac-cb80b74a7831
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b09a610d000ae6beaef75b1ed0144d1597d517b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-modes"></a>Modos de mensaje
Hay dos conceptos básicos que subyacen a todos los mensajes de HL7. Estos conceptos de direcciones distintas formas en el que pueden interactuar sistemas independientes que intercambian datos y proporcionan una estructura que admita los requisitos de interoperabilidad con el tiempo dentro de un sistema distribuido de atención médica. Los conceptos siguientes definen los temas subyacentes detrás del diseño de HL7:  
  
-   **Modo de mensajería**. El reconocimiento de los tres objetivos fundamentales para el intercambio de información: para difundir información (declarativo), para solicitar información (interrogative) y para solicitar que el sistema realice la acción (imperativo). Cada uno de estos propósitos tiene su unos requisitos determinados y el modelo de flujo de mensajes.  
  
-   **Modo de confirmación**. La necesidad de admitir flexible y estrechamente acoplado estilos de mensajería. Los modos de confirmación para HL7 habilitar una aplicación emisora que requieren una respuesta desde el receptor, o para habilitar la red subyacente garantizar la entrega de mensajes.  
  
-   **Localización**. La necesidad de admitir los requisitos locales específicos al permitir que las entidades introducir material específica del sitio en las especificaciones de mensaje.  
  
-   **Evolución**. La necesidad de admitir sitios con muchas interfaces y muchas aplicaciones habilitando la interoperabilidad entre las versiones estándares. Esto permite que las entidades a las actualizaciones de interfaz de fase, en lugar de requerir actualizaciones simultáneas de todas las interfaces.  
  
 Las siguientes funciones de [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) admite los requisitos anteriores:  
  
-   Modos de confirmación de HL7. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]admite el modo de confirmación original pasando confirmaciones de aplicación al remitente del mensaje original.  
  
-   Diferentes modos de mensajes. Esto permite la difusión a varios destinos y une las consultas a la respuesta de consultas asociado.  
  
-   Compatibilidad con varias versiones, incluidas la codificación XML y delimitado por canalización.  
  
-   Asignación entre versiones de HL7 a habilitar diversos entornos y las actualizaciones.  
  
-   Localización (personalización) dentro de la orquestación.  
  
-   Herramientas para admitir la depuración y la evaluación de nuevas interfaces.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [Utilizar esquemas 2.X HL7](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [Uso de esquemas XML de HL7 2.](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)   
 [Eventos y los tipos de mensaje](../../adapters-and-accelerators/accelerator-hl7/message-types-and-events.md)   
 [Mensajería HL7](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)