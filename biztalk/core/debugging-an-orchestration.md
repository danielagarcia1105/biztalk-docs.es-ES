---
title: "Depuración de una orquestación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c231513ad75520fcadd88e5dd7d88104ddeeced5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="debugging-an-orchestration"></a>Depuración de una orquestación
El Depurador de orquestaciones le permite realizar el seguimiento de la actividad de una actividad de una instancia de orquestación única forma a forma. Muestra una vista procesada de la orquestación creada en el Diseñador de orquestaciones.  
  
 Se obtiene acceso al Depurador de orquestaciones en la página de información general de grupo de la consola de administración de BizTalk Server.  Para ello, en los resultados de una consulta de seguimiento, haga clic con el botón secundario en cualquier instancia de servicio o mensaje asociada a un tipo de orquestación para abrir el menú contextual. Cuando se encuentre en esta página, puede cambiar entre la vista Depurador de orquestaciones y Flujo de mensajes.  
  
 El Depurador de orquestaciones proporciona la funcionalidad siguiente:  
  
-   Muestra una vista procesada de la orquestación en la que puede reproducir todos los pasos de procesamiento para esa orquestación en particular.  
  
-   Le permite establecer puntos de interrupción antes de cualquier forma de orquestación y continuar con la ejecución.  
  
-   Le permite analizar variables y datos de mensaje específicos.  
  
-   Habilita automáticamente todas las opciones de seguimiento de una instancia de orquestación determinada cuando ésta se abre en el Depurador de orquestaciones.  
  
-   Le ofrece la posibilidad de continuar, reanudar en el modo de depuración y finalizar la instancia de orquestación determinada.  
  
    > [!NOTE]
    >  Si anula la implementación de un ensamblado, la base de datos mantiene las opciones de seguimiento y la información del punto de interrupción de dicho ensamblado. Si a continuación vuelve a implantar el mismo ensamblado, se restauran las opciones y la información de punto de interrupción para el ensamblado.  
  
 Los dos modos de utilización del Depurador de orquestaciones son los siguientes:  
  
-   [Modo de informe en el depurador de orquestaciones](../core/reporting-mode-in-orchestration-debugger.md)  
  
-   [Modo interactivo en el depurador de orquestaciones](../core/interactive-mode-in-orchestration-debugger.md)  
  
 Las funciones varían en función del estado del servicio. Puede realizar una depuración interactiva al invocar cualquier instancia de servicio que se encuentre en estado En punto de interrupción desde cualquier vista. Para obtener información sobre la depuración de una orquestación, consulte [cómo invocar el depurador de orquestaciones y las vistas de flujo de mensajes](../core/how-to-invoke-the-orchestration-debugger-and-the-message-flow-views.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Interfaz de usuario del depurador de orquestaciones](../core/orchestration-debugger-user-interface.md)  
  
-   [Consideraciones al utilizar el depurador de orquestaciones](../core/considerations-when-using-orchestration-debugger.md)  
  
-   [Trabajar con la vista depurador de orquestaciones](../core/working-with-the-orchestration-debugger-view.md)