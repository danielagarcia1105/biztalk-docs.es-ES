---
title: "Cómo capturar un volcado de memoria de un proceso que está bloqueado | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5f436b72-2b6a-4519-acc3-e7ba978651fe
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e87664180b7ad4d5fdcd121542974a08b8634d55
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-capture-a-memory-dump-of-a-process-that-is-crashing"></a>Cómo capturar un volcado de memoria de un proceso que está bloqueado
El proceso de BizTalk BTSNTSvc.exe se define como **bloqueo** cuando finaliza el proceso de forma inesperada por Windows. El bloqueo suele provocarlo una excepción no controlada en el proceso, como una infracción de acceso o un desbordamiento de la pila. En estas situaciones, las ventanas de forma predeterminada depurador, recuperación ante desastres. Watson (drwtsn32.exe) detecta la excepción y finaliza el proceso.  
  
 Para capturar un volcado de memoria de un proceso que se está bloqueando, configure la herramienta de diagnósticos de depuración para capturar la excepción no controlada siguiendo estos pasos:  
  
### <a name="to-configure-the-debug-diagnostics-tool-to-capture-a-crash-dump"></a>Para configurar la herramienta de diagnósticos de depuración y capturar un volcado  
  
1.  Inicie la herramienta de diagnósticos de depuración desde **iniciar**, **todos los programas**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.  
  
2.  Si el **Select Rule Type** no se muestra el cuadro de diálogo del Asistente para agregar regla, haga clic en el **herramientas** menú, seleccione **acciones de regla**y haga clic en **Agregar regla**para mostrar el Asistente para agregar regla.  
  
3.  Seleccione el **bloqueo** opción en el **Select Rule Type** cuadro de diálogo y haga clic en **siguiente**.  
  
4.  Seleccione **un proceso específico** en el **Select Target Type** cuadro de diálogo y haga clic en **siguiente**.  
  
5.  Seleccione el proceso BTSNTSvc.exe que está bloqueando y haga clic en **siguiente**.  
  
6.  En el **configuración avanzada de** diálogo haga clic en **siguiente** para aceptar los valores predeterminados.  
  
7.  En el **seleccione Dump Location And Rule Name** diálogo haga clic en **siguiente** para aceptar los valores predeterminados.  
  
8.  En el **Rule Completed** diálogo haga clic en **finalizar** para aceptar el valor predeterminado de **activar la regla ahora**.  
  
9. De forma predeterminada, se guardará un volcado de memoria del proceso para el \Program Files\IIS Resources\DebugDiag\Logs\\<*nombre de regla de bloqueo* \> directorio del equipo local la próxima vez que un se produce una excepción no controlada en el proceso.  
  
## <a name="see-also"></a>Vea también  
 [Cómo usar diagnósticos de depuración para analizar un volcado de memoria](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)