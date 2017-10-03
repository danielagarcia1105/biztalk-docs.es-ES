---
title: "Cómo iniciar excepciones SOAP desde orquestaciones publicado como un servicio Web | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- errors, SOAP exceptions
- orchestrations, SOAP errors
- Web services, orchestrations
ms.assetid: e1c7cd74-d1c8-4b9d-a418-4601b1f040d7
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4ef3d975632b6230cf1e3df299d0d9455f39da0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-throw-soap-exceptions-from-orchestrations-published-as-a-web-service"></a>Cómo iniciar excepciones SOAP desde orquestaciones publicadas como un servicio Web
Puede devolver una excepción SOAP desde una orquestación que haya publicado como un servicio Web. Además, puede agregar un mensaje de error al puerto SOAP y enviarlo en lugar de la respuesta.  
  
### <a name="to-throw-a-soap-exception-from-an-orchestration-published-as-a-web-service"></a>Para iniciar una excepción SOAP desde una orquestación publicada como un servicio Web  
  
1.  Agregar un mensaje de error al tipo de puerto SOAP. El tipo de este mensaje puede ser cualquier esquema compatible con esquema XML (XSD) o un tipo simple.  
  
    > [!NOTE]
    >  Para devolver una cadena como un **SoapException** con información de error, puede utilizar la cadena de tipo simple como el tipo de mensaje de error.  
  
2.  En la orquestación, crear el mensaje de error.  
  
3.  Use la **enviar** forma que se va a vincular a la operación del error en el puerto SOAP que se corresponde con el mensaje de error. Una excepción SOAP ajusta el mensaje de error devuelto.  
  
 Si la orquestación no devuelve un error, utilice otro **enviar** forma para enviar el mensaje de respuesta SOAP estándar mediante la operación de respuesta habitual.  
  
## <a name="see-also"></a>Vea también  
 [Mensajes de error](../core/fault-messages.md)   
 [Publicar una orquestación como servicio Web](../core/publishing-an-orchestration-as-a-web-service.md)