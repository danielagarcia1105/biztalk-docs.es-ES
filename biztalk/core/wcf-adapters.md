---
title: Adaptadores de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e64cd189-8805-4209-bd06-971363f38585
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb77124dbad631cd521a285ff4f036e0545ca819
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="wcf-adapters"></a>Adaptadores de WCF

## <a name="overview"></a>Información general
Los adaptadores de BizTalk para Windows Communication Foundation (WFC) permiten que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se comunique con aplicaciones basadas en WCF. Los adaptadores de WCF de BizTalk incluyen cinco adaptadores físicos que representan los enlaces predefinidos de WCF:**BasicHttpBinding**, **WsHttpBinding**, **NetTcpBinding**,  **NetNamedPipeBinding**, y **NetMsmqBinding**. Se proporcionan adaptadores de WCF para los enlaces predefinidos para permitir configurar de forma sencilla la información necesaria para la mayoría de los requisitos de la aplicación.  
  
 Asimismo, los adaptadores de WCF de BizTalk incorporan dos adaptadores que permiten configurar libremente la información de comportamiento y el enlace de WCF para la ubicación de recepción y el puerto de envío.  

## <a name="available-wcf-adapters"></a>Adaptadores WCF disponibles
    
-   **Adaptador de WCF-WSHttp**. proporciona compatibilidad de los estándares WS-* a través de transporte HTTP. Este adaptador implementa las especificaciones siguientes: WS-Transaction para las interacciones de transacciones entre aplicaciones externas y la base de datos de cuadro de mensaje y WS-Security para la seguridad y la autenticación de mensajes. El transporte es HTTP o HTTPS y los mensajes tienen codificación de texto o de Message Transmission Optimization Mechanism (MTOM).  
  
-   **Adaptador de WCF-BasicHttp**. se comunica con servicios y clientes Web basados en ASMX y con otros servicios compatibles con el Perfil básico de servicios Web WS-I, versión 1.1. El transporte es HTTP o HTTPS y los mensajes tienen una codificación de texto.  
  
-   **Adaptador de WCF-NetTcp**. proporciona compatibilidad de los estándares WS-* a través de transporte TCP. Este adaptador ofrece una comunicación eficaz en un entorno de WCF a WCF. El adaptador implementa las especificaciones siguientes: WS-Transaction para las interacciones de transacciones entre aplicaciones externas y la base de datos de cuadro de mensajes y WS-Security para la autenticación y seguridad de los mensajes. El transporte es TCP y codificación de mensajes es la codificación binaria.  
  
-   **Adaptador de WCF-NetMsmq**. admite el tratamiento de colas mediante el aprovechamiento de [!INCLUDE[btsCoName](../includes/btsconame-md.md)] Message Queuing (MSMQ) como transporte y permite la compatibilidad con aplicaciones de acoplamiento flexible, aislamiento de errores, nivelación de cargas y operaciones desconectadas.  
  
-   **Adaptador de WCF-NetNamedPipe**. proporciona una optimización segura para la comunicación entre procesos en el equipo. Este adaptador usa seguridad de transporte para la seguridad de transferencia, canalizaciones con nombre para la entrega de mensajes y codificación binaria de mensajes.  
  
-   **Adaptador de WCF-Custom**. permite el uso de características de extensibilidad de WCF. El adaptador permite seleccionar y configurar enlaces de WCF y la información de comportamiento de la ubicación de recepción y el puerto de envío.  
  
-   **Adaptador de WCF-CustomIsolated**. permite el uso de características de extensibilidad de WCF a través del transporte HTTP. El adaptador permite seleccionar y configurar enlaces de WCF y la información de comportamiento de la ubicación de recepción que se ejecuta en un host aislado.  
  
 Además, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona el Asistente para publicación de Servicio WCF de BizTalk y el Asistente para consumición del Servicio WCF de BizTalk. Puede usar el Asistente para publicación de Servicio WCF de BizTalk para crear y publicar orquestaciones de BizTalk como servicios WCF y publicar esquemas como servicios WCF. El Asistente para consumición del Servicio WCF de BizTalk se usa para generar los artefactos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], como tipos y orquestaciones, necesarios para consumir un Servicio WCF basado en el documento de metadatos del Servicio WCF.  
  
 En esta sección se proporcionan recursos para ayudarle a configurar e implementar los adaptadores de WCF.  
  
## <a name="next"></a>Siguiente 
  
-   [¿Cuáles son los adaptadores de WCF?](../core/what-are-the-wcf-adapters.md)  
  
-   [Configurar los adaptadores de WCF](../core/configuring-the-wcf-adapters.md)  
  
-   [Adaptador de WCF-BasicHttp](../core/wcf-basichttp-adapter.md)  
  
-   [Adaptador de WCF-WSHttp](../core/wcf-wshttp-adapter.md)  
  
-   [Adaptador de WCF-NetTcp](../core/wcf-nettcp-adapter.md)  
  
-   [Adaptador de WCF-NetMsmq](../core/wcf-netmsmq-adapter.md)  
  
-   [Adaptador de WCF-NetNamedPipe](../core/wcf-netnamedpipe-adapter.md)  
  
-   [Adaptador de WCF-Custom](../core/wcf-custom-adapter.md)  
  
-   [Adaptador de WCF-CustomIsolated](../core/wcf-customisolated-adapter.md)  
  
## <a name="see-also"></a>Vea también  
 [Uso de servicios WCF](../core/using-wcf-services.md)   