---
title: Dirección de comunicación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- port types, communication direction
- communication direction [port types]
ms.assetid: b278325e-a1da-49a6-8332-80a5f640cc22
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d6c664643629971366805d08600677d22d7c419
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231380"
---
# <a name="communication-direction"></a>Dirección de comunicación
Cada *puerto* tiene su propia dirección de comunicación. La dirección de comunicación se utiliza junto con el patrón de comunicación del tipo de puerto para completar la definición de cómo se puede usar un puerto. La dirección de comunicación o polaridad determina la dirección en la que se transmiten los mensajes a través de ese puerto.  
  
 Si el tipo de puerto tiene un patrón de comunicación unidireccional, la dirección de comunicación puede ser de envío o recepción. Si el tipo de puerto tiene un patrón de comunicación bidireccional (Solicitud-respuesta), la dirección de comunicación puede ser de Envío-Recepción (se envía una solicitud y se recibe una respuesta) o de Recepción-Envío (se recibe una solicitud y se envía una respuesta).  
  
## <a name="see-also"></a>Vea también  
 [Patrón de comunicación](../core/communication-pattern.md)  
 [Cómo ejecutar al Asistente para configuración de puertos](../core/how-to-run-the-port-configuration-wizard.md)   
 [Uso de puertos en orquestaciones](../core/using-ports-in-orchestrations.md)