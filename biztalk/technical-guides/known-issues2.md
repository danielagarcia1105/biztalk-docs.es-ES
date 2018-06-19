---
title: Conoce problemas2 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 709c19ea-1138-49f8-8898-c2d2c60c3923
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28378697c145f48881f4ae850488c0c5afcb4ea3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298740"
---
# <a name="known-issues"></a>Problemas conocidos
En la tabla siguiente se enumera todos los problemas conocidos con la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack para Operations Manager 2007 R2/2012.  
  
|Problema|Description|Solución|  
|-----------|-----------------|----------------|  
|Contador de rendimiento relacionados con errores y advertencias después del reinicio|Puede ver información de los errores relacionados en rendimiento y las advertencias en el registro de eventos de Operations Manager después de agente reiniciar.|El módulo de administración se recupera después de los errores y se vuelve a funcionar.|  
|Detección de objetos relacionados con las advertencias en el registro de eventos de Operations Manager|Cuando no se puede encontrar una instancia de una detección (incluida la detección de relación), se escribe una advertencia al registro de eventos de Operations Manager, que indica que null devuelto por el script de detección.||  
|Las alertas en el nodo físico en un entorno en clúster no es confiable|Hay dos problemas conocidos asociados con la supervisión en entornos en clúster:<br /><br /> -Cuando un nodo cambia de activo a pasivo, la supervisión del estado del nodo y artefactos asociados podrían no reflejarse correctamente en la consola del operador.<br />-En entornos en clúster, Operations Manager crea un nodo virtual que puede mostrar las alertas y el estado duplicado.|En entornos en clúster que contiene nodos activo/pasivo; se basan en la información de supervisión que se muestran en el nodo virtual únicamente. Esto es porque el nodo virtual siempre señala al nodo físico que está activo en cualquier momento en el tiempo.|  
|Las relaciones y los monitores de dependencia|Los siguientes son los problemas conocidos relacionados con las relaciones y los monitores de dependencia: Esto ocurre sobre todo cuando el módulo de administración de BizTalk es volver a importar en un servidor determinado de SCOM. El usuario, a continuación, es necesario para ver el comentario del estado anterior tal como se indica en la sección "Pasos para reproducir el comportamiento".<br /><br /> -No se detectan relaciones entre artefactos de BizTalk.<br />-No se muestran las relaciones de dependencia según lo previsto.<br />-Resumen de estado de supervisión no se produce.<br />-Algunos monitores de dependencia están sin inicializadas incluso después de la detección de relación.|Las soluciones alternativas para solucionar estos problemas son los siguientes:<br /><br /> <ul><li>Reinicie el servicio de mantenimiento de Operations Manager en el equipo de agente de BizTalk. <br />     -OR-</li><li>Ejecutar la tarea de vaciado de estado del servicio y la memoria caché. Los pasos para hacerlo son los siguientes:<br /><br /> <ol><li>En el árbol de navegación, seleccione el estado de mantenimiento de agente de Operations Manager agente.</li><li>Seleccione el equipo que ejecuta BizTalk Server en el estado del agente de Monitor de servicio de mantenimiento.</li><li>Seleccione el estado del agente en el estado del agente.</li><li>Haga clic en la tarea de vaciado de estado del servicio y la memoria caché en el panel de la derecha.</li><li>En la tarea de ejecución - estado de servicio de mantenimiento de vaciado y cuadro de diálogo de caché, haga clic en ejecutar.</li></ol></li></ul>|  
|Muestra mal estado de los puertos de envío y ubicaciones de recepción|Cuando el servicio SSO está inactivo, el módulo de administración de BizTalk Server no muestren el estado correcto de puertos de envío y ubicaciones de recepción.||