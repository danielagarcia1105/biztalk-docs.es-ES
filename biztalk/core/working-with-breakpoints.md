---
title: Trabajar con puntos de interrupción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Orchestration Debugger, breakpoints
- Orchestration Debugger, suspended orchestrations
- Orchestration Debugger, Message Flow view
- Orchestration Debugger, service options
- Message Flow view [Orchestration Debugger]
ms.assetid: aad1a2b0-d705-49cd-85f7-b0ab2e473bcc
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60e9cee77f105b132438e621651ee90c0090c1be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289212"
---
# <a name="working-with-breakpoints"></a>Trabajar con puntos de interrupción
Puede establecer puntos de interrupción si se conecta a una orquestación suspendida o establece un punto de interrupción en una clase.  
  
> [!NOTE]
>  Si anula la implementación de un ensamblado, la base de datos mantiene la información del punto de interrupción y las opciones de seguimiento de ese ensamblado. Si a continuación vuelve a implantar el mismo ensamblado, se restauran la información del punto de interrupción y las opciones de ese ensamblado.  
  
### <a name="to-attach-to-a-suspended-orchestration"></a>Para conectarse a una orquestación suspendida  
  
1.  Seleccione una orquestación suspendida automáticamente mediante una forma de suspensión y luego continúe en el paso 3.  
  
2.  Actualice la vista para comprobar que la instancia aparece en estado de suspensión.  
  
3.  Haga clic en **reanudar en depuración**.  
  
     La orquestación se reanuda en un estado En punto de interrupción. Ahora puede depurar interactivamente.  
  
### <a name="to-switch-to-the-message-flow-view"></a>Para pasar a la vista Flujo de mensajes  
  
-   Haga clic en una celda de la lista de resultados y seleccione **flujo de mensajes** en el menú contextual.  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con la vista depurador de orquestaciones](../core/working-with-the-orchestration-debugger-view.md)