---
title: Cómo reemplazar esquemas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 104e60d3-1303-4e56-b13a-c10ab14ba383
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df444b8169d75408fe6e412135029ae2b051a6d2
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-replace-schemas"></a>Cómo reemplazar esquemas
Puede que en algún momento desee reemplazar el esquema de origen o el de destino en una asignación existente, como cuando recibe un esquema actualizado de un socio comercial.  
  
> [!NOTE]
>  El Asignador de BizTalk intenta mantener todos los vínculos existentes entre el esquema que se conserva y el que se reemplaza.  
  
## <a name="replace-a-source-or-destination-schema"></a>Reemplazar un esquema de origen o destino  
  
1.  Haga clic en vista de árbol de esquema de origen o de destino y, a continuación, seleccione **Reemplazar esquema**.  
  
    > [!NOTE]
    >  Como alternativa, también puede presionar CTRL+M o CTRL+S del teclado. Para obtener una lista completa de métodos abreviados de teclado del asignador, vea [métodos abreviados de teclado del asignador de BizTalk](../core/biztalk-mapper-keyboard-shortcuts.md).  
  
2.  En el **selector de tipos de BizTalk** cuadro de diálogo, expanda el **esquemas** nodo en el árbol, seleccione el esquema apropiado y, a continuación, seleccione **Aceptar**.  
  
     ![Seleccione el esquema](../core/media/biztalk-typepicker.gif "BizTalk_TypePicker")  

    > [!TIP] 
    > **A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** , puede cambiar el tamaño de la ventana del selector de tipos para ver el nombre completo del esquema.
      
     Si solo existe una raíz en el esquema de reemplazo, o se ha establecido un nodo de raíz para el esquema de reemplazo mediante la **referencia raíz** propiedad de la **esquema** abre el nodo, el esquema de reemplazo en el panel correspondiente, y no debe realizar el paso 3.  
  
3.  Si existen múltiples nodos raíz en el esquema de destino, y no se ha establecido ningún nodo de raíz para el esquema de destino mediante el **referencia raíz** propiedad de la **esquema** nodo, en el **raíz Nodo de \< *origen/destino* \> esquema** cuadro de diálogo, seleccione el nodo raíz apropiado y, a continuación, seleccione **Aceptar**.  
  
     El esquema de reemplazo se abre en el panel correspondiente.  
  
    > [!NOTE]
    >  Mientras se reemplaza el esquema, si no se encuentran los registros/campos relevantes, pueden perderse algunos vínculos. El esquema se sustituirá solo cuando se selecciona **Sí** en el **confirmación** cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Administración de asignaciones en proyectos](../core/managing-maps-within-projects.md)