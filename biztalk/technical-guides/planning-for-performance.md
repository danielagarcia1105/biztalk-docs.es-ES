---
title: Planear el rendimiento de | Microsoft Docs
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
ms.openlocfilehash: 452dd1a8a038ab151b98aac8ce6c4f93641f7361
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752716"
---
# <a name="planning-for-performance"></a>Planear el rendimiento
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es una plataforma de aplicaciones. No es simplemente un producto de servidor o un solo producto para desarrolladores. Es una plataforma de aplicaciones que se usa para crear sistemas de administración de procesos empresariales, para integrar aplicaciones empresariales, para automatizar los flujos de trabajo, y habilitar el servicio de arquitecturas orientadas a servicios.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] depende de muchos otros componentes de software. Normalmente, la plataforma de aplicaciones de BizTalk incluye algunos de los siguientes componentes de software: el sistema operativo Windows Server, SQL Server, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], externo (opcional), IIS sistemas que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está interactuando con, así como los adaptadores que no sean de Microsoft y componentes.  
  
 Debido a la naturaleza compleja de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno, hay muchas consideraciones que debe hacerse al planear el rendimiento. Hay varios parámetros predeterminados que son aplicables a todos los [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entornos y hay consideraciones adicionales y metodologías para optimizar específico [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] arquitecturas.  
  
 En este tema proporciona información general sobre la configuración predeterminada que se debe aplicar al optimizar el rendimiento para todos los [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entornos. También se proporcionan recomendaciones para las pruebas y optimización [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entornos que están diseñados para escenarios específicos.  
  
## <a name="settings-that-you-should-apply-to-all-biztalk-server-environments"></a>Configuración que se debe aplicar a todos los entornos de servidor BizTalk Server  
 El [listas de comprobación de preparación operativa](../technical-guides/operational-readiness-checklists.md) sección de esta guía contiene una lista de elementos que debe revisar antes de emplear cualquier solución de BizTalk. Esta lista de comprobación contiene elementos de acción que pueden tener un impacto significativo en el rendimiento de su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno independientemente de la naturaleza específica de la solución de BizTalk que se emplea.  
  
## <a name="considerations-for-testing-and-optimizing-a-biztalk-solution"></a>Consideraciones para probar y optimizar una solución de BizTalk  
 Soluciones de BizTalk diferentes tengan criterios de rendimiento muy diferentes. Por ejemplo, una solución de BizTalk que se basa en orquestaciones en ejecución tendrán un perfil de rendimiento diferente que una solución de BizTalk que se centra en la recepción, convertir y asignar documentos de archivo sin formato. Una solución centrada en la orquestación puede ser mucho la CPU o puede llamar a componentes personalizados que se benefician de optimización, mientras que una solución de centrado en la asignación y conversión de archivo sin formato pueden ser más intensivo de memoria.  
  
 Los adaptadores y las canalizaciones que se utiliza para recibir y enviar documentos dentro y fuera de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] también se puede tener un impacto profundo en el rendimiento de la solución de BizTalk. El nivel de seguimiento de documentos requerido la solución también en gran medida afectará al rendimiento. Debido a los perfiles de rendimiento divergente muchos que son posibles en diferentes soluciones de BizTalk, es absolutamente crítico que probar la solución de BizTalk para medir el rendimiento de seguimiento sostenible máximo y el rendimiento máximo sostenible.  
  
 Después de determinar el rendimiento sostenible máximo y el rendimiento de seguimiento sostenible máximo de la solución de BizTalk, hay pasos específicos que puede emplear para eliminar cuellos de botella en la solución de BizTalk. Para obtener más información, consulte el [Guía de rendimiento de BizTalk Server 2009](http://go.microsoft.com/fwlink/?LinkID=150492) (http://go.microsoft.com/fwlink/?LinkID=150492).  
  
## <a name="see-also"></a>Vea también  
 [Planificación del nivel de BizTalk Server](../technical-guides/planning-the-biztalk-server-tier.md)