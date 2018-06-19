---
title: Diseñar una arquitectura distribuida | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- clustering, SQL Servers
- SQL Server, clustering
ms.assetid: 8a8f1710-4d53-42bf-b5e5-2be3b43813b4
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 156c7107abfd0fd140a5e7b07f06d00eabf7c961
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239428"
---
# <a name="designing-a-distributed-architecture"></a>Diseñar una arquitectura distribuida
Para obtener información completa sobre la arquitectura del sistema para la implementación de BizTalk Server, vea [arquitecturas de servidor de BizTalk de ejemplo](../core/sample-biztalk-server-architectures.md).  
  
 La arquitectura presentada en el tema [arquitectura distribuida de gran tamaño](../core/large-distributed-architecture.md) soluciona muchas de las posibles amenazas de seguridad a la que el entorno de BizTalk es vulnerable. Aunque la seguridad debe ocupar un puesto importante en su lista de prioridades a la hora de diseñar la arquitectura, en un entorno distribuido, hay que tener en cuenta otros factores como la alta disponibilidad, la escalabilidad y el rendimiento. Esta sección ofrece opciones adicionales que puede tomar en consideración a la hora de diseñar la arquitectura de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="domains"></a>Dominios  
 Si las comunicaciones de la compañía se realizan principalmente con Internet, puede quitar los servicios de intranet del dominio corporativo. Por el contrario, si utiliza BizTalk Server para conectarse a otras aplicaciones o socios comerciales que se conectan a través de la intranet, puede prescindir de la red perimetral. Si la compañía realiza comunicaciones tanto en Internet como en la intranet con un número reducido de socios, es posible que sea conveniente combinar los servicios de la intranet y la red perimetral.  
  
 Si desea minimizar el período de latencia en la comunicación entre los servidores de procesamiento y los servidores SQL en el dominio de datos, y no le preocupan los problemas de seguridad como los husmeadores de redes, la manipulación de paquetes y la suplantación de host en la red interna, puede eliminar el servidor de seguridad entre el dominio de procesamiento y el dominio de datos, y combinar ambos dominios. Se recomienda el uso de la seguridad de Protocolo Internet (IPSec) o de Capa de sockets seguros (SSL) para proteger los datos en su tránsito de un servidor a otro.  
  
## <a name="sql-server-clustering"></a>Organización por clústeres de SQL Server  
 Aunque no se describe detalladamente en esta sección, se recomienda organizar las bases de datos por clústeres como protección contra la conmutación por error. Para obtener más información acerca de los clústeres de conmutación por error de SQL Server 2008, vea el sitio Web de Microsoft MSDN en [http://go.microsoft.com/fwlink/?LinkId=131016](http://go.microsoft.com/fwlink/?LinkId=131016).  
  
## <a name="messagebox-database"></a>Base de datos de cuadro de mensajes  
 Según los requisitos de rendimiento para los mensajes de la organización, puede que necesite agregar (o quitar) bases de datos de cuadro de mensajes. Para obtener más información sobre el cuadro de mensajes múltiples, consulte [bases de datos de Scaled-Out](../core/scaled-out-databases.md).  
  
## <a name="see-also"></a>Vea también  
 [Diseñar una arquitectura segura](../core/designing-a-secure-architecture.md)   
 [Planeamiento para alta disponibilidad](../core/planning-for-high-availability3.md)   
 [Planear el rendimiento sostenido de](../core/planning-for-sustained-performance.md)   
 [Diseñar las arquitecturas de sistema de BizTalk Server](../core/designing-the-system-architectures-for-biztalk-server.md)   
 [Arquitecturas de BizTalk Server de ejemplo](../core/sample-biztalk-server-architectures.md)