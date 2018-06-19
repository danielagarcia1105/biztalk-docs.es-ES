---
title: Uso de puertos en orquestaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, receiving
- ports, configuring manually
- send ports, messages
- ports, creating
- ports, messages
- creating, ports
- send ports, sending
- ports, operations
- configuring, ports
- ports, deleting
- deleting, ports
- orchestrations, ports
- Port Configuration Wizard [Orchestration Designer]
- ports
- ports, about ports
- ports, configuring
ms.assetid: 968b2d1b-e233-4eb0-8254-9ec6b7642cdf
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7f48c1c070e3a3a3e7ebe7e86618a4fd9ebc90d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287420"
---
# <a name="using-ports-in-orchestrations"></a>Utilizar puertos en orquestaciones
Los puertos especifican cómo la orquestación enviará los mensajes a otros procesos empresariales y cómo los recibirá de ellos. Cada puerto tiene un tipo, una dirección y un enlace, que en combinación determinan la dirección de la comunicación, el patrón de comunicación, la ubicación de destino a la que se envía el mensaje, la ubicación de origen desde la que se recibe el mensaje y cómo tiene lugar la comunicación.  
  
> [!NOTE]
>  Existe una diferencia entre un puerto y un tipo de puerto. Un puerto es una instancia de un tipo de puerto; varios puertos diferentes pueden tener el mismo tipo de puerto.  
  
 En función de estos factores, un puerto puede tener asociado un URI (una ubicación física), un transporte (ARCHIVO, HTTP, SOAP, SMTP o Message Queue Server de BizTalk), una canalización de envío para preparar un mensaje para el envío (por ejemplo, ensamblado, cifrado, compresión o cualquier otro tipo de acción en él) y una canalización de recepción para preparar un mensaje recibido para el procesamiento (por ejemplo, desensamblado, descifrado o descompresión).  
  
 Los puertos se agregan a una orquestación de forma muy similar a como se agregan controles a un formulario Web Forms o Windows Forms. También se pueden agregar puertos mediante la ventana Vista orquestación.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Patrón de comunicación](../core/communication-pattern.md)  
  
-   [Dirección de comunicación](../core/communication-direction.md)  
  
-   [Enlaces de puertos](../core/port-bindings.md)  
  
-   [Cómo usar puertos en orquestaciones](../core/how-to-use-ports-in-orchestrations.md)  
  
-   [Cómo trabajar con tipos de puerto](../core/how-to-work-with-port-types.md)  
  
-   [Cómo ejecutar al Asistente para configuración de puertos](../core/how-to-run-the-port-configuration-wizard.md)  
  
-   [Trabajar con puertos de enlace directo en orquestaciones](../core/working-with-direct-bound-ports-in-orchestrations.md)  
  
## <a name="see-also"></a>Vea también  
 [Cómo ejecutar al Asistente para configuración de puertos](../core/how-to-run-the-port-configuration-wizard.md)   
 [Usar vínculos de rol en orquestaciones](../core/using-role-links-in-orchestrations.md)