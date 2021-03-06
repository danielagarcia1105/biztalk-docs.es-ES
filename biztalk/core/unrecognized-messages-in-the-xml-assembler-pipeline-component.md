---
title: Componente de canalización de mensajes desconocidos en el ensamblador XML | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XMLNorm.AllowUnrecognizedMessage property
- XML Assembler [pipeline component], unrecognized messages
- pipeline components, XML Assembler
ms.assetid: dd98512a-33a4-4b2e-977e-1b3a30747c6a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de9f072fc09126d56397725f93505afaca46adf4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974821"
---
# <a name="unrecognized-messages-in-the-xml-assembler-pipeline-component"></a>Mensajes desconocidos en el componente de canalización de ensamblador XML
El componente de ensamblador XML trata los mensajes como “desconocidos” si:  
  
-   No hay ninguna parte del cuerpo  
  
-   Hay una parte del cuerpo vacía.  
  
-   No hay datos en la parte del cuerpo.  
  
-   No hay ningún esquema implementado asociado.  
  
> [!NOTE]
>  A los mensajes que no sean XML siempre se les trata como desconocidos.  
  
 La manera en que el ensamblador XML controla un mensaje desconocido se controla mediante el **XMLNorm.AllowUnrecognizedMessage** propiedad de contexto del mensaje.  
  
 Cuando **XMLNorm.AllowUnrecognizedMessage** está establecido en **True**, el ensamblador XML controla los documentos XML como sigue:  
  
- Un mensaje sin ninguna parte del cuerpo, con una parte del cuerpo vacía o con datos vacíos en la parte del cuerpo pasa sin ningún cambio a través del desensamblador XML.  
  
- Un documento que no tiene un esquema implementado asociado pasa sin ningún cambio a través del ensamblador.  
  
- El ensamblador procesa un documento que tiene un esquema implementado asociado (independientemente de si se hace referencia explícita al esquema en una propiedad del componente o si se ha encontrado durante el proceso de resolución del esquema).  
  
  Si **XMLNorm.AllowUnrecognizedMessage** está establecido en **False**, el ensamblador XML controla los documentos XML como sigue:  
  
- Un mensaje sin ninguna parte del cuerpo, con una parte del cuerpo vacía o con datos vacíos en la parte del cuerpo no se procesa. Se genera un informe de error y se suspende el mensaje.  
  
- Un mensaje que no tenga un esquema implementado asociado no se procesa. Se genera un informe de error y se suspende el mensaje.  
  
- El ensamblador procesa un documento que tiene un esquema implementado asociado (independientemente de si se hace referencia explícita al esquema en una propiedad del componente o si se ha encontrado durante el proceso de resolución del esquema).  
  
- De forma predeterminada, el componente de ensamblador XML no permite mensajes desconocidos (es decir, **XMLNorm.AllowUnrecognizedMessages** se considera **False** si no se establece en el contexto del mensaje).  
  
## <a name="see-also"></a>Vea también  
 [Componente de canalización de ensamblador XML](../core/xml-assembler-pipeline-component.md)   
 [Cómo configurar el componente de canalización de ensamblador XML](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
 [Pipelines\AssemblerDisassembler (carpeta de ejemplos de BizTalk Server)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)