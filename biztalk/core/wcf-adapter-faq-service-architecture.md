---
title: 'Adaptador WCF preguntas más frecuentes: Arquitectura del servicio | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8bad0063-ccff-41f4-b4e0-a02b49403c2d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b73b70474fd30e3a571f59558d6dc439cb981f64
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288724"
---
# <a name="wcf-adapter-faq-service-architecture"></a>Adaptador de WCF preguntas más frecuentes: Arquitectura de servicio
## <a name="what-is-the-difference-between-a-wcf-custom-behavior-and-a-biztalk-pipeline-component"></a>¿Cuál es la diferencia entre un comportamiento personalizado de WCF y un componente de canalización de BizTalk?  
 Tras la inspección inicial, un comportamiento personalizado de WCF es muy similar a una canalización de BizTalk tradicional. Ambos aprovechan el concepto básico de interceptación de mensajes para interrumpir el flujo de un mensaje hacia su destino, ejecutar cierto procesamiento del mensaje y continuar enviándolo hacia su destino. Esta interceptación puede producirse tanto antes (enlazado a una ubicación de recepción) como después (enlazado a un puerto de envío) de que BizTalk Server haya procesado un mensaje. La manera en que tiene lugar esta interceptación dentro de los dos métodos difiere no solo en la implementación, sino también en el punto de interceptación. A continuación se proporcionan algunas de las diferencias:  
  
-   Una orquestación puede usar las canalizaciones. Los comportamientos de WCF se limitan a ser llamados por un adaptador de WCF desde BizTalk Server.  
  
-   Las canalizaciones son una tecnología anterior y específica de BizTalk Server. BizTalk Server puede usar los comportamientos de WCF y éstos también se pueden usar en otros escenarios de WCF puros.  
  
-   Las canalizaciones viven en etapas de canalización de conjunto, como Decode, Validate, etcetera. Los comportamientos de WCF se pueden conectar en el flujo de mensajes en cualquiera de sus puntos de entrada de cuatro interceptación (descritas en breve).  
  
-   Las canalizaciones son puramente tiempo de ejecución en su funcionalidad. Aunque también lo son los comportamientos de WCF, pueden asimismo imponer restricciones relacionales o de datos sobre los valores establecidos durante la configuración desde la consola de administración de BizTalk Server.  
  
-   Las canalizaciones pueden funcionar en mensajes de BizTalk, mientras que los comportamientos de WCF funcionan en mensajes de WCF. Esto implica que la canalización puede realizar cosas como, por ejemplo, promocionar una propiedad de contexto de BizTalk, mientras que un comportamiento de WCF puede obtener acceso a una propiedad de mensaje de WCF.  
  
-   No hay ningún modelo de mensajes de varias partes en WCF ni en los adaptadores de WCF. No obstante, dado que un componente de canalización puede manipular el mensaje de BizTalk del modo que necesite, puede procesar un mensaje de varias partes si fuera necesario.  
  
## <a name="for-the-receive-locations-or-send-ports-using-the-wcf-basichttp-and-wcf-wshttp-adapters-what-type-of-encoding-should-i-select"></a>Para las ubicaciones de recepción o los puertos de envío que usen adaptadores de WCF-BasicHttp y WCF-WSHttp, ¿qué tipo de codificación se debe seleccionar?  
 Para cada uno de estos adaptadores existe un mensaje basado en HTTP y codificación de texto. La codificación de mensaje especifica el codificador de SOAP que se usa para el mensaje, que es MTOM (Mecanismo de optimización de transmisión del mensaje) o Texto. Si se selecciona Texto, debe seleccionarse una codificación de texto. Las opciones para esto son unicodeFFF (big endian), utf-16 (codificación de 16 bits) y utf-8 (codificación de 8 bits).  
  
 MTOM es el mecanismo de transferencia más eficaz y recomendado para datos binarios. No obstante, precisa que el servicio pueda procesar datos MTOM y esto hace que la opción sea mucho menos transportable que el texto sin formato. Si se usa para transferir datos estándar no binarios, MTOM puede en realidad ser menos eficiente que el uso de la opción Texto. La opción Texto se acepta universalmente y permite una mayor interoperabilidad entre plataformas, pero es la opción menos eficiente de las dos si los datos que se transmiten presentan contenido que no sea de texto. Esto es un importante factor a la hora de seleccionar una opción de codificaciones de enlace al usar contratos de Servicio WCF. Conocer los datos que van a transferir y procesar las operaciones de WCF afecta a la opción correcta para la codificación de mensajes.