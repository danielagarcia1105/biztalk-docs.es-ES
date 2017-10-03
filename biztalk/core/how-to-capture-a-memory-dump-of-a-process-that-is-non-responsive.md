---
title: "Cómo capturar un volcado de memoria de un proceso que no responde | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ad53376-2fab-4dee-8a6a-a44d157390f2
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 520921010a8bbfd73de8c3b305a1270ca8363c46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-capture-a-memory-dump-of-a-process-that-is-non-responsive"></a>Cómo capturar un volcado de memoria de un proceso que no responde
El proceso de BizTalk BTSNTSvc.exe se define como **francesa** cuando el proceso parece que deja de responder. Los síntomas comunes de que un proceso no responde incluyen los siguientes:  
  
-   Parece que las orquestaciones dejan de ejecutarse.  
  
-   Los mensajes no se procesan.  
  
-   Se producen problemas generales de tiempo de espera.  
  
-   El proceso de BizTalk BTSNTSvc.exe consume una cantidad inusualmente elevada de ciclos de CPU tal como se ve en el **procesos** ficha de **el Administrador de tareas**.  
  
 Para capturar un volcado de memoria de un proceso BTSNTSvc.exe que no responde, siga los siguientes pasos.  
  
### <a name="to-configure-the-debug-diagnostics-tool-to-capture-a-hang-dump"></a>Para configurar la herramienta de diagnósticos de depuración y capturar un volcado que no responde  
  
1.  Inicie la herramienta de diagnósticos de depuración desde **iniciar**, **todos los programas**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.  
  
2.  Si el **Select Rule Type** se muestra el cuadro de diálogo del Asistente para la configuración de reglas, haga clic en el **cancelar** botón.  
  
3.  Haga clic en el **procesos** ficha de la herramienta de diagnóstico de depuración.  
  
4.  Haga clic en el proceso BTSNTSvc.exe que no responde y seleccione **Create Full Userdump**. De forma predeterminada, un volcado de memoria del proceso se guardará en el directorio \Archivos de programa\IIS Resources\DebugDiag\Logs\Misc del equipo local.  
  
## <a name="see-also"></a>Vea también  
 [Cómo usar diagnósticos de depuración para analizar un volcado de memoria](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)