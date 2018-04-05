---
title: Arquitecturas de ejemplo para pequeñas &amp; medianas empresas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, examples
ms.assetid: fc8c2fdd-bcb1-481c-b351-03092dd48540
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fa7911b7b2da942d559f2c85ad32e896c79d174
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sample-architectures-for-small-amp-medium-sized-companies"></a>Arquitecturas de ejemplo para pequeñas &amp; medianas empresas
Esta sección ofrece una arquitectura de ejemplo en la que Microsoft BizTalk Server se implementa para proteger los activos de una pequeña o mediana empresa. Aunque estas arquitecturas fomentan la protección en profundidad y la separación de servicios para minimizar el impacto de un ataque, dan por sentadas las magnitudes de hardware, software y recursos humanos que normalmente tienen a su disposición las grandes compañías.  
  
 No obstante, las pequeñas y medianas empresas (o las grandes organizaciones con pequeñas implementaciones de BizTalk Server) también deben preocuparse de proteger sus entornos. Una vez que hemos observado cómo las empresas implementan (o pretenden implementar) las soluciones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], hemos desarrollado una arquitectura de ejemplo para pequeñas y medianas empresas que mantiene un equilibrio entre los recursos disponibles y la mayor seguridad posible. Utilice la información de esta sección como guía para planear su propia implementación. Puede que, después de evaluar sus activos y necesidades empresariales, decida adoptar otra arquitectura para su implementación de BizTalk Server.  
  
 Para que resulte más fácil ver el aspecto que tendría la arquitectura, esta sección proporciona arquitecturas de ejemplo basadas en varios adaptadores que podría usar en su entorno. Las ilustraciones muestran los componentes de la topología que son independientes de los adaptadores y los que dependen del adaptador que se usa en el entorno de BizTalk Server.  
  
 Además, se examinan escenarios de uso basados en algunos de los adaptadores que se pueden utilizar en BizTalk Server. Para ayudarle a planear y diseñar su propia arquitectura, le ofrecemos un análisis de modelo de amenaza de esta arquitectura de ejemplo. Este análisis ofrece un examen más profundo de los problemas de seguridad que pueden afectar a su empresa según los adaptadores que use para comunicarse con sus asociados.  
  
 Aunque esta sección contiene información para ayudarle a diseñar una implementación segura de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], para mejorar la seguridad de su entorno, debería considerar la posibilidad de proteger la comunicación entre los servidores del entorno.  
  
> [!IMPORTANT]
>  En esta sección se supone que no está usando la supervisión de la actividad económica (BAM). Esta característica necesita que se tengan en cuenta temas de seguridad adicionales. Esto se explica en [arquitecturas de servidor de BizTalk de ejemplo](../core/sample-biztalk-server-architectures.md).  
  
> [!NOTE]
>  Para obtener más información acerca de los adaptadores no se describe en este documento, consulte el centro de desarrollo de BizTalk Server ([http://go.microsoft.com/fwlink/?LinkId=46420](http://go.microsoft.com/fwlink/?LinkId=46420).)  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Arquitectura de ejemplo: Servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md)  
  
-   [Arquitectura de ejemplo: Los adaptadores SOAP y HTTP](../core/sample-architecture-http-and-soap-adapters.md)  
  
-   [Arquitectura de ejemplo: Message Queue Server de BizTalk](../core/sample-architecture-biztalk-message-queuing.md)  
  
-   [Arquitectura de ejemplo: Adaptador de FTP de](../core/sample-architecture-ftp-adapter.md)  
  
-   [Arquitectura de ejemplo: Adaptador de archivo de](../core/sample-architecture-file-adapter.md)