---
title: Trabajar con puertos de enlace directo en orquestaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03a37ac0-5131-4d37-b60b-56763c460463
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e7b2b59ccdaa23271ee0707f19f4fd2cddc0508
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="working-with-direct-bound-ports-in-orchestrations"></a>Trabajar con puertos de enlace directo en orquestaciones
Hay tres tipos de puertos de enlace directo: cuadro de mensajes, autocorrelación y orquestación de socio.  
  
 Los puertos de enlace directo de cuadro de mensajes permiten patrones de diseño de publicación-suscripción. Los mensajes que se envían por un puerto de enlace directo de cuadro de mensajes se publican en la base de datos de cuadro de mensajes, donde los destinatarios los toman según las suscripciones. Los puertos de recepción lógicos configurados como puertos de enlace directo de cuadro de mensajes obtienen los mensajes directamente desde la base de datos de cuadro de mensajes. Para activar **recepción** formas, el cuadro de mensajes directa enlazado reciban puertos get los mensajes a través de suscripciones para el tipo de mensaje y la expresión de filtro. Para no activar **recepción** formas, el cuadro de mensajes directa enlazado reciban puertos get los mensajes a través de suscripciones para el tipo de mensaje y el conjunto de correlaciones.  
  
 Los puertos de enlace directo de autocorrelación le ayudan a diseñar una comunicación asíncrona entre orquestaciones. Los mensajes que se envían a un puerto de enlace directo de autocorrelación se enrutan a la instancia de la orquestación que ha creado el extremo receptor del puerto de enlace directo de autocorrelación.  
  
 Los puertos de enlace directo de orquestación de socio facilitan la comunicación entre orquestaciones. Los mensajes que se envían por un puerto de enlace directo de orquestación de socio se pueden enviar a la orquestación de un destinatario específico, y los mensajes que se reciben en un puerto de enlace directo de orquestación de socio pueden recibirse desde la orquestación de un remitente específico.  
  
 Aunque con el enlace directo parece que el mensaje va directamente de una orquestación a otra, en realidad todos los mensajes que se envían a través de cualquier tipo de puerto lógico viajan siempre a través de la base de datos de cuadro de mensajes. Por añadidura, los puertos de enlace directo no son más que puertos lógicos, de modo que el enlace directo es tan solo una característica de configuración en tiempo de diseño. Un puerto de enlace directo no se puede enlazar a un puerto físico y la configuración de enlace únicamente puede cambiarse en tiempo de diseño.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo usar el cuadro de mensajes directamente puertos de enlace](../core/how-to-use-messagebox-direct-bound-ports.md)  
  
-   [Puertos de enlace de uso directo de autocorrelación](../core/how-to-use-self-correlating-direct-bound-ports.md)  
  
-   [Cómo utilizar la orquestación de socio directo puertos de enlace](../core/how-to-use-partner-orchestration-direct-bound-ports.md)  
  
## <a name="see-also"></a>Vea también  
 [Enlaces de puertos](../core/port-bindings.md)