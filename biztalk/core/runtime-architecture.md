---
title: Arquitectura del Runtime | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- runtime, architecture
- architecture, runtime
- runtime
ms.assetid: feff9a84-f19b-44c9-8d05-8e6015bb1ef9
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e45ac745dbf6704f06f61155b3f57edfdec9e09
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268996"
---
# <a name="runtime-architecture"></a>Arquitectura en tiempo de ejecución
Antes de revisar información detallada adicional sobre los distintos componentes de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], es importante entender cómo encajan los componentes en la arquitectura global del producto. El tiempo en ejecución de BizTalk Server está basado en una arquitectura de publicación/suscripción en la que se publica un mensaje en el sistema y, a continuación, éste es recibido por uno o varios suscriptores activos. Existen distintos tipos de esta arquitectura, pero a menudo se denomina el modelo implementado en BizTalk Server *basado en contenido de publicación/suscripción*.  
  
 En un modelo de publicación/suscripción basada en contenido, los suscriptores especifican los mensajes que desean recibir con un conjunto de criterios relativos al mensaje. El mensaje se evalúa en el momento de su publicación y todos los suscriptores activos con suscripciones coincidentes (indicadas mediante expresiones de filtro) recibirán el mensaje. Sin embargo, tal y como se aplica a BizTalk Server, la denominación “basada en contenido” resulta algo inapropiada, pues los criterios utilizados para generar suscripciones no tienen que proceder del contenido del mensaje y pueden incluir también información contextual sobre el mensaje. Para obtener detalles sobre el mecanismo de suscripción, consulte [publicar y arquitectura de suscripción](../core/publish-and-subscribe-architecture.md).  
  
 En las secciones siguientes se describen los distintos componentes de la arquitectura en tiempo de ejecución de BizTalk Server.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Mensaje de BizTalk Server](../core/the-biztalk-server-message.md)  
  
-   [Ciclo de vida de un mensaje](../core/lifecycle-of-a-message.md)  
  
-   [Procesar el mensaje](../core/processing-the-message.md)  
  
-   [Mensajería de solicitud-respuesta](../core/request-response-messaging.md)  
  
-   [El motor de mensajería](../core/the-messaging-engine.md)  
  
-   [Entidades](../core/entities.md)  
  
-   [Artefactos](../core/artifacts.md)  
  
-   [Enterprise Single Sign-On (SSO)](../core/enterprise-single-sign-on-sso.md)  
  
-   [Motor de reglas de negocios](../core/business-rules-engine.md)  
  
-   [Ensamblados de BizTalk](../core/biztalk-assemblies.md)