---
title: Planear el rendimiento de | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 267a8bc6-a0ab-4335-bc04-c22d5a56792f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fac21f0b483ac3cbaec64c48b524a17422cb146
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22303004"
---
# <a name="planning-for-performance"></a>Planificación de rendimiento
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]es una plataforma de aplicación. No es simplemente un producto de servidor o simplemente un producto de desarrollador. Es una plataforma de aplicación que se usa para crear sistemas de administración de procesos empresariales, para integrar aplicaciones empresariales, para automatizar los flujos de trabajo, y habilitar el servicio arquitecturas orientadas a.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]depende de muchos otros componentes de software. Normalmente, la plataforma de aplicaciones de BizTalk incluye algunos de los siguientes componentes de software: el sistema operativo Windows Server, SQL Server, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], externo (opcional), IIS sistemas que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está interactuando con, así como los adaptadores de terceros y componentes.  
  
 Debido a la naturaleza inherentemente compleja de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno, hay muchas consideraciones realizarse al planear el rendimiento de. Hay varias configuraciones predeterminadas que son aplicables a todos los [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entornos y existen consideraciones adicionales y metodologías disponibles para optimizar específicos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] arquitecturas.  
  
 Este tema proporciona información general sobre la configuración predeterminada que se debe aplicar al optimizar el rendimiento para todos los [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entornos. También se proporcionan recomendaciones para probar y optimizar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entornos que están diseñados para escenarios concretos.  
  
## <a name="settings-that-you-should-apply-to-all-biztalk-server-environments"></a>Configuración que se debe aplicar a todos los entornos de servidor BizTalk Server  
 El [listas de comprobación de preparación operativa](../technical-guides/operational-readiness-checklists.md) sección de esta guía contiene una lista de elementos que debe leer antes de emplear cualquier solución de BizTalk. Esta lista de comprobación contiene elementos de acción que pueden tener un impacto significativo en el rendimiento de su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno sin tener en cuenta la naturaleza específica de la solución de BizTalk que se emplea.  
  
## <a name="considerations-for-testing-and-optimizing-a-biztalk-solution"></a>Consideraciones para probar y optimizar una solución de BizTalk  
 Diferentes soluciones de BizTalk tienen criterios de rendimiento drásticamente diferentes. Por ejemplo, una solución de BizTalk que se basa en orquestaciones en ejecución tendrá un perfil de rendimiento diferentes a una solución de BizTalk que se centra en la recepción, convertir y asignar documentos de archivo sin formato. Una solución centrada en la orquestación puede ser mucho la CPU o puede llamar a los componentes personalizados que se benefician de la optimización, mientras que una solución de centrada en la asignación y conversión de archivos planos pueden consumir más memoria.  
  
 Los adaptadores y las canalizaciones que se utiliza para recibir y enviar documentos dentro y fuera de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] también se puede tener un profundo impacto en el rendimiento de la solución de BizTalk. El nivel de seguimiento de documentos requerido la solución también en gran medida afectará al rendimiento. Debido a los perfiles de rendimiento divergentes muchos que son posibles en diferentes soluciones de BizTalk, es fundamental para probar la solución de BizTalk para medir el rendimiento máximo sostenible y el rendimiento de seguimiento sostenible máximo.  
  
 Después de determinar el rendimiento máximo sostenible y el rendimiento de seguimiento sostenible máximo de la solución de BizTalk, hay pasos específicos que puede emplear para quitar los cuellos de botella en la solución de BizTalk. Para obtener más información, consulte el [Guía de rendimiento de BizTalk Server 2009](http://go.microsoft.com/fwlink/?LinkID=150492) (http://go.microsoft.com/fwlink/?LinkID=150492).  
  
## <a name="see-also"></a>Vea también  
 [Planear el nivel de servidor BizTalk Server](../technical-guides/planning-the-biztalk-server-tier.md)