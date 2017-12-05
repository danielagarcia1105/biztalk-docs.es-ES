---
title: "Supervisión de instancias de Host | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4e7c6b80-7371-46ea-bf9c-82acb22012a3
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b41dd0e01aa1e28862a3e99cfc767b3dd6ddec3c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="monitoring-host-instances"></a>Supervisión de instancias de Host
Este tema describe supervisión instancias de host de BizTalk mediante Microsoft System Center Operations Manager.  
  
## <a name="using-threshold-rules-to-monitor-health"></a>Uso de reglas de umbral para supervisar el estado  
 El módulo de administración de BizTalk Server incorpora reglas de umbral de rendimiento que proporcionan una vista completa del estado de los hosts de BizTalk. Se proporcionan dos tipos distintos de reglas de umbral:  
  
-   Reglas que se aplican genéricamente (por ejemplo, para todos los hosts de BizTalk y a todas las bases de datos de cuadro de mensajes).  
  
-   Reglas que son específicas de un host de BizTalk determinado.  
  
 Las reglas genéricas supervisan todos los hosts de BizTalk tomando como base un umbral común. Por ejemplo, la regla de Monitor HostQ Size supervisa las colas de trabajo de todos los hosts de BizTalk tomando como base un umbral común. Si hay tres hosts diferentes, la misma regla supervisa sus colas de trabajo y alertas se producen cuando cualquiera de las colas de trabajo de host cruza el umbral común.  
  
 Reglas de específico del host de BizTalk le permiten configurar varios umbrales para distintos hosts. Por ejemplo, la regla Monitor HostQ Size – BizTalkServerApplication es una regla específica de host que supervisa la cola de trabajo del host BizTalkServerApplication. En este ejemplo puede definir un proveedor concreto de Operations Manager para la instancia de contador de rendimiento específicos y usar ese proveedor en la regla de umbral. Dado que estas reglas son específicos del host, debe definir reglas específicas para cada host recién creado.  
  
 Las reglas de específico del host de BizTalk se proporcionan como reglas de plantilla para crear reglas que son aplicables en su entorno. Todas las reglas de supervisión de umbral están deshabilitadas de forma predeterminada:  
  
-   Debe configurar las reglas genéricas con valores de umbral específicos para su entorno.  
  
-   Debe crear reglas de específico del host de BizTalk en función de los umbrales adecuados y reglas de plantilla.  
  
## <a name="monitoring-biztalk-host-instances"></a>Supervisar instancias de Host de BizTalk  
 Las reglas dirigidas a hosts específicos de BizTalk son más flexibles desde la perspectiva de supervisión. Todas las reglas de supervisión de umbral para el host de BizTalkServerApplication proporcionado en el módulo de administración de BizTalk Server son reglas de plantilla. Para usar estas reglas, debe usar la consola de administrador de Operations Manager para:  
  
-   Crear una copia de la regla de plantilla en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de reglas y cambie su nombre.  
  
-   Crear un nuevo proveedor de Operations Manager para la instancia del contador de rendimiento específico del host de BizTalk.  
  
-   Modificar el proveedor de Operations Manager utilizado la regla y haga que señale al nuevo.  
  
 Suponga que su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instalación tiene un host de BizTalk ReceiveHost y que desea supervisar el tamaño de la cola de Host para este host. En este caso, debe crear un proveedor de Operations Manager basado en la instancia de ReceiveHost del contador de rendimiento para el tamaño de la cola del host de BizTalk. También debe establecer el valor del umbral en la regla de modo que sea adecuado para su entorno.  
  
 Si usa reglas de umbral específico del host de supervisión, debe deshabilitar las reglas de supervisión genéricas. De este modo se evitan las alertas redundantes.  
  
## <a name="see-also"></a>Vea también  
 [Supervisión de BizTalk Server con System Center Operations Manager 2007](../technical-guides/monitoring-biztalk-server-with-system-center-operations-manager-2007.md)