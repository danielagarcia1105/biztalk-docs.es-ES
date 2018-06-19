---
title: Diferencia entre el canal del adaptador y el servicio en el SDK de adaptador LOB de WCF | Documentos de Microsoft
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
ms.openlocfilehash: 2e377568887d3d626e288fc47f82714b189d44b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225012"
---
# <a name="difference-between-adapter-channel-and-service-in-the-wcf-lob-adapter-sdk"></a>Diferencia entre el canal del adaptador y el servicio en el SDK de adaptador LOB de WCF
El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] y [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] cada uno de ellos proporcionan un conjunto de API que pueden utilizarse para exponer la funcionalidad de la aplicación para consumir las aplicaciones en el mismo equipo o a través de una red. Para elegir el marco de trabajo más adecuado, debe tener en cuenta las propiedades de la aplicación del sistema de destino que está exponiendo así como los requisitos empresariales de la funcionalidad expuesta. Este tema proporcionan instrucciones que puede usar para elegir el marco de trabajo adecuado.  
  
## <a name="when-to-write-an-adapter"></a>Cuando se escribe un adaptador  
 Considere la posibilidad de escribir un adaptador mediante la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] cuando:  
  
-   El sistema de destino sea una existente, no es*Web habilitadas para los servicios* sistema  
  
-   El sistema de destino es dinámico y puede mejorarse con nuevas operaciones  
  
-   El sistema de destino tiene una gran cantidad de metadatos  
  
-   Hay un número grande, distintos de los usuarios para los datos del sistema de destino  
  
-   Aplicaciones de consumo necesitan funcionalidad de detección de metadatos de aplicación enriquecida  
  
 Por ejemplo, si el sistema de destino contiene centenares de operaciones para administrar notificaciones sanitarios y las operaciones son dinámicas (es decir, los usuarios pueden agregar nuevas operaciones que realizan tareas adicionales), tiene sentido para exponer esta funcionalidad mediante la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. Esto garantizará que nuevas operaciones son reconocibles las aplicaciones que utilizan el adaptador. Con [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], tendría que modificar el contrato de servicio, puesto que es estático.  
  
## <a name="when-to-write-a-service"></a>Cuándo se debe escribir un servicio  
 Use la *modelo de servicio de WCF* para crear un servicio cuando:  
  
-   El sistema de destino es estático y tiene un conjunto fijo de operaciones  
  
-   El sistema de destino tiene poca o ninguna metadatos  
  
-   Los programadores del servicio tener información detallada de la aplicación que se puedan exponer  
  
-   Se expone una nueva aplicación  
  
-   Va a crear adaptadores de transporte genérico  
  
 Por ejemplo, si el sistema de destino contiene 20 operaciones para administrar equipos deportivos, puede exponer las operaciones como un contrato estática mediante [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]. De esta forma, evita tener que implementar funciones de metadatos innecesarios y potencialmente puede minimizar el tiempo de desarrollo.  
  
## <a name="when-to-write-a-channel"></a>Cuándo se debe escribir un canal  
 Use la *modelo del canal WCF* para crear un canal cuando:  
  
-   Creación de un protocolo de conexión. Ejemplos de protocolos de conexión incluyen el protocolo WS-ReliableMessaging.  
  
-   Enviar y recibir mensajes WCF a través de un transporte que no sea de los que se incluyen en WCF (TCP, HTTP, canalizaciones con nombre, MSMQ y PeerChannel). Por ejemplo, puede escribir un transporte UDP, TIBCO o un transporte de servicio de mensajería Java (JMS).  
  
-   Integración con un sistema que no se expone como un servicio Web.  En este caso, su transporte actúa como un adaptador adaptar los mensajes de WCF para el formato del mensaje del sistema existente o API que permite que a un cliente de WCF para comunicarse directamente con el sistema existente. Un ejemplo de esto es el transporte TCP de Web Services Enhancement (WSE) 3.0.  
  
## <a name="see-also"></a>Vea también  
 [Planear y diseñar un adaptador mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)   
 [Comprender el sistema LOB con el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/understand-the-lob-system-with-the-wcf-lob-adapter-sdk.md)