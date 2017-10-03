---
title: "Diseñar una arquitectura segura | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- firewalls
- architecture, security
- installation, firewalls
- installation, security
ms.assetid: 93df6a3f-396c-4767-99c8-2145bddf8fdf
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 157c11477efb9dec455e9ac2de81736cd4ea72ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="designing-a-secure-architecture"></a>Diseñar una arquitectura segura
Para obtener información completa sobre la arquitectura del sistema para la implementación de BizTalk Server, vea [arquitecturas de servidor de BizTalk de ejemplo](../core/sample-biztalk-server-architectures.md).  
  
 La arquitectura presentada en el tema [arquitectura distribuida de gran tamaño](../core/large-distributed-architecture.md) soluciona muchas de las posibles amenazas de seguridad a la que el entorno de BizTalk es vulnerable. No obstante, para determinar qué arquitectura es la que más le conviene, es necesario evaluar las necesidades de su empresa, los peligros a los que se enfrenta el negocio y los recursos disponibles para proteger los activos y mitigar las posibles amenazas. Esta sección ofrece opciones de seguridad adicionales que puede tomar en consideración a la hora de diseñar la arquitectura de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="firewalls"></a>Firewalls  
 Para restringir el acceso a los recursos de su entorno, puede utilizar servidores de seguridad físicos (de hardware) o de software. Aunque en el tema [arquitectura distribuida de gran tamaño](../core/large-distributed-architecture.md) usa Forefront Threat Management Gateway (TMG) 2010 server, puede crear una arquitectura similar mediante el uso de hardware o firewalls de software de terceros, siempre y cuando se abre y configurar los puertos necesarios para la comunicación entre los distintos componentes de BizTalk Server. Para obtener más información acerca de los puertos que utiliza BizTalk Server, vea [los puertos necesarios para que BizTalk Server](../core/required-ports-for-biztalk-server.md).  
  
## <a name="active-directory"></a>Active Directory  
 En la implementación de ejemplo, se utiliza el servicio de directorio Active Directory® para crear un límite de seguridad entorno a cada grupo de servidores. La confianza unidireccional, permite proporcionar aún más protección al entorno de BizTalk Server contra ataques debidos a errores de otras aplicaciones que no son de BizTalk Server y que se ejecutan en los servidores de procesamiento, ya que las aplicaciones de BizTalk Server se ejecutan en cuentas creadas en el dominio de datos. Como el dominio de datos no confía en ninguna cuenta de ningún otro dominio, el entorno de BizTalk Server se mantiene protegido aunque se produzcan ataques contra las cuentas de otro dominio.  
  
## <a name="ipsec-and-ssl"></a>IPSec y SSL  
 Si es necesario proteger el entorno de amenazas graves con el nivel de protección que proporcionan los servidores de seguridad, pero los segmentos de la red que conectan los dominios de servicios, procesamiento y datos no están protegidos físicamente de los diversos ataques contra la red (por ejemplo, los husmeadores de paquetes o la manipulación de datos), tendrá que proteger los datos en su tránsito de un servidor a otro. En este caso, puede usar la seguridad de Protocolo Internet (IPSec) o de Capa de sockets seguros (SSL) para cifrar el tráfico entre servidores.  
  
## <a name="see-also"></a>Vea también  
 [Diseñar una arquitectura distribuida](../core/designing-a-distributed-architecture.md)   
 [Planear la seguridad](../core/planning-for-security.md)   
 [Diseñar las arquitecturas de sistema de BizTalk Server](../core/designing-the-system-architectures-for-biztalk-server.md)   
 [Arquitecturas de BizTalk Server de ejemplo](../core/sample-biztalk-server-architectures.md)