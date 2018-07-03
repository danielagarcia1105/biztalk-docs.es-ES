---
title: HL7 Versiones | Microsoft Docs
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
ms.openlocfilehash: b3806ed8db2272068ff60c6656b73cdf4a726bd9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005901"
---
# <a name="hl7-versions"></a>Versiones de HL7
HL7 versión 2 es una familia de estándares estrechamente relacionados, en lugar de un único estándar. La organización de HL7 ha diseñado estos estándares para ser hacia arriba compatibles a través de la aplicación de las reglas de compatibilidad entre versiones de HL7. Estas reglas garantizan que, dentro de los confines de la versión 2, una interfaz definida en las reglas de una versión de HL7 seguirán funcionando en la definición de las versiones de sucesor. Para que un sistema receptor podrá aceptar mensajes de las versiones posteriores sin interrumpir su implementación y el envío de un sistema podrá continuar enviando mensajes a los receptores que admiten las versiones posteriores.  
  
 Es importante tener en cuenta que Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]):  
  
- Admite todas las versiones de HL7 en directo desde la versión 2.1 a través de la versión 2.5  
  
- Proporciona la funcionalidad necesaria para la asignación entre las versiones de HL7 y permite la interoperabilidad de varias versiones en un único sitio  
  
- Admite la localización de admitiendo los segmentos de Z y permite la asignación entre las interpretaciones alternativas o usos de los mensajes estándares  
  
  Es importante tener en cuenta la diferencia entre las versiones del estándar de mensajería:  
  
- Versión 1 funcionaba como una prueba de concepto  
  
- Versión 2 le proporciona una colección de especificaciones de mensaje para admitir el intercambio de mensajes entre aplicaciones  
  
- Versión 3 proporcionará un conjunto integrado de especificaciones para admitir una variedad de necesidades de interoperabilidad basados en modelo  
  
  En esencia, versión 2 se centra en un método pragmático para proporcionar a los usuarios con las especificaciones que necesitan para llevar a cabo las tareas especificadas, aunque versión 3 se centra en garantizar la coherencia y extensibilidad a largo plazo para el cuerpo de las especificaciones de mensaje que se toma como un entero.  
  
  La arquitectura de documento clínico proporciona una extensión importante para el estándar HL7 mediante la introducción de estándares para la representación de documentos clínicos mediante XML.  
  
  En la tabla siguiente se muestra la progresión de desarrollo estándar HL7.  
  
|Evento|Year|Detalles|  
|-----------|----------|-------------|  
|Fundada de HL7|1987|La primera reunión, en Stanford, CA, que incluye a 12 asistentes.|  
|V1.0|1987|Borrador presentado a HL7 pleno reunión.|  
|VERSIÓN 2.0|1988|Borrador presentado a HL7 pleno reunión.|  
|V2.1 publicado|1990|La primera ampliamente implementado versión|  
|V2.2 publicar|1994||  
|V.2.3 publicado|1997|ANSI aprobado|  
|V2.3.1 publicado|1999|ANSI aprobado|  
|V2.4 publicado|2000|ANSI aprobado|  
|Arquitectura de documento clínico|2000|ANSI aprobado|  
|Versión 2.5 publicado|2003|Completar la aprobación de HL7, enviado a ANSI para su aprobación.|  
|V3.0 en curso|2003||  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes de HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [Uso de esquemas de HL7 2.X](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [Uso de esquemas de HL7 2.Xml](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)   
 [Modos de mensaje](../../adapters-and-accelerators/accelerator-hl7/message-modes.md)   
 [Mensajería de HL7](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)