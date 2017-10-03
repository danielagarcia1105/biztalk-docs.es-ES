---
title: "Adaptador de recepción SOAP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SOAP adapters, receive adapters
- receive adapters, SOAP adapters
ms.assetid: bb968fa8-0515-4f3a-bb39-9effb83e960c
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06fac19580d6083ed1b0d4be315d3285acf14fcc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="soap-receive-adapter"></a>Adaptador de recepción SOAP
El adaptador de recepción SOAP se utiliza para recibir solicitudes de servicios Web. El adaptador de recepción SOAP crea un objeto de mensaje de BizTalk y promociona las propiedades asociadas al contexto de mensaje.  
  
 Una recepción de SOAP adaptador URI debe correlacionarse con una o varias orquestaciones de BizTalk o esquemas que se han publicado como un servicio web con el **Asistente para publicación de BizTalk Web Services**. El servicio Web publicado expone uno o más métodos web que se correlacionan con uno o varios esquemas u orquestaciones de BizTalk Server en un ensamblado de BizTalk. En esencia, el servicio Web publicado actúa como proxy del servidor para los esquemas o las orquestaciones de BizTalk y reenvía solicitudes y respuestas entre el cliente y éstos. Para obtener más información acerca de cómo publicar orquestaciones de BizTalk o esquemas como servicios web, consulte [publicar servicios Web](../core/publishing-web-services.md).  
  
 Una ubicación de recepción que usa el adaptador de SOAP se puede configurar como unidireccional o como solicitud-respuesta (bidireccional). Cuando una ubicación de recepción unidireccional se configura para usar el adaptador de SOAP, el servicio Web asociado invoca el ensamblado enlazado al puerto de recepción y devuelve el estado de la solicitud al cliente. Cuando una ubicación de recepción de solicitud-respuesta (bidireccional) se configura para usar el adaptador de SOAP, el servicio Web asociado invoca el ensamblado enlazado al puerto de recepción y devuelve un documento de respuesta al cliente. Para obtener más información acerca de la mensajería de solicitud-respuesta vea [mensajería de solicitud-respuesta](../core/request-response-messaging.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué es el adaptador de SOAP?](../core/what-is-the-soap-adapter.md)   
 [Recomendaciones de seguridad del adaptador SOAP](../core/soap-adapter-security-recommendations.md)