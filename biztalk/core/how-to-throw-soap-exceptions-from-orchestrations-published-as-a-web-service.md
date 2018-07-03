---
title: Cómo iniciar excepciones SOAP desde orquestaciones publicado como un servicio Web | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- errors, SOAP exceptions
- orchestrations, SOAP errors
- Web services, orchestrations
ms.assetid: e1c7cd74-d1c8-4b9d-a418-4601b1f040d7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 328f468485f729df03c28bca48a8b5ed4eaf59e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015205"
---
# <a name="how-to-throw-soap-exceptions-from-orchestrations-published-as-a-web-service"></a>Cómo iniciar excepciones SOAP desde orquestaciones publicadas como un servicio Web
Puede devolver una excepción SOAP desde una orquestación que haya publicado como un servicio Web. Además, puede agregar un mensaje de error al puerto SOAP y enviarlo en lugar de la respuesta.  
  
### <a name="to-throw-a-soap-exception-from-an-orchestration-published-as-a-web-service"></a>Para iniciar una excepción SOAP desde una orquestación publicada como un servicio Web  
  
1. Agregar un mensaje de error al tipo de puerto SOAP. El tipo de este mensaje puede ser cualquier esquema compatible con esquema XML (XSD) o un tipo simple.  
  
   > [!NOTE]
   >  Para devolver una cadena como un **SoapException** con información de error, puede usar la cadena de tipo simple como el tipo de mensaje de error.  
  
2. En la orquestación, crear el mensaje de error.  
  
3. Use la **enviar** forma para vincular a la operación errónea en el puerto SOAP que se corresponde con el mensaje de error. Una excepción SOAP ajusta el mensaje de error devuelto.  
  
   Si la orquestación no devuelve un error, use otro **enviar** forma para enviar el mensaje de respuesta SOAP estándar mediante la operación de respuesta habitual.  
  
## <a name="see-also"></a>Vea también  
 [Mensajes de error](../core/fault-messages.md)   
 [Publicación de una orquestación como un servicio web](../core/publishing-an-orchestration-as-a-web-service.md)