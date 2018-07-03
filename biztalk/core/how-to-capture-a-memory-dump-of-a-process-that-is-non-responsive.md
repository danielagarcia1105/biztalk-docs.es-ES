---
title: Cómo capturar un volcado de memoria de un proceso que no responde | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ad53376-2fab-4dee-8a6a-a44d157390f2
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f79cbc492611a6a1271e45b4198401b3d17452e7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016191"
---
# <a name="how-to-capture-a-memory-dump-of-a-process-that-is-non-responsive"></a>Cómo capturar un volcado de memoria de un proceso que no responde
El proceso de BizTalk BTSNTSvc.exe se define como **francesa** cuando el proceso parece dejar de responder. Los síntomas comunes de que un proceso no responde incluyen los siguientes:  
  
- Parece que las orquestaciones dejan de ejecutarse.  
  
- Los mensajes no se procesan.  
  
- Se producen problemas generales de tiempo de espera.  
  
- El proceso de BizTalk BTSNTSvc.exe consume una cantidad inusualmente elevada de ciclos de CPU, tal como se ve en el **procesos** ficha de **el Administrador de tareas**.  
  
  Para capturar un volcado de memoria de un proceso BTSNTSvc.exe que no responde, siga los siguientes pasos.  
  
### <a name="to-configure-the-debug-diagnostics-tool-to-capture-a-hang-dump"></a>Para configurar la herramienta de diagnósticos de depuración y capturar un volcado que no responde  
  
1.  Inicie la herramienta de diagnósticos de depuración desde **iniciar**, **todos los programas**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.  
  
2.  Si el **Select Rule Type** se muestra el cuadro de diálogo del Asistente para la configuración de reglas, haga clic en el **cancelar** botón.  
  
3.  Haga clic en el **procesos** pestaña de la herramienta Debug Diagnostic Tool.  
  
4.  Haga clic en el proceso BTSNTSvc.exe que no responde y seleccione **Create Full Userdump**. De forma predeterminada, un volcado de memoria del proceso se guardará en el directorio \Archivos de programa\IIS Resources\DebugDiag\Logs\Misc del equipo local.  
  
## <a name="see-also"></a>Vea también  
 [Cómo usar diagnósticos de depuración para analizar un volcado de memoria](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)