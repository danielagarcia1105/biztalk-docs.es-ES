---
title: ¿Qué es el marco de trabajo de adaptadores? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd1e2fd7-4e77-49c4-839d-c2bf16b10ba2
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7efa468cd21720ae04dc34197f790863fadaeb91
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995949"
---
# <a name="what-is-the-adapter-framework"></a>¿Qué es el marco de trabajo de adaptadores?
El adaptador de BizTalk Framework ofrece un mecanismo estable y abierto para todos los adaptadores implementen u obtener acceso a trabajo desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] motor de mensajería. Las interfaces se describen en el **Microsoft.BizTalk.Adapter.Framework** espacio de nombres permiten a los adaptadores proporcionan un medio para modificar las páginas de propiedades de configuración. Además, se trata de un medio para importar servicios y esquemas en el proyecto de BizTalk.  
  
 En la siguiente ilustración se muestra cómo funcionan conjuntamente un adaptador y el entorno de adaptador para conectar la aplicación a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 ![El marco de trabajo de adaptador](../core/media/ebiz-sdk-adpttoday.gif "ebiz_sdk_adpttoday")  
  
 Los siguientes pasos describen la secuencia de pasos indicados en esta ilustración:  
  
1. Los datos se reciben desde una ubicación de recepción que escucha mensajes con un protocolo concreto en una dirección específica. La ubicación de recepción está asociada con un adaptador y una canalización de recepción. Puede configurar el adaptador y los componentes de canalización para llevar a cabo cierta lógica en los mensajes de un protocolo predeterminado.  
  
2. Tras recibir el mensaje la ubicación de recepción, se envía éste al adaptador, que crea un mensaje nuevo de BizTalk, agrega la secuencia de datos al mensaje (normalmente al cuerpo del mensaje), agrega cualquier metadato perteneciente al extremo en el que se han recibido los datos y envía dicho mensaje al motor de mensajería.  
  
3. El motor de mensajería envía el mensaje a la canalización de recepción donde los datos se transforman en XML, se autentica el remitente del mensaje, se descifra y se valida el código XML.  
  
4. El motor de mensajería publica el mensaje en la base de datos de cuadro de mensajes. El cuadro de mensajes es un Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] tabla que contiene mensajes para procesarlos. Tanto las orquestaciones como los puertos de envío se pueden suscribir al Cuadro de mensajes.  
  
5. El motor de mensajería envía el mensaje a una orquestación o a un suscriptor de puerto de envío según si las propiedades de contexto del mensaje coinciden con las especificaciones establecidas en el filtro del suscriptor.  
  
6. Si una orquestación es el suscriptor, procesa el mensaje y lo envía a través de un puerto de envío. Si el suscriptor es un envío, el mensaje se transfiere a través de la canalización de envío en un adaptador de envío antes de transmitirlo.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Uso de las herramientas de marco de trabajo de adaptadores](../core/using-the-adapter-framework-tools.md)  
  
-   [Patrones de intercambio de mensajes de adaptador](../core/adapter-message-exchange-patterns.md)  
  
-   [Componentes del marco de trabajo de adaptadores](../core/adapter-framework-components.md)  
  
-   [Modelo de hospedaje de adaptadores](../core/adapter-hosting-model.md)  
  
-   [Componentes del adaptador](../core/adapter-components.md)