---
title: Cómo configurar la forma decidir | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Decide shape [Orchestration Designer]
- Decide shape [Orchestration Designer], configuring
- Decide shape [Orchestration Designer], branching
- configuring [Orchestration Designer], Decide shapes
ms.assetid: 70910861-3834-49e7-ab1e-d62730ea2a95
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a22368134e2c1a0d8deb277e186792158a7c2dd0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248692"
---
# <a name="how-to-configure-the-decide-shape"></a>Cómo configurar la forma Decidir
![](../core/media/ebiz-orch-decide.gif "ebiz_orch_decide")  
Forma Decidir  
  
 Cada rama de un **decidir** forma, excepto el **else** crear una bifurcación, tiene una regla asociados con él. Puede usar el Editor de expresiones de BizTalk para crear una expresión booleana en la regla que se evalúa para la ejecución de esa rama. Dado que la **else** bifurcación implica la negación de la expresión booleana de la rama anterior, no tiene una expresión asociada con él.  
  
 Debajo de la regla o **else** cláusula, una rama de un **decidir** forma puede contener formas adicionales, como cualquier otra parte de la orquestación.  
  
### <a name="to-configure-a-decide-shape"></a>Para configurar una forma Decidir  
  
1.  Si el Editor de expresiones de BizTalk no está visible, haga clic en la regla y haga clic en **Editar expresión booleana**, o en la ventana Propiedades, haga clic en el **puntos suspensivos** (**...** ) botón la **expresión** propiedad.  
  
2.  En el Editor de expresiones de BizTalk, cree una expresión booleana para cada rama, excepto la **Else** bifurcación. Por ejemplo,  
  
    ```  
    myMessage.Total > 1000  
    myObject.IsValid()  
    myMessage.VIP == true  
    ```  
  
### <a name="to-add-a-branch-to-a-decide-shape"></a>Para agregar una rama a una forma Decidir  
  
1.  Haga clic en el **decidir** forma y, a continuación, haga clic en **nueva rama de reglas**.  
  
     : "O":  
  
2.  Arrastre una nueva forma entre dos ramas existentes.  
  
    > [!NOTE]
    >  Para quitar una rama de un **decidir** forma, haga clic en la rama que desee quitar y, a continuación, haga clic en **eliminar**, o seleccione la rama de reglas y presione la **eliminar** clave.