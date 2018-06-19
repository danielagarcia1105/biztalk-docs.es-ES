---
title: Cómo copiar, cortar y pegar un Functoid | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 825847e4-87db-4b40-8e5d-5b5b1c79c6de
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9af3662fb866eb09c1dcb2516279ca097cc998f6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249532"
---
# <a name="how-to-copy-cut-and-paste-a-functoid"></a>Cómo copiar, cortar y pegar un functoid
La característica de copiar, cortar y pegar del Asignador de BizTalk permite la reutilización de functoids. En una asignación, puede copiar y cortar uno o varios functoids de una página de cuadrícula y pegarlos en otra. En este tema se proporcionan instrucciones detalladas para realizar estas operaciones.  
  
 Puede usar la característica de copiar y pegar cuando desee reutilizar functoids. Y, cuando desee eliminar un functoid de la ubicación existente y moverlo a una nueva ubicación, puede usar la característica de cortar y pegar.  
  
> [!IMPORTANT]
>  Cuando elige copiar un functoid, se copia el functoid, su etiqueta, los comentarios y las entradas de constantes junto con los índices de marcador. De forma similar, cuando elige cortar un functoid, se corta el functoid, su etiqueta, los comentarios y las entradas de constantes, junto con los índices de marcador de posición. Pero, al pegar la selección (después de elegir cortar), únicamente se conserva el functoid y los vínculos huérfanos se eliminan. No se conservan la etiqueta, los comentarios, las entradas constantes y los índices de marcador de posición.  
  
 Si únicamente selecciona un functoid, que está vinculado a otro functoid o a un nodo de esquema, solo se cortará o copiará el functoid, sin los vínculos. Si corta un functoid que está vinculado a otros functoids en la asignación o a los nodos de esquema, se eliminan los vínculos para el functoid que se corta.  
  
 Puede copiar o cortar functoids de:  
  
-   Dentro de la misma página de cuadrícula de un mapa  
  
-   Una página de cuadrícula a las otras del mismo mapa  
  
-   Una instancia de Visual Studio a otra  
  
 Las operaciones de cortar y pegar no se pueden deshacer o rehacer. Para obtener más información, consulte [cómo deshacer o rehacer operaciones de usuario](../core/how-to-undo-or-redo-user-operations.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Estas instrucciones requieren que se está ejecutando el asignador de BizTalk.  
  
### <a name="to-copy-and-paste-a-functoid"></a>Procedimiento para copiar y pegar un functoid  
  
1.  En el Explorador de soluciones, abra el proyecto BizTalk y haga doble clic en el mapa para abrirlo en el Asignador de BizTalk.  
  
2.  Seleccione el functoid que desee copiar. Para seleccionar varios functoids, haga clic en un functoid, mantenga presionada la tecla CTRL y haga clic en los demás functoids.  
  
    > [!NOTE]
    >  Puede usar la operación "seleccionar en la cinta" para seleccionar varios vínculos o functoids. Para obtener más información, consulte [cómo seleccionar varios vínculos y Functoids](../core/how-to-select-multiple-links-and-functoids.md).  
  
3.  Haga clic en la selección y, a continuación, haga clic en **copia**. Como alternativa, puede hacer clic en **copia** desde el Visual Studio **editar** menú o presione CTRL + C en el teclado.  
  
    > [!NOTE]
    >  Para obtener una lista de métodos abreviados de teclado, consulte [métodos abreviados de teclado del asignador de BizTalk](../core/biztalk-mapper-keyboard-shortcuts.md).  
  
4.  Coloque el cursor donde desee pegar el functoid.  
  
5.  Haga doble clic en la página de cuadrícula y, a continuación, haga clic en **pegar**. Como alternativa, puede hacer clic en **pegar** desde el Visual Studio **editar** menú o presionar CTRL+V en el teclado. Aparece una copia del functoid o grupo de functoids seleccionado en la nueva ubicación.  
  
### <a name="to-cut-and-paste-a-functoid"></a>Procedimiento para cortar y pegar un functoid  
  
1.  En el Explorador de soluciones, abra el proyecto BizTalk y haga doble clic en el mapa para abrirlo en el Asignador de BizTalk.  
  
2.  Seleccione el functoid que desee cortar. Para seleccionar varios functoids, haga clic en un functoid, mantenga presionada la tecla CTRL y haga clic en los demás functoids.  
  
3.  Haga clic en la selección y, a continuación, haga clic en **cortar**. Como alternativa, puede hacer clic en **cortar** desde el Visual Studio **editar** menú o presionar CTRL+X en el teclado.  
  
    > [!NOTE]
    >  Para obtener una lista de métodos abreviados de teclado, consulte [métodos abreviados de teclado del asignador de BizTalk](../core/biztalk-mapper-keyboard-shortcuts.md).  
  
4.  Coloque el cursor donde desee pegar el functoid.  
  
5.  Haga doble clic en la página de cuadrícula y, a continuación, haga clic en **pegar**. Como alternativa, puede hacer clic en **pegar** desde el Visual Studio **editar** menú o presionar CTRL+V en el teclado. El functoid o grupo de functoids seleccionado se elimina de la ubicación existente y aparece en la nueva ubicación.  
  
## <a name="see-also"></a>Vea también  
 [Utilizar Functoids para crear asignaciones más complejas.](../core/using-functoids-to-create-more-complex-mappings.md)