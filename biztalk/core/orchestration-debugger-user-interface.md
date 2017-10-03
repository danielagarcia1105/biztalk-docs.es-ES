---
title: Interfaz de usuario del depurador de orquestaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.hat.orchdebugger
helpviewer_keywords:
- Orchestration Debugger, debug mode
- Orchestration Debugger, Interactive mode
ms.assetid: ca18f1e2-63b7-4177-82ba-4accc3369a2a
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4663a642ffc960d969c994b5471d866a80fde828
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="orchestration-debugger-user-interface"></a>Interfaz de usuario del Depurador de orquestaciones
En el modo interactivo (depurar), la vista depurador de orquestaciones contiene tres paneles: el panel orquestación, panel eventos controlados y panel de servicio. Además, en modo interactivo, la Lista de variables y las Propiedades de variables aparecen en la parte inferior de la vista.  
  
> [!NOTE]
>  El depurador de orquestaciones no se puede mostrar el verdadero estado del servicio a menos que aparezca en **en punto de interrupción** modo y se ha adjuntado a la instancia.  
  
## <a name="service-pane-in-orchestration-debugger"></a>Panel Servicio del Depurador de orquestaciones  
 El panel superior de la ventana Depurador de orquestaciones muestra la siguiente información.  
  
|Etiqueta|Detalle|  
|---------|------------|  
|Nombre|Indica la vista actual (Depurador de orquestaciones) y permite pasar a la vista Flujo de mensajes.|  
|Detalles de instancia|Muestra el nombre del servicio y el GUID que identifica de forma exclusiva la instancia de orquestación actual.|  
|Modos|Modo de depuración (Responder/Activo), Estado de la orquestación (Iniciado, Suspendido, Completado, etc.), Adjunto (Sí o No) y Modo de punto de interrupción (En la clase o En la instancia).|  
|Opciones de servicio|Lista desplegable de acciones que puede realizar en función del estado del depurador y de la instancia.|  
  
 Debajo de esta información, el depurador de orquestaciones tiene dos paneles: el panel eventos controlados de la izquierda y el panel de la orquestación a la derecha.  
  
## <a name="tracked-events-pane-in-orchestration-debugger"></a>Panel eventos controlados del Depurador de orquestaciones  
 El panel eventos controlados lista el estado de cada una de las acciones llevadas a cabo en la orquestación. Por ejemplo, si la orquestación está iniciada o terminada. A medida que vaya seleccionando filas en el panel, aparecerá la correspondiente forma en el panel Orquestación (resaltada en verde para indicar que está iniciada, o en azul si está terminada).  
  
 El panel eventos controlados muestra las columnas siguientes:  
  
|Opción|Acción|  
|------------|------------|  
|Estado de acción (columna izquierda)|Estado de una determinada acción. Una flecha indica que la acción ha comenzado, y una forma de terminación indica que se ha completado.|  
|Nombre de la acción|Nombre de la acción en la orquestación.|  
|Tipo de acción|Tipo de forma que representa la acción. Una flecha indica que se inició la acción y una forma de terminación indica que se ha completado.|  
|Time|Hora a la que se llevó a cabo la acción.|  
|Date|Fecha en que se llevó a cabo la acción.|  
  
## <a name="orchestration-pane-in-orchestration-debugger"></a>Panel Orquestación del Depurador de orquestaciones  
 El panel Orquestación de la salida del seguimiento de instancias de servicios y eventos de mensajes de la página Concentrador de grupo es el área donde se representa la instancia de la orquestación con todas sus formas. La tabla siguiente muestra las acciones del menú Contexto del panel Orquestación.  
  
|Opción|Acción|  
|------------|------------|  
|Configurar punto de interrupción en clase|Haga clic en una forma para el **Establecer puntosInterrupción en la clase** opción. Un punto rojo aparece en la forma e indica que se ha establecido el punto de interrupción.|  
|Establecer punto de interrupción en la instancia|Haga clic en una forma para el **Establecer puntosInterrupción en la instancia** opción. Un punto rojo aparece en la forma e indica que se ha establecido el punto de interrupción.|  
|Quitar punto de interrupción en la clase|Haga clic en una forma para el **Quitar puntosInterrupción** opción. El punto rojo desaparece de la forma e indica que se ha quitado el punto de interrupción.|  
|Quitar punto de interrupción de la instancia|Haga clic en una forma para el **Establecer puntosInterrupción en la instancia** opción. El punto rojo desaparece de la forma e indica que se ha quitado el punto de interrupción.|  
  
