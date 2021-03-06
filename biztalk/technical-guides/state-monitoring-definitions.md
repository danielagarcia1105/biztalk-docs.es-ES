---
title: Definiciones de supervisión de estado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa2c8247-5e25-4624-9f0d-c7fe621ffba2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 95a15bc55bce7c39bdae67e04ff0a323776a180a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011685"
---
# <a name="state-monitoring-definitions"></a>Definiciones de supervisión de estado
Supervisión de estado le ayuda a responder la pregunta de si un equipo supervisado está en buen estado en un momento dado desde la perspectiva de una aplicación determinada. System Center Operations Manager (SCOM) actualiza el estado de distintas entidades administradas expuestas al usuario y presenta el estado como parte de la vista de supervisión de estado.  
  
 Para comprender el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] vista de supervisión de estado, debe entender los conceptos de supervisión de estado SCOM. La siguiente terminología se usa para describir los componentes fundamentales de la supervisión de estado:  
  
- **Rol** : un rol que desempeña un servidor en un entorno según lo determinado por la detección de servicios. Por ejemplo, la función de tiempo de ejecución de BizTalk encapsula los artefactos de tiempo de ejecución y las instancias de servidor BizTalk Server.  
  
- **Componente** : un rol secundario que se usa como parte de la acumulación de estado para medir el estado general del rol de servidor. Por ejemplo, el componente de alertas de BAM se utiliza para generar alertas para indicar el estado de mantenimiento general.  
  
- **Instancia** -un equipo determinado puede alojar las instancias del rol de servidor.  
  
  En pocas palabras, a continuación se citan los principios importantes de la supervisión de estados de SCOM:  
  
- Estado de un grupo de equipos se deriva el estado de los equipos que se encuentran en el grupo de equipos.  
  
- El estado del equipo muestra si las aplicaciones (denominadas roles de servidor) que se ejecutan en ese equipo están en buen estado de funcionamiento, y si éste se deriva del estado de las aplicaciones alojadas.  
  
- En el nivel de aplicación (rol de servidor), el estado del rol de servidor es el estado global de todas las instancias de aplicaciones de ese rol de servidor. Por ejemplo, estado de uno o varios artefactos como orquestaciones, recibe las ubicaciones, recibe los puertos y así sucesivamente afecta al estado y el estado general de una aplicación de BizTalk.  
  
- En el nivel de instancia de aplicación (instancia de rol de servidor), el estado de la instancia de aplicación se deriva del estado de diferentes áreas de la instancia de aplicación (denominados componentes).  
  
- Las alertas de SCOM están asociadas con el estado de funcionamiento de un componente. El estado de un componente se establece en rojo, amarillo o verde cuando se desencadenan alertas para indicar el estado general.  
  
- El estado de funcionamiento de un componente contribuye al estado de funcionamiento del rol de servidor.  
  
  En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
- Cada servidor BizTalk Server se considera una instancia del rol de servidor BizTalk Server.  
  
- En consecuencia, la función de BizTalk Server de un equipo se calcula como resultado de todos los eventos y actividades de todos los procesos de BizTalk Server de ese equipo.  
  
  El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] módulo de administración proporciona supervisión de estado de artefactos de BizTalk Server que incluye  
  
- Artefactos de la aplicación, como orquestaciones. Componentes de mensajería, como los puertos de recepción, ubicaciones de recepción y puertos de envío.  
  
- Artefactos de implementación, como servidores, instancias de host, inicio de sesión único y así sucesivamente.  
  
  En la tabla siguiente se enumera los tres estados que representan visualmente el estado de mantenimiento de todas las plataformas y aplicaciones nivel artefactos de BizTalk Server. De este modo, se proporciona al operador de SCOM una vista avanzada de una implementación de varios servidores, para que pueda centrarse rápidamente en los problemas importantes.  
  
|Artefactos|Verde|Amarillo|Rojo|  
|---------------|-----------|------------|---------|  
|Artefactos de nivel de aplicación|Se encuentran en un estado de ejecución.|Menos del 70% de las instancias con errores.|Más del 70% de las instancias con errores o han dado lugar a errores críticos.|  
|Artefactos de nivel de implementación|Se encuentran en un estado de ejecución.|No aplicable|No están en un estado de ejecución o se haya detenido.|