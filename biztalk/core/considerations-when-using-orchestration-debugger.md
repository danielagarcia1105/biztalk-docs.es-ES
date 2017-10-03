---
title: Consideraciones al utilizar el depurador de orquestaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Orchestration Debugger, modified orchestrations
- Orchestration Debugger, planning
- atomic scopes
- planning, Orchestration Debugger
- Orchestration Debugger, atomic scopes
- Orchestration Debugger, simple types
- orchestrations, modifying
ms.assetid: 55bfef48-08bd-48bb-abd5-7264e683da46
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2815da55bc74d822cb5fe2540347855db75b3a8b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="considerations-when-using-orchestration-debugger"></a>Consideraciones acerca del uso del Depurador de orquestaciones
A continuación se describen algunas consideraciones que debe tener en cuenta cuando trabaje con el Depurador de orquestaciones.  
  
## <a name="tracking-atomic-scopes"></a>Realizar un seguimiento de ámbitos atómicos  
 Una orquestación puede contener ámbitos atómicos para incluir llamadas al motor de reglas. Cuando se asocia a una instancia en el depurador de orquestaciones, todos los ámbitos atómicos en la instancia de orquestación provocará "huecos" que aparecen en la lista de eventos de seguimiento. Esto ocurre por dos motivos:  
  
-   Porque los eventos de las formas de las transacciones atómicas no se guardan hasta que se confirma el ámbito.  
  
-   El depurador vuelve a cargar los eventos al final de la lista, por lo que todos los espacios en blanco se quedan sin rellenar durante la sesión activa.  
  
 Puede eliminar los espacios en blanco si actualiza la vista.  
  
> [!NOTE]
>  No puede establecer un punto de interrupción en formas de un ámbito atómico.  
  
## <a name="setting-breakpoints-in-the-exception-handler-scope"></a>Establecer puntos de interrupción en el ámbito del controlador de excepción  
 Si el punto de interrupción se define en el controlador de detección de excepción, los tipos de excepción deben marcarse como serializables o el depurador de orquestaciones no se detendrá en los puntos de interrupción establecidos. Ello se debe a que el depurador de orquestaciones realiza la persistencia en el punto de interrupción. Por lo tanto, cuando hay un objeto no serializable en el estado de la instancia de orquestación, se producirá una excepción de persistencia y, en este caso, también recibirá una excepción DebugBreakPointFailedException.  
  
## <a name="tracking-a-modified-orchestration"></a>Realizar un seguimiento de una orquestación modificada  
 Si realiza el seguimiento de una orquestación modificada sin cambiar el número de versión, debe reiniciar todas las instancias de host para las que dio de alta la orquestación. Esto garantiza que cualquier cambio de la forma en la versión implementada recientemente se muestre correctamente, ejecutar paso a paso mediante el depurador de orquestaciones.  
  
## <a name="tracking-simple-types"></a>Realizar el seguimiento de tipos simples  
 El Depurador de orquestaciones solo admite tipos simples. Por ejemplo, si realiza el seguimiento de un mensaje de varias partes que contiene un objeto .NET, puede ver las propiedades de todas las partes del mensaje, excepto las propiedades del objeto .NET.  
  
 Cuando una orquestación aparece en estado En punto de interrupción y se inicia el Depurador de orquestaciones, puede realizar las siguientes acciones:  
  
-   Use la **adjuntar** opción de servicio.  
  
-   Revise los pasos que ya se han completado.  
  
-   Consulte el estado de variables y mensajes.  
  
-   Establezca puntos de interrupción adicionales.  
  
-   Seleccione el **continuar servicio** opción.  
  
-   Repita los pasos tantas veces como sea necesario.  
  
## <a name="see-also"></a>Vea también  
 [Modo interactivo en el depurador de orquestaciones](../core/interactive-mode-in-orchestration-debugger.md)   
 [Depuración de una orquestación](../core/debugging-an-orchestration.md)