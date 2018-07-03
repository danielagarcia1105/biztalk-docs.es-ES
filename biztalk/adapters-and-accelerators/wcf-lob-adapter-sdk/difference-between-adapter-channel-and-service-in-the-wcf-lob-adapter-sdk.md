---
title: Diferencia entre el canal del adaptador y el servicio en el SDK de adaptador LOB de WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24d41d96-0ea1-4a97-bd45-b65afdbbd923
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8583b615e6a6e8fcd999e5120bca531d3c74090d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010039"
---
# <a name="difference-between-adapter-channel-and-service-in-the-wcf-lob-adapter-sdk"></a>Diferencia entre el canal del adaptador y el servicio en el SDK de adaptador LOB de WCF
El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] y [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] cada una proporciona un conjunto de API que se pueden usar para exponer la funcionalidad de la aplicación para consumir las aplicaciones en el mismo equipo o a través de una red. Para elegir el marco de trabajo más adecuada, debe tener en cuenta las propiedades de la aplicación del sistema de destino que está exponiendo, así como los requisitos empresariales de la funcionalidad expuesta. Este tema proporciona directrices que puede usar para elegir el marco de trabajo adecuado.  
  
## <a name="when-to-write-an-adapter"></a>Cuándo se debe escribir un adaptador  
 Considere la posibilidad de escribir un adaptador mediante el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] cuando:  
  
- El sistema de destino es una existente, que no sean de*Web habilitadas para los servicios* sistema  
  
- El sistema de destino es dinámico y se puede mejorar con nuevas operaciones  
  
- El sistema de destino tiene una gran cantidad de metadatos  
  
- Hay un número grande, diverso de usuarios para los datos del sistema de destino  
  
- Aplicaciones de consumo necesitan la funcionalidad de detección de metadatos de aplicación enriquecida  
  
  Por ejemplo, si el sistema de destino contiene centenares de operaciones para administrar las reclamaciones de atención médica y las operaciones son dinámicas (es decir, los usuarios pueden agregar nuevas operaciones que llevan a cabo tareas adicionales), tiene sentido para exponer esta funcionalidad mediante el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. Esto garantizará que nuevas operaciones son reconocibles en las aplicaciones que utilizan el adaptador. Con [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], tendría que modificar el contrato de servicio porque es estático.  
  
## <a name="when-to-write-a-service"></a>Cuándo se debe escribir un servicio  
 Use la *modelo de servicio WCF* para crear un servicio cuando:  
  
- El sistema de destino es estático y tiene un conjunto fijo de operaciones  
  
- El sistema de destino tiene poca o ninguna de metadatos  
  
- Los desarrolladores de servicios tienen información detallada de la aplicación se exponga  
  
- Exposición de una aplicación nueva  
  
- Creación de adaptadores de transporte genérico  
  
  Por ejemplo, si el sistema de destino contiene 20 operaciones para administrar equipos deportivos, puede exponer las operaciones de forma estática del contrato utilizando [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]. Al hacerlo, evita tener que implementar funciones de metadatos innecesarios y potencialmente puede minimizar el tiempo de desarrollo.  
  
## <a name="when-to-write-a-channel"></a>Cuándo se debe escribir un canal  
 Use la *modelo del canal WCF* para crear un canal cuando:  
  
-   Creación de un protocolo de conexión. Ejemplos de protocolos de conexión que incluyen WS-ReliableMessaging protocolo.  
  
-   Enviar y recibir mensajes WCF a través de un transporte que no sean las que se incluyen en WCF (TCP, HTTP, canalizaciones con nombre, MSMQ y PeerChannel). Por ejemplo, puede escribir un transporte UDP, TIBCO o un transporte de servicio de mensajería de Java (JMS).  
  
-   La integración con un sistema que no se expone como un servicio Web.  En este caso, el transporte actúa como un adaptador adaptar los mensajes de WCF en formato de mensaje del sistema existente o API que permite que a un cliente WCF para comunicarse directamente con el sistema existente. Un ejemplo de esto es el transporte TCP de Web Services Enhancement (WSE) 3.0.  
  
## <a name="see-also"></a>Vea también  
 [Planear y diseñar un adaptador mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)   
 [Comprender el sistema LOB con el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/understand-the-lob-system-with-the-wcf-lob-adapter-sdk.md)