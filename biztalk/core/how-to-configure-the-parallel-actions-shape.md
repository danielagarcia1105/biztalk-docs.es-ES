---
title: "Cómo configurar la forma acciones paralelas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Parallel Actions shape [Orchestration Designer], Terminate shape [Orchestration Designer]
- Parallel Actions shape [Orchestration Designer], synchronizing data access
- Parallel Actions shape [Orchestration Designer]
- configuring [Orchestration Designer], Parallel Actions shapes
- Parallel Actions shape [Orchestration Designer], branching
- Parallel Actions shape [Orchestration Designer], about Parallel Actions shape
- Terminate shape [Orchestration Designer], Parallel Actions shape [Orchestration Designer]
- Parallel Actions shape [Orchestration Designer], configuring
ms.assetid: 396d6182-f5dd-4aab-9edc-92efe236fd3e
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 125d479a09eefb6771a884d2cddbfa98f34aeb36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-parallel-actions-shape"></a>Cómo configurar la forma Acciones paralelas
![](../core/media/ebiz-orch-paralactions.gif "ebiz_orch_paralactions")  
Forma acciones paralela  
  
> [!CAUTION]
>  Si coloca un **Terminate** forma dentro de un **acciones paralelas** forma así como la rama con la **Terminate** en que se ejecuta, la instancia se completa inmediatamente, sin tener en cuenta Si el resto de bifurcaciones ha terminado de ejecutarse. Según su diseño, los resultados podrían ser imprevisibles en este caso.  
  
## <a name="synchronization-of-data-access"></a>Sincronización de acceso a datos  
 Es posible que más de una bifurcación de un **acciones paralelas** forma intentará tener acceso a los mismos datos. Para evitar errores, coloque las formas que tienen acceso a los datos en el interior de ámbitos sincronizados. Puede especificar en las propiedades de un **ámbito** forma que se está sincronizado o no. Para obtener más información, consulte [ámbitos](../core/scopes.md).  
  
#### <a name="to-add-a-branch-to-a-parallel-actions-shape"></a>Para agregar una rama a una forma Acciones paralelas  
  
1.  Haga clic en el **acciones paralelas** forma y, a continuación, haga clic en **nueva rama paralela**.  
  
     : "O":  
  
2.  Arrastre una nueva forma entre dos ramas existentes.  
  
> [!NOTE]
>  Para quitar una rama de un **acciones paralelas** forma, haga clic en la rama que desee quitar y, a continuación, haga clic en **eliminar**.