### <a name="variable-list-and-variable-properties-panes"></a>Paneles Propiedades de variables y Lista de variables  
 Estos paneles sólo aparecen en la depuración interactiva cuando adjunta a la orquestación en tiempo de ejecución por medio del **adjuntar** opción de servicio. Estos paneles aparecen en la parte inferior de la pantalla.  
  
 La Lista de variables muestra el Nombre, Valor y Tipo de la variable. El valor indica si la variable es nula o, si no, qué tipo de objeto contiene. El tipo es el **Assembly.Namespace.Name** del objeto.  
  
 El panel Propiedades de variables muestra las propiedades para la variable que varían en función del tipo de objeto. Por ejemplo, para puertos, se incluye Dirección, Nombre, Ámbito, Tipo y Valor. Los mensajes indican el acceso directo, como Nombre, Tamaño, Propiedades, Tipo y Valor para cada parte en el mensaje. Las colecciones como Contexto y Propiedades aparecen en una ventana emergente. Una presentación parcial del valor aparece como información sobre herramientas.  
  
 El usuario avanza a través de la programación de punto de interrupción en punto de interrupción y examina el estado de estas variables.  
  
 La tabla siguiente muestra las acciones del menú Contexto de la Lista de variables.  
  
|Opción|Acción|  
|------------|------------|  
|Guardar mensaje|Haga clic en un mensaje que es distinto de null en el panel de la lista de variables para el **Guardar mensaje** opción. Aparece un mensaje que le indica que debe seleccionar un directorio par guardarlo.|  
  
### <a name="service-options-drop-down-list"></a>Lista desplegable Opciones de servicios  
 La lista desplegable Opciones de servicios muestra las acciones posibles que estén basadas en el estado de la instancia y del depurador. En la tabla siguiente se muestra las acciones disponibles en la lista desplegable Opciones de servicios.  
  
|Opción|Acción|  
|------------|------------|  
|Continuar servicio|Continúa una instancia de orquestación que se detuvo en el punto de interrupción si adjuntó el servicio.|  
|Reanudar en modo de depuración|Reanuda una instancia de orquestación suspendida en modo de depuración. Esto le permite obtener acceso al modo interactivo, adjuntarla a la instancia y depurarla interactivamente.<br /><br /> Disponible desde las vistas Operaciones y del Depurador de orquestaciones. Sólo se aplica a orquestaciones.|  
|Finalizar servicio|Finaliza una instancia de orquestación.|  
|Adjuntar|Conecta el servicio a la instancia de orquestación y recupera el estado actual y las variables actuales|  
|Eliminar todos los puntos de interrupción en la clase|Quita todos los puntos de interrupción en la clase de orquestación. Sólo disponible si no se adjuntan.|  
|Quitar todos los puntos de interrupción|Quita todos los puntos de interrupción de la instancia de orquestación. Sólo disponible si se adjuntan.|  
|Guardar todos los mensajes|Guarda todos los mensajes asociados con la instancia de orquestación siempre que se haya seleccionado hacer un seguimiento de todos los mensajes entrantes y salientes.|  
|Mostrar acción en punto de interrupción|Resalta en amarillo la forma de la última acción que se ejecutó antes de la interrupción.|  
|Ver Orquestación de llamada|Devuelve la vista a la instancia de orquestación que realizó la llamada. Es decir, vuelve a la orquestación primaria.<br /><br /> Sólo disponible en una instancia de orquestación solicitada.|  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Modo de informe en el depurador de orquestaciones](../core/reporting-mode-in-orchestration-debugger.md)  
  
-   [Modo interactivo en el depurador de orquestaciones](../core/interactive-mode-in-orchestration-debugger.md)  
  
## <a name="see-also"></a>Vea también  
 [Depuración de una orquestación](../core/debugging-an-orchestration.md)