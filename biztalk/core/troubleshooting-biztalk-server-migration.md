---
title: "Solución de problemas de migración de BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e6eddc0a-2403-4bcd-9327-23f51ce7d57b
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1dcdb53c7123b4ffaa2294db080e1efc4fb4eb65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-biztalk-server-migration"></a>Solución de problemas de migración de BizTalk Server
En esta sección se proporciona una ubicación centralizada para la información acerca de los problemas comunes que suelen producirse al migrar aplicaciones de BizTalk de [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] o [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009 a [!INCLUDE[prague](../includes/prague-md.md)].  
  
## <a name="known-issues"></a>Problemas conocidos  
  
#### <a name="custom-applications-might-not-work-while-upgrading"></a>Las aplicaciones personalizadas no funcionan durante la actualización  
  
##### <a name="problem"></a>Problema  
 Al actualizar de [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] o [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009 a [!INCLUDE[prague](../includes/prague-md.md)], es posible que algunas aplicaciones personalizadas no funcionen.  
  
##### <a name="cause"></a>Causa  
 Todos los componentes de código administrado de BizTalk se ejecutan en CLR 4.0. Dado que estos componentes se compilan con [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)], necesitan un archivo de configuración para ejecutarse en CLR 4.0.  
  
##### <a name="solution"></a>Solución  
 Para resolver este problema, actualice el archivo de configuración.  
  
```  
<configuration>  
<startup useLegacyV2RuntimeActivationPolicy="true">  
<supportedRuntime version="v4.0" />  
</startup>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 [Solucionar problemas](../core/troubleshooting.md)