---
title: Componente de canalización de mensajes desconocidos en el desensamblador XML | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Allow Unrecognized Messages property
- XMLNorm.AllowUnrecognizedMessage property
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component], unrecognized messages
ms.assetid: 5a6be3a8-0bac-426a-bf0b-5091191091de
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c7df0ea8abe05f866d5cb4f9fb86d85083e1690
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987669"
---
# <a name="unrecognized-messages-in-the-xml-disassembler-pipeline-component"></a>Mensajes desconocidos en el componente de canalización de desensamblador XML
El componente de canalización de desensamblador XML puede controlar un mensaje como "desconocido" en los siguientes casos:  
  
- Se recibe un mensaje XML sin cuerpo, con el cuerpo vacío o con datos vacíos en el cuerpo.  
  
- Se recibe un mensaje XML pero no se ha implementado ningún esquema para él.  
  
  Un mensaje desconocido se realiza según la **permitir mensaje desconocido** propiedad (o en el **XMLNorm.AllowUnrecognizedMessage** propiedad en el contexto del mensaje).  
  
  Si **permitir mensaje desconocido** está establecido en **True**, ocurre lo siguiente:  
  
- Un mensaje sin cuerpo, con el cuerpo vacío/nulo o con datos vacíos/nulos en el cuerpo pasa sin ningún cambio a través del desensamblador XML.  
  
- Un documento XML sin ningún esquema implementado asociado pasa sin cambios a través del desensamblador XML.  
  
- El desensamblador XML procesa un documento XML que tiene un esquema implementado asociado independientemente de si se hace referencia explícita al esquema en una propiedad del componente o si se ha encontrado durante el proceso de resolución del esquema.  
  
  Si **permitir mensaje desconocido** está establecido en **False**, ocurre lo siguiente:  
  
- Un mensaje sin cuerpo, con el cuerpo vacío/nulo o con datos vacíos/nulos en el cuerpo no pasa a través del desensamblador XML.  
  
- Un documento XML que no tiene un esquema implementado asociado no pasa a través del desensamblador. Se genera un informe de error y se suspende el mensaje si es posible.  
  
- El desensamblador XML procesa un documento XML que tiene un esquema implementado asociado independientemente de si se hace referencia explícita al esquema en una propiedad del componente o si se ha encontrado durante el proceso de resolución del esquema.  
  
  De forma predeterminada, el desensamblador XML no permite mensajes desconocidos.  
  
> [!NOTE]
>  No se procesan mensajes XML que no son el Desensamblador de XML sin tener en cuenta la **permitir mensaje desconocido** configuración de la propiedad.  
  
## <a name="see-also"></a>Vea también  
 [Componente de canalización de desensamblador XML](../core/xml-disassembler-pipeline-component.md)   
 [Cómo configurar el componente de canalización de desensamblador XML](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)