---
title: Supervisión de instancias de Host | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4e7c6b80-7371-46ea-bf9c-82acb22012a3
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91ad5ec158466db6716b515fe3d34ae76c4cde0f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003341"
---
# <a name="monitoring-host-instances"></a>Supervisión de instancias de Host
Este tema describe la supervisión de las instancias de host de BizTalk mediante Microsoft System Center Operations Manager.  
  
## <a name="using-threshold-rules-to-monitor-health"></a>Uso de reglas de umbral para supervisar el estado  
 El módulo de administración de BizTalk Server incorpora reglas de umbral de rendimiento que proporcionan una visión completa del estado de los hosts de BizTalk. Se proporcionan dos tipos distintos de reglas de umbral:  
  
- Reglas que se aplican de forma genérica (por ejemplo, para todos los hosts de BizTalk y a todas las bases de datos de cuadro de mensajes).  
  
- Reglas que son específicas de un determinado host de BizTalk.  
  
  Las reglas genéricas supervisan todos los hosts de BizTalk según un umbral común. Por ejemplo, la regla de Monitor HostQ Size supervisa las colas de trabajo de todos los hosts de BizTalk según un umbral común. Si hay tres hosts diferentes, la misma regla supervisa todas las colas de trabajo y las alertas se producen cuando cualquiera de las colas de trabajo de host cruza el umbral común.  
  
  Reglas específicas del host de BizTalk le permiten configurar varios umbrales para distintos hosts. Por ejemplo, la regla de Monitor HostQ Size – BizTalkServerApplication es una regla de host específico que supervisa la cola de trabajo del host BizTalkServerApplication. En este ejemplo puede definir un proveedor específico de Operations Manager para la instancia de contador de rendimiento determinado y usar ese proveedor en la regla de umbral. Dado que estas reglas son específicos del host, debe definir reglas específicas para cada host recién creado.  
  
  Reglas específicas del host de BizTalk se proporcionan como reglas de plantilla para crear reglas que son aplicables en su entorno. Todas las reglas de supervisión de umbral están deshabilitadas de forma predeterminada:  
  
- Debe configurar las reglas genéricas con valores de umbral específicos para su entorno.  
  
- Debe crear reglas de específico del host de BizTalk según las reglas de plantilla y los umbrales apropiados.  
  
## <a name="monitoring-biztalk-host-instances"></a>Supervisión de instancias de Host de BizTalk  
 Las reglas dirigidas a hosts específicos de BizTalk son más flexibles desde una perspectiva de supervisión. Todas las reglas de supervisión de umbral para el host de BizTalkServerApplication proporcionado en el módulo de administración de BizTalk Server son reglas de plantilla. Para poder usar estas reglas, debe usar la consola de administrador de Operations Manager para:  
  
- Crear una copia de la regla de plantilla en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de reglas y cambie su nombre.  
  
- Crear un nuevo proveedor de Operations Manager para la instancia del contador de rendimiento específicos de host de BizTalk.  
  
- Modificar el proveedor de Operations Manager utilizado la regla y haga que señale al nuevo.  
  
  Supongamos que su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instalación tiene un host de BizTalk denominado ReceiveHost y que desea supervisar el tamaño de cola de Host para este host. En este caso, debe crear un proveedor de Operations Manager basado en la instancia de ReceiveHost del contador de rendimiento para el tamaño de la cola del host de BizTalk. También debe establecer el valor del umbral en la regla de modo que sea adecuado para su entorno.  
  
  Si usa reglas de supervisión de umbral específico del host, debe deshabilitar las reglas de supervisión genéricas. De este modo se evitan las alertas redundantes.  
  
## <a name="see-also"></a>Vea también  
 [Supervisión de BizTalk Server con System Center Operations Manager 2007](../technical-guides/monitoring-biztalk-server-with-system-center-operations-manager-2007.md)