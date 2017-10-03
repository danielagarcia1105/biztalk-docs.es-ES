---
title: "Configurar puertos para una solución AS2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 715358b1-4226-476b-b0de-2b91434aa24c
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8f02c5de0edd7956f00e10ce8782e4865033076
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-ports-for-an-as2-solution"></a>Configurar puertos para una solución AS2
Puede usar los siguientes puertos de recepción y envío para transmitir mensajes EDI y no pertenecientes a EDI a través de AS2:  
  
 **Puertos de recepción**  
  
|Para recibir|Para enviar|Tipo de puerto|  
|----------------|-------------|------------------|  
|Un mensaje o confirmación EDI o no perteneciente a EDI|Una respuesta MDN (si se encuentra en modo sincrónico) o una respuesta HTTP (si se encuentra en modo asíncrono)|Puerto de recepción HTTP de solicitud-respuesta bidireccional|  
|Una respuesta MDN|-|Puerto de recepción HTTP unidireccional|  
  
 **Puertos de envío**  
  
|Para enviar|Para recibir|Tipo de puerto|  
|-------------|----------------|------------------|  
|Un mensaje o confirmación EDI o no perteneciente a EDI<br /><br /> (enrutamiento basado en acuerdo)|-|Puerto de envío HTTP unidireccional estático|  
|Un mensaje o confirmación EDI o no perteneciente a EDI<br /><br /> (enrutamiento por contenidos)|Una respuesta MDN|Puerto de envío HTTP de petición-respuesta bidireccional dinámico|  
|Un mensaje o confirmación EDI o no perteneciente a EDI<br /><br /> (enrutamiento por contenidos)|-|Puerto de envío HTTP unidireccional dinámico|  
|Una respuesta MDN asíncrona<br /><br /> (enrutamiento por contenidos)|-|Puerto de envío unidireccional dinámico|  
|Una respuesta MDN asíncrona|-|Puerto de envío unidireccional estático|  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Configurar un puerto de recepción de mensajes a través de AS2](../core/configuring-a-receive-port-for-messages-over-as2.md)  
  
-   [Configurar un puerto de recepción para MDN entrantes](../core/configuring-a-receive-port-for-incoming-mdns.md)  
  
-   [Configurar un puerto de envío estático para mensajes a través de AS2](../core/configuring-a-static-send-port-for-messages-over-as2.md)  
  
-   [Configurar un puerto de envío dinámico para mensajes a través de AS2](../core/configuring-a-dynamic-send-port-for-messages-over-as2.md)  
  
-   [Configurar un puerto de envío estático para MDN asíncronos a través de AS2](../core/configuring-a-static-send-port-for-asynchronous-mdns-over-as2.md)  
  
-   [Configurar un puerto de envío dinámico para MDN asíncronos a través de AS2](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md)  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar y configurar soluciones AS2 de BizTalk Server](../core/developing-and-configuring-biztalk-server-as2-solutions.md)