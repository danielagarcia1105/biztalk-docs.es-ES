---
title: Depuración de una orquestación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debugging, Orchestration Debugger
- debugging, orchestrations
- Orchestration Debugger, about Orchestration Debugger
- Orchestrations Debugger
- orchestrations, debugging
- debugging, HAT
- HAT, debugging
ms.assetid: aae99cfd-d3dd-41c8-ae7a-b2733352cd69
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 498063f5faa500b81c772bc646a2b1cd0f1c8df1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994493"
---
# <a name="debugging-an-orchestration"></a>Depuración de una orquestación
El Depurador de orquestaciones le permite realizar el seguimiento de la actividad de una actividad de una instancia de orquestación única forma a forma. Muestra una vista procesada de la orquestación creada en el Diseñador de orquestaciones.  
  
 Se obtiene acceso al Depurador de orquestaciones en la página de información general de grupo de la consola de administración de BizTalk Server.  Para ello, en los resultados de una consulta de seguimiento, haga clic con el botón secundario en cualquier instancia de servicio o mensaje asociada a un tipo de orquestación para abrir el menú contextual. Cuando se encuentre en esta página, puede cambiar entre la vista Depurador de orquestaciones y Flujo de mensajes.  
  
 El Depurador de orquestaciones proporciona la funcionalidad siguiente:  
  
- Muestra una vista procesada de la orquestación en la que puede reproducir todos los pasos de procesamiento para esa orquestación en particular.  
  
- Le permite establecer puntos de interrupción antes de cualquier forma de orquestación y continuar con la ejecución.  
  
- Le permite analizar variables y datos de mensaje específicos.  
  
- Habilita automáticamente todas las opciones de seguimiento de una instancia de orquestación determinada cuando ésta se abre en el Depurador de orquestaciones.  
  
- Le ofrece la posibilidad de continuar, reanudar en el modo de depuración y finalizar la instancia de orquestación determinada.  
  
  > [!NOTE]
  >  Si anula la implementación de un ensamblado, la base de datos mantiene las opciones de seguimiento y la información del punto de interrupción de dicho ensamblado. Si a continuación vuelve a implantar el mismo ensamblado, se restauran las opciones y la información de punto de interrupción para el ensamblado.  
  
  Los dos modos de utilización del Depurador de orquestaciones son los siguientes:  
  
- [Modo de informe en el Depurador de orquestaciones](../core/reporting-mode-in-orchestration-debugger.md)  
  
- [Modo interactivo en el Depurador de orquestaciones](../core/interactive-mode-in-orchestration-debugger.md)  
  
  Las funciones varían en función del estado del servicio. Puede realizar una depuración interactiva al invocar cualquier instancia de servicio que se encuentre en estado En punto de interrupción desde cualquier vista. Para obtener información sobre cómo depurar una orquestación, consulte [cómo invocar el depurador de orquestaciones y las vistas de flujo de mensajes](../core/how-to-invoke-the-orchestration-debugger-and-the-message-flow-views.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Interfaz de usuario del Depurador de orquestaciones](../core/orchestration-debugger-user-interface.md)  
  
-   [Consideraciones al usar el Depurador de orquestaciones](../core/considerations-when-using-orchestration-debugger.md)  
  
-   [Trabajar con la vista Depurador de orquestaciones](../core/working-with-the-orchestration-debugger-view.md)