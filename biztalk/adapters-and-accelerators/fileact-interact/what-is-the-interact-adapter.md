---
title: ¿Qué es el adaptador de InterAct? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a09063df-c6c4-41b9-96a1-e5059777fa72
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fc2f29f08edda2fb8d2b0cf05f3ba5b2b786e8f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967085"
---
# <a name="what-is-the-interact-adapter"></a>¿Qué es el adaptador de InterAct?
El adaptador de interactuar de SWIFTNet proporciona conectividad entre BizTalk Server y la red de IP segura de SWIFT (SIPN) para la transferencia de mensajes. La SIPN transfiere archivos y mensajes a través de una red privada segura que interconecta las instituciones financieras, infraestructuras de la industria financiera y clientes. El adaptador de InterAct utiliza la interfaz de programación de aplicaciones (API) s para conectarse a la SIPN SWIFTNet vínculo (SNL).  
  
 Interactuar SWIFTNet proporciona exchange segura y confiable de los mensajes estructurados de financieros individuales. Requisitos de mensajería de SWIFT clientes varían de un cliente a otro, pero también de un mensaje a.  
  
 Admite la funcionalidad siguiente:  
  
- Seguridad de PKI  
  
- Validación de mensajes  
  
- Puede configurar el enrutamiento central  
  
- Prioridad del mensaje  
  
- Notificación de entrega para almacenar y reenviar mensajes  
  
- Sin repudio de emisión y recepción.  
  
  Utilice el adaptador interactuar para SWIFTNet con las aplicaciones externamente proporcionadas para utilizar las características de interacción. Este adaptador no tiene conocimiento del contenido de los mensajes a transferirse y no auditar ni validar el contenido de los mensajes, excepto para las primitivas de exchange.  
  
## <a name="interact-message-exchange"></a>Intercambio de mensajes interAct  
 Interactuar SWIFTNet proporciona exchange segura y confiable de los mensajes estructurados de financieros individuales. Requisitos de mensajería de SWIFT clientes varían de un cliente a otro, pero también de un mensaje a. Interactuar SWIFTNet ofrece una amplia variedad de modos de telecomunicaciones:  
  
- **Store y reenvío de mensajes.** Capacidad de almacenamiento y reenvío de SWIFTNet interactuar está diseñado para los mensajes destinados a un gran número de corresponsales, muchos de los cuales pueden no estar conectados a la hora de la transmisión. Quita la incertidumbre y los inconvenientes de tener que preocuparse de si son o no los corresponsales en línea en el momento de que enviar el mensaje. El mensaje se entrega tan pronto como el destinatario está listo para recibirlo. Como resultado, proporciona una manera ideal para enviar instrucciones individuales, confirmaciones y los informes a un gran número de corresponsales, algunos de los cuales pueden estar en distintas zonas horarias.  
  
- **Mensajería en tiempo real.** Mensajería en tiempo real, ofrece una alternativa de bajo costo para almacenar y reenviar mensajes que están destinados a corresponsales que están en línea en el momento de la transmisión. Como resultado, es ideal para enviar instrucciones individuales, confirmaciones y los informes, a unos corresponsales grandes o para los mensajes en el mercado de infraestructuras.  
  
  Las características opcionales de SWIFTNet interactuar (dentro de un mensaje por mensaje) incluyen:  
  
- **Prioridad del mensaje.** Los mensajes pueden marcarse como "Urgente" en el mensaje, para permitir adecuado de procesamiento por sus corresponsales.  
  
- **Notificación de entrega (modo de almacenamiento y reenvío).** Proporciona la confirmación de que el destinatario recibe el mensaje  
  
- **Sin repudio de recepción y de emisión.** En el caso de conflicto, permite SWIFT confirmar que el intercambio de mensajes tuvo lugar como reclamado.  
  
  Las características estándares de SWIFTNet interactuar incluyen seguridad SWIFTNet PKI. SWIFTNet FileAct está protegida con SWIFTNet PKI y ofrece control de integridad y autenticación de mensajes.  
  
  Todos los mensajes y los archivos que se intercambian en SWIFTNet someterse a un conjunto común de comprobaciones para asegurarse de que ningún usuario puede omitir la seguridad, validación y las reglas de enrutamiento de la plataforma. Estas comprobaciones se realizan mediante la aplicación de puerta de enlace SWIFTAlliance (SAG).  
  
## <a name="see-also"></a>Vea también  
 [Introducción a la FileAct e interactuar de adaptadores](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md)   
 [¿Qué es SWIFTNet?](../../adapters-and-accelerators/fileact-interact/what-is-swiftnet.md)   
 [¿Qué es el adaptador de FileAct?](../../adapters-and-accelerators/fileact-interact/what-is-the-fileact-adapter.md)