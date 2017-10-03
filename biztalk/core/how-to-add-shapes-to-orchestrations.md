---
title: "Cómo agregar formas a orquestaciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- shapes, orchestrations
- orchestrations, shapes
- Construct Message shape [Orchestration Designer]
- Message Assignment shape [Orchestration Designer]
- Scope shape [Orchestration Designer]
ms.assetid: d39eb12c-cdc6-4918-93d9-536db1dfb889
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9fa6634adb20ffcf927da0af6f58e9daa2800ac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-shapes-to-orchestrations"></a>Cómo agregar formas a orquestaciones
En esta sección se describen los procedimientos para agregar y quitar formas en la orquestación. Para obtener más información acerca de las formas disponibles, consulte [formas de orquestación](../core/orchestration-shapes.md).  
  
### <a name="to-add-a-shape-to-an-orchestration"></a>Para agregar una forma a una orquestación  
  
1.  En el cuadro de herramientas, en la **orquestaciones de BizTalk** ficha, arrastre la forma hasta una línea de conexión en la superficie de diseño de orquestación.  
  
     : "O":  
  
2.  Haga clic en la línea de conexión o el marcador de posición de la forma en la que desea agregar la forma, seleccione **Insertar forma**y, a continuación, haga clic en el nombre de la forma que desee agregar.  
  
    > [!NOTE]
    >  Si una forma aún no está completamente configurada, aparece una etiqueta inteligente sobre ella.  
  
> [!NOTE]
>  **Transformar** formas y **asignación de mensajes** solo pueden existir dentro de un **construir mensaje** forma. Si agrega una de estas formas a la orquestación fuera de un **construir mensaje** forma, se colocará automáticamente dentro de una nueva **construir mensaje** forma.  
  
> [!NOTE]
>  **Detectar excepciones** y **compensación** bloques solo pueden existir a continuación un **ámbito** forma.  
  
### <a name="to-remove-a-shape-from-an-orchestration"></a>Para quitar una forma de una orquestación  
  
1.  Haga clic en la forma en la superficie de diseño y, a continuación, haga clic en **eliminar**.  
  
     : "O":  
  
2.  Seleccione la forma y presione la **eliminar** clave.  
  
## <a name="see-also"></a>Vea también  
 [Crear orquestaciones](../core/creating-orchestrations.md)