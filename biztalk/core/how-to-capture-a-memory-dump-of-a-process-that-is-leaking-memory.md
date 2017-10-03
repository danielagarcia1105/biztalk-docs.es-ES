---
title: "Cómo capturar un volcado de memoria de un proceso que pierde memoria | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 67404919-33a6-40ac-b1c4-09841db12fcf
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2999ce9a188b2d9b94df11328485e8b7440ecec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-capture-a-memory-dump-of-a-process-that-is-leaking-memory"></a>Cómo capturar un volcado de memoria de un proceso que pierde memoria
Se dice que el proceso BTSNTSvc.exe de BizTalk pierde memoria cuando no puede liberar la memoria que ya no necesita, lo que reduce, por tanto, la cantidad de memoria disponible con el tiempo. Se puede determinar el uso de memoria del proceso observando el valor en el **uso de memoria** columna de la **procesos** ficha disponible en **el Administrador de tareas**. Si el proceso sigue utilizando memoria con el tiempo sin liberarla, el rendimiento general del sistema se verá afectado negativamente.  
  
 Este tema contiene instrucciones para capturar un volcado de memoria de un proceso de BizTalk que parece que pierde memoria mediante una regla o de la captura de un volcado de memoria manual. Si la pérdida de memoria no es previsible, use el método manual.  
  
### <a name="to-capture-a-memory-dump-of-a-process-that-is-leaking-memory-by-using-a-rule"></a>Para capturar un volcado de memoria de un proceso que pierde memoria mediante una regla  
  
1.  Inicie la herramienta de diagnósticos de depuración desde **iniciar**, **todos los programas**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.  
  
2.  Si el **Select Rule Type** no se muestra el cuadro de diálogo del Asistente para agregar regla, haga clic en el **herramientas** menú, seleccione **acciones de regla**y haga clic en **Agregar regla**para mostrar el Asistente para agregar regla.  
  
3.  Seleccione el **Memory and Handle Leak** opción en el **Select Rule Type** cuadro de diálogo y haga clic en **siguiente**.  
  
4.  Seleccione el proceso BTSNTSvc.exe que parece que pierde memoria y haga clic en **siguiente**.  
  
5.  En el **Configure Tracking Duration** diálogo siga estos pasos:  
  
    1.  Si el aumento de memoria del proceso observado se produce inmediatamente, seleccione la opción **Iniciar seguimiento inmediatamente cuando se activa la regla de la memoria**. Si el aumento de memoria del proceso observado no se produce inmediatamente, especifique un número adecuado de minutos en el **tiempo de preparación** cuadro de texto después del cual se iniciará el seguimiento de la memoria.  
  
        > [!NOTE]
        >  El aumento de memoria del proceso observado puede no producirse inmediatamente si la pérdida de memoria ocurre al cargar un componente concreto en la memoria, por ejemplo, cuando una orquestación de BizTalk hace referencia a un componente externo.  
  
    2.  Especifique un número adecuado de minutos en el **seguimiento tiempo** cuadro de texto después del cual se detendrá el seguimiento de la memoria. Debe ser un número de minutos suficiente para reproducir la pérdida de memoria. Transcurrido este período, se capturará un volcado de memoria del proceso.  
  
    3.  Active la opción para **crear automáticamente un bloqueo de reglas para obtener userdump al salir del proceso inesperado**.  
  
    4.  Haga clic en **Siguiente**.  
  
6.  En el **seleccione Dump Location And Rule Name** diálogo haga clic en **siguiente** para aceptar los valores predeterminados.  
  
7.  En el **Rule Completed** diálogo haga clic en **finalizar** para aceptar el valor predeterminado de **activar la regla ahora**.  
  
8.  De forma predeterminada, se guardará un volcado de memoria del proceso para el \Program Files\IIS Resources\DebugDiag\Logs\\<*nombre de regla de bloqueo*> directorio del equipo local después de los intervalos de tiempo especificado en el **Configure Tracking Duration** ha transcurrido el cuadro de diálogo.  
  
### <a name="to-manually-capture-a-memory-dump-of-a-process-that-is-leaking-memory"></a>Para capturar manualmente un volcado de memoria de un proceso que pierde memoria  
  
1.  Inicie la herramienta de diagnósticos de depuración desde **iniciar**, **todos los programas**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.  
  
2.  Si el **Select Rule Type** se muestra el cuadro de diálogo del Asistente para agregar regla, haga clic en **cancelar**.  
  
3.  Haga clic para seleccionar la **procesos** ficha de la herramienta de diagnóstico de depuración.  
  
4.  Haga clic en el proceso BTSNTSvc.exe que parece que pierde memoria y haga clic en **Monitor For Leaks**.  
  
5.  Supervisar el uso de memoria del proceso en **el Administrador de tareas** y cuando el uso de memoria del proceso aproxima 60-80% de la memoria disponible en el equipo de BizTalk, capture manualmente un volcado de memoria del proceso haciendo clic en el proceso y seleccionando la opción de **Create Full Userdump**.  
  
6.  De forma predeterminada, un volcado de memoria del proceso se guardará en el directorio \Archivos de programa\IIS Resources\DebugDiag\Logs\Misc\ del equipo local.  
  
## <a name="see-also"></a>Vea también  
 [Cómo usar diagnósticos de depuración para analizar un volcado de memoria](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)