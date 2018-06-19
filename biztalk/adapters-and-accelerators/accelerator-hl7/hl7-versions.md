---
title: HL7 Versiones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HL7, standards
- HL7, versions
ms.assetid: 47299c6f-55c3-4434-8170-5ad73fe9a84c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c7edcfa6c44467c0660efd8a9b4b02df7010de6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204828"
---
# <a name="hl7-versions"></a>Versiones de HL7
HL7 versión 2 es una familia de estándares estrechamente relacionados, en lugar de un único estándar. La organización de HL7 ha diseñado estos estándares para ser compatibles hacia arriba a través de la aplicación de las reglas de compatibilidad entre versiones de HL7. Estas reglas se garantizan que, dentro de los límites de la versión 2, una interfaz definida en las reglas de una versión de HL7 seguirá funcionando dentro de la definición de las versiones de sucesor. Para que un sistema receptor podrá aceptar mensajes de las versiones posteriores sin interrumpir su implementación y el envío de un sistema podrá continuar enviando mensajes para destinatarios que son compatibles con versiones posteriores.  
  
 Es importante tener en cuenta que [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]):  
  
-   Es compatible con todas las versiones de HL7 en vivo de la versión 2.1 a través de la versión 2.5  
  
-   Proporciona la funcionalidad necesaria para la asignación entre las versiones de HL7 y permite la interoperabilidad de varias versiones en un único sitio  
  
-   Admite la localización admitiendo segmentos de Z y permite la asignación entre interpretaciones alternativos o los usos de los mensajes estándares  
  
 Es importante tener en cuenta la diferencia entre las versiones del estándar de mensajería:  
  
-   Versión 1 funcionaron como una prueba de concepto  
  
-   Versión 2 proporciona una colección de especificaciones de mensaje para admitir el intercambio de mensajes entre aplicaciones  
  
-   Versión 3 proporcionará un conjunto integrado de especificaciones para admitir una variedad de necesidades de interoperabilidad basados en modelos  
  
 En esencia, la versión 2 se centra en un enfoque práctico para proporcionar a los usuarios con las especificaciones que necesitan para llevar a cabo tareas especificadas, mientras la versión 3 se centra en asegura la coherencia y la extensibilidad a largo plazo para el cuerpo de las especificaciones de mensaje toma como una entero.  
  
 La arquitectura de documento clínicos proporciona una extensión importante para el estándar HL7 introduciendo estándares para la representación de documentos clínicos mediante XML.  
  
 La siguiente tabla muestra la progresión de desarrollo estándar HL7.  
  
|Evento|Year|Detalles|  
|-----------|----------|-------------|  
|HL7 fundada|1987|La primera reunión en Stanford, CA, incluye a 12 asistentes.|  
|V1.0|1987|Borrador presentada a reunión pleno HL7.|  
|V2.0|1988|Borrador presentada a reunión pleno HL7.|  
|V2.1 publicado|1990|La primera se ha implementado ampliamente versión|  
|V2.2 publicado|1994||  
|V.2.3 publicado|1997|ANSI aprobado|  
|V2.3.1 publicado|1999|ANSI aprobado|  
|V2.4 publicado|2000|ANSI aprobado|  
|Arquitectura documento clínicos|2000|ANSI aprobado|  
|Versión 2.5 publicado|2003|Completar la aprobación de HL7, enviada a ANSI para su aprobación.|  
|V3.0 en curso|2003||  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [Utilizar esquemas 2.X HL7](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [Uso de esquemas XML de HL7 2.](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)   
 [Modos de mensaje](../../adapters-and-accelerators/accelerator-hl7/message-modes.md)   
 [Mensajería HL7](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)