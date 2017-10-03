---
title: "¿Qué es el adaptador de interactuar? | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a09063df-c6c4-41b9-96a1-e5059777fa72
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25877b95a440faef802d3d2ba7861687d7e4b108
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-interact-adapter"></a>¿Qué es el adaptador de interactuar?
El adaptador interactuar para SWIFTNet proporciona conectividad entre BizTalk Server y la red de IP seguros de SWIFT (SIPN) para la transferencia de mensajes. La SIPN transfiere los mensajes y archivos a través de una red privada segura que interconecta instituciones financieras, infraestructuras de sector financiero y los clientes. El adaptador de InterAct utiliza la interfaz de programación de aplicaciones (API) s para conectarse a la SIPN SWIFTNet vínculo (SNL).  
  
 SWIFTNet interactuar proporciona exchange segura y confiable de los mensajes individuales estructurados financieros. Requisitos de mensajería de los clientes SWIFT varían de un cliente a otro, pero también de un mensaje a.  
  
 Admite la funcionalidad siguiente:  
  
-   Seguridad PKI  
  
-   Validación del mensaje  
  
-   Puede configurar el enrutamiento central  
  
-   Prioridad del mensaje  
  
-   Notificación de entrega para almacenar y reenviar mensajes  
  
-   Sin rechazo de recepción y de emisión.  
  
 Utilice el adaptador interactuar para SWIFTNet con las aplicaciones externamente proporcionadas para usar las características de interacción. Este adaptador no tiene conocimiento del contenido de los mensajes a transferirse y no de auditoría ni validar el contenido de los mensajes, excepto para las primitivas de exchange.  
  
## <a name="interact-message-exchange"></a>Intercambio de mensajes interAct  
 SWIFTNet interactuar proporciona exchange segura y confiable de los mensajes individuales estructurados financieros. Requisitos de mensajería de los clientes SWIFT varían de un cliente a otro, pero también de un mensaje a. SWIFTNet interactuar ofrece una amplia variedad de modos de telecomunicaciones:  
  
-   **Mensajería de almacenamiento y reenvío.** Capacidad de almacenamiento y reenvío de SWIFTNet interactuar está diseñado para los mensajes destinados a un gran número de correspondientes, muchos de los cuales pueden no estar conectados a la hora de la transmisión. Quita la incertidumbre y los inconvenientes de tener que preocuparse de si son o no sus correspondientes en línea en el momento de que enviar el mensaje. El mensaje se entrega en cuanto el destinatario está listo para recibirlo. Como resultado, proporciona una forma ideal de enviar instrucciones individuales, las confirmaciones y los informes a un gran número de correspondientes, algunos de los cuales pueden ser en zonas horarias diferentes.  
  
-   **Mensajería en tiempo real.** Mensajería en tiempo real ofrece una alternativa de bajo costo para almacenar y reenviar mensajes que están destinados a correspondientes que están en línea en el momento de la transmisión. Como resultado, es ideal para enviar instrucciones individuales, las confirmaciones y los informes, a unos correspondientes grandes o para los mensajes en el mercado de infraestructuras.  
  
 Las características de interactuar SWIFTNet opcionales (en forma de mensaje por mensaje) incluyen:  
  
-   **Prioridad del mensaje.** Los mensajes se pueden marcar como "Urgente" en el mensaje, para permitir adecuado de procesamiento por sus correspondientes.  
  
-   **Notificación de entrega (modo de almacenamiento y reenvío).** Proporciona la confirmación de que el destinatario recibe el mensaje  
  
-   **Sin rechazo de recepción y de emisión.** En caso de conflicto, permite SWIFT confirmar que el intercambio de mensajes tuvo lugar como reclamado.  
  
 Las características estándares de interactuar SWIFTNet incluyen seguridad SWIFTNet PKI. SWIFTNet FileAct se protege con SWIFTNet PKI y ofrece control de integridad y autenticación de mensajes.  
  
 Todos los mensajes y archivos intercambiados en SWIFTNet debe someterse a un conjunto común de comprobaciones para asegurarse de que ningún usuario puede omitir la seguridad, validación y las reglas de enrutamiento de la plataforma. Estas comprobaciones se realizan mediante la aplicación de puerta de enlace de SWIFTAlliance (SAG).  
  
## <a name="see-also"></a>Vea también  
 [Introducción a la FileAct e interactuar adaptadores](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md)   
 [¿Qué es SWIFTNet?](../../adapters-and-accelerators/fileact-interact/what-is-swiftnet.md)   
 [¿Qué es el adaptador de FileAct?](../../adapters-and-accelerators/fileact-interact/what-is-the-fileact-adapter.md)