---
title: "Cómo deshacer o rehacer operaciones de usuario | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1cb3708e-a9c2-4795-aba0-9c6d9635e08c
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8358fc1624346b90d98fd1f1707dd2bfb02446dd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-undo-or-redo-user-operations"></a>Deshacer o rehacer operaciones de usuario
La compatibilidad para deshacer/rehacer es otra facilidad de uso proporcionada por el Asignador de BizTalk. Si no está satisfecho con las modificaciones que ha realizado, o si ha hecho un cambio por error, puede deshacer para volver gradualmente al estado anterior "sin tocar" y continuar desde él. Rehacer permite volver a aplicar las acciones de edición que se han deshecho. En este tema se proporciona información acerca de las operaciones que se pueden deshacer o rehacer.  
  
> [!IMPORTANT]
>  Solo puede deshacer una operación si ha realizado al menos una operación de edición en el mapa. Rehacer no está disponible a menos que haya utilizado el comando Deshacer.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Estas instrucciones requieren que se está ejecutando el asignador de BizTalk.  
  
## <a name="what-can-you-undoredo"></a>¿Qué se puede deshacer/rehacer?  
 Se pueden deshacer y rehacer todas las operaciones de edición. Las operaciones que se pueden deshacer/rehacer son las siguientes:  
  
-   cortar/copiar/pegar functoids y/o vínculos  
  
     No se puede deshacer ni rehacer un número cualquiera de elementos (vínculos o functoids) con solo seleccionarlos y copiarlos. La función Copiar no cambia nada en la asignación.  
  
    > [!NOTE]
    >  Para obtener información acerca de cómo cortar, copiar y pegar un functoid, consulte [cómo copiar, cortar y pegar un Functoid](../core/how-to-copy-cut-and-paste-a-functoid.md). Para obtener más información acerca de cómo cortar/copiar/pegar functoid y un vínculo, vea [cómo copiar, cortar y pegar vínculos y Functoids](../core/how-to-copy-cut-and-paste-links-and-functoids.md).  
  
-   Vincular un nodo de origen a uno de destino o a un functoid, un functoid a otro functoid o un functoid a un nodo de destino  
  
-   Eliminar functoids y/o vínculos  
  
-   Mover vínculos y functoids seleccionados a otra página de cuadrícula  
  
-   Agregar, mover, reordenar o eliminar páginas de cuadrícula  
  
    > [!NOTE]
    >  Para obtener información sobre cómo agregar, mover, reordenar o eliminar páginas de cuadrícula, vea [cómo reorganizar páginas de cuadrícula](../core/how-to-reorder-grid-pages.md).  
  
-   Seleccionar esquemas de origen y destino al crear un mapa  
  
-   Reemplazar el esquema de origen o destino  
  
    > [!NOTE]
    >  Para obtener información sobre cómo reemplazar el esquema de origen o destino, consulte [cómo reemplazar esquemas](../core/how-to-replace-schemas.md).  
  
-   Configurar parámetros de entrada para functoids  
  
    > [!NOTE]
    >  Para obtener más información, consulte [cómo configurar parámetros de entrada del Functoid](../core/how-to-configure-functoid-input-parameters.md).  
  
-   Configurar o editar etiquetas para vínculos  
  
    > [!NOTE]
    >  Para obtener más información, consulte [cómo etiquetar un vínculo](../core/how-to-label-a-link.md).  
  
-   Configurar o editar etiquetas o comentarios para functoids  
  
    > [!NOTE]
    >  Para obtener más información, consulte [cómo etiquetar y comentar un Functoid](../core/how-to-label-and-comment-a-functoid.md).  
  
-   Omitir espacios de nombres para las propiedades Vínculos y Prioridad de los tipos de scripts para la cuadrícula del Asignador.  
  
-   Reemplazar un vínculo al arrastrar un extremo de un vínculo desde un nodo o functoid a otro nodo o functoid.  
  
    > [!NOTE]
    >  Para obtener más información, consulte [cómo crear vínculos](../core/how-to-create-links.md).  
  
-   Realizar varias modificaciones en el **configurar \<Functoid\> Functoid** cuadro de diálogo que se trata como una única operación.  
  
-   Arrastrar functoids o vínculos en la cuadrícula del Asignador.  
  
    > [!NOTE]
    >  Para obtener más información, consulte [cómo mover una relación entre páginas de cuadrícula](../core/how-to-move-a-relationship-between-grid-pages.md).  
  
## <a name="how-can-you-undoredo-any-operation"></a>¿Cómo se puede deshacer o rehacer cualquier operación?  
 Se puede deshacer o rehacer una operación de una de las maneras siguientes:  
  
-   Desde el Visual Studio **editar** menú.  
  
-   Al hacer clic en los iconos de deshacer y rehacer de la barra de herramientas.  
  
-   Al presionar CTRL+Z para deshacer y CTRL+Y para rehacer.  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con páginas de cuadrícula](../core/working-with-grid-pages.md)