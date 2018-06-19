---
title: Cómo configurar los parámetros de entrada de Functoid | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bts10.mapper.functoid.inputs
ms.assetid: 2c8f773a-932c-423d-b3fe-724265304b0a
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab04111835e7732aa8384e1d701a15ae8d268378
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969546"
---
# <a name="how-to-configure-functoid-input-parameters"></a>Cómo configurar parámetros de entrada de functoid
La configuración correcta de los parámetros de entrada de los functoids en la asignación es uno de los aspectos más importantes, y que más errores potenciales puede ocasionar, al utilizar los functoids. Puede configurar los parámetros de entrada de functoid como sigue:  
  
-   Cree vínculos de entradas visibles al conectar los nodos de esquema y los functoids respectivos (arrastre y suelte el mouse desde el nodo del esquema al functoid).  
  
-   Edite directamente la lista de parámetros de entrada con el **configurar \<Functoid\> Functoid** cuadro de diálogo.  
  
 En este tema se proporcionan instrucciones detalladas para configurar los parámetros de entrada de un functoid mediante estos métodos.  
  
 El método de arrastrar para establecer parámetros de entrada de functoid es una manera adecuada de especificar parámetros de entrada que implican especificaciones de XPath en el esquema de origen. Para obtener información acerca de cómo crear un esquema de parámetros de entrada de functoid y nodo, consulte [cómo agregar Functoids básicos a una asignación](../core/how-to-add-basic-functoids-to-a-map.md). Sin embargo, el **configurar \<Functoid\> Functoid** cuadro de diálogo es el mecanismo definitivo para ver todos los parámetros de entrada a un functoid, para crear y modificar cualquier parámetro constante y de volver a establecer el orden de los parámetros de entrada cuando sea necesario.  
  
 Al configurar los parámetros de entrada para un functoid directamente en la página de cuadrícula (trazando líneas, arrastrando y soltando con el mouse, desde el nodo del esquema de origen y vinculándolo con el functoid), si el número de entradas alcanza el máximo, el cursor cambia a un estado NO. Además, la barra de estado muestra el motivo. La siguiente ilustración muestra un functoid que acepta solo un vínculo de entrada.  
  
 ![SIN estado para configurar el parámetro de entrada de functoid](../core/media/configure-input-parameters-no-state.gif "Configure_input_parameters_NO_state")  
  
 Puede configurar los functoids de secuencias de comandos y el bucle de tabla mediante el **configurar \<Functoid\> Functoid** cuadro de diálogo. Para obtener información sobre cómo configurar los functoids, consulte [cómo configurar el Functoid de secuencias de comandos](../core/how-to-configure-the-scripting-functoid.md) y [cómo configurar el bucle de tabla y el functoid de Extractor de tabla](../core/how-to-configure-the-table-looping-and-table-extractor-functoids.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Estas instrucciones requieren que se está ejecutando el asignador de BizTalk.  
  
## <a name="what-is-an-input-parameter"></a>¿Qué es un parámetro de entrada?  
 Un parámetro de entrada puede ser cualquiera de los siguientes:  
  
-   Un vínculo de un nodo del esquema de origen a un functoid  
  
-   Un vínculo desde un functoid a otro functoid válido  
  
-   Un valor constante  
  
> [!NOTE]
>  Existen algunos functoids, como **fecha**, **tiempo**, **fecha y hora**, y **Nil**, que no necesita ningún parámetro de entrada.  
  
 La siguiente ilustración muestra un functoid (resaltado en rojo) con dos parámetros de entrada (Input[0] e Input[1]) y un parámetro constante (Input[2]).  
  
 ![Mostrar los parámetros de entrada a un functoid](../core/media/identifying-input-parameters.gif "Identifying_input_parameters")  
  
## <a name="to-open-the-configure-functoid-functoid-dialog-box"></a>Para abrir configurar \<Functoid\> cuadro de diálogo de Functoid  
 Puede abrir el **configurar \<Functoid\> Functoid** cuadro de diálogo de una de las maneras siguientes:  
  
-   En la página de cuadrícula correspondiente, haga clic en el functoid y, a continuación, haga clic en **configurar entradas de Functoid**.  
  
-   Haga doble clic en el functoid para el que desea configurar los parámetros de entrada.  
  
-   Seleccione el functoid y, a continuación, haga clic en el botón de puntos suspensivos (**...** ) en la Visual Studio **propiedades** ventana.  
  
-   Seleccione el functoid y presione ENTRAR del teclado.  
  
-   Seleccione el functoid y presione CTRL+M, CTRL+I del teclado. Para obtener una lista de teclas de método abreviado de asignador, vea [métodos abreviados de teclado del asignador de BizTalk](../core/biztalk-mapper-keyboard-shortcuts.md).  
  
### <a name="to-insert-constant-input-parameters"></a>Para insertar parámetros de entrada constantes  
  
1.  En el **configurar \<Functoid\> Functoid** cuadro de diálogo, seleccione la **entradas de Functoid** ficha.  
  
    > [!NOTE]
    >  El **entradas de Functoid** ficha está activada de forma predeterminada.  
  
2.  Haga clic en el ![agregar parámetros de entrada constantes a un functoid](../core/media/add-input-parameters.gif "Add_input_parameters") botón. Se agrega una nueva fila.  
  
3.  Escriba el valor para el nuevo parámetro de entrada y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Si el botón Agregar no está habilitado, el functoid no acepta o no requiere parámetros de entrada, o puede que ya tenga el máximo número de entradas permitidas.  
  
### <a name="to-edit-existing-constant-input-parameters"></a>Para editar parámetros de entrada constantes que ya existen  
  
1.  En el **configurar \<Functoid\> Functoid** cuadro de diálogo, haga clic en la constante existente de entrada de parámetro que desea editar. El valor actual está seleccionado.  
  
    > [!IMPORTANT]
    >  Solo puede editar los parámetros de las entradas constantes. No se pueden editar los parámetros de entrada de todos los demás tipos. Solo se pueden reorganizar o eliminar.  
  
2.  Haga clic en el ![editar parámetros de entrada constantes](../core/media/edit-input-parameters.gif "Edit_input_parameters") botón. Realice los cambios apropiados en el valor constante y, a continuación, haga clic en **Aceptar**.  
  
     Como alternativa, puede hacer doble clic en el parámetro de entrada constante para modificarlo o presionar F2 del teclado.  
  
## <a name="to-select-multiple-input-parameters"></a>Para seleccionar varios parámetros de entrada  
 Para seleccionar varios parámetros de entrada, mantenga presionada la tecla CTRL y haga clic en las filas que desee. A continuación, realice cualquiera de las siguientes operaciones. Presione CTRL+A del teclado para seleccionar todas las filas.  
  
-   Mueva la selección hacia arriba o hacia abajo.  
  
    > [!NOTE]
    >  Si la selección masiva incluye la fila situada en la parte superior o en la parte inferior entre otras, no es posible mover la selección hacia arriba o hacia abajo, respectivamente.  
  
-   Reorganice la selección.  
  
-   Elimine la selección.  
  
### <a name="to-change-the-order-of-existing-input-parameters"></a>Para cambiar el orden de los parámetros de entrada existentes  
  
1.  En el **configurar \<Functoid\> Functoid** cuadro de diálogo, haga clic en las existentes de entrada de parámetro que desee mover a una posición diferente en la lista ordenada de parámetros de entrada.  
  
2.  Haga clic en el ![se desplazan hacia arriba en la lista](../core/media/move-up-button.gif "Move_up_button") botón para mover el parámetro hacia arriba en la lista de parámetros. Repita según sea necesario hasta que el parámetro de entrada seleccionado se encuentre en la posición deseada. Como alternativa, puede presionar la tecla FLECHA ARRIBA del teclado. Para obtener una lista de teclas de método abreviado de asignador, vea [métodos abreviados de teclado del asignador de BizTalk](../core/biztalk-mapper-keyboard-shortcuts.md).  
  
     -OR-  
  
     Haga clic en el ![mover hacia abajo en una lista](../core/media/move-down-button.gif "Move_down_button") botón para mover el parámetro hacia abajo en la lista de parámetros. Repita según sea necesario hasta que el parámetro de entrada seleccionado se encuentre en la posición deseada. Como alternativa, puede presionar la tecla FLECHA ABAJO del teclado. Para obtener una lista de teclas de método abreviado de asignador, vea [métodos abreviados de teclado del asignador de BizTalk](../core/biztalk-mapper-keyboard-shortcuts.md).  
  
    > [!IMPORTANT]
    >  Puede reorganizar la secuencia de entradas solo desde el **configurar \<Functoid\> Functoid** cuadro de diálogo. Si selecciona la fila superiores o inferiores, la ![se desplazan hacia arriba en la lista](../core/media/move-up-button.gif "Move_up_button") o ![mover hacia abajo en una lista](../core/media/move-down-button.gif "Move_down_button")botones se deshabilitaría, respectivamente.  
  
### <a name="to-delete-an-input-parameter-by-deleting-the-input-link"></a>Para eliminar un parámetro de entrada eliminando el vínculo de entrada  
  
1.  En la página de cuadrícula correspondiente, haga clic en el vínculo de entrada que corresponda al parámetro de entrada que desea eliminar.  
  
2.  En el **editar** menú, haga clic en **eliminar**.  
  
    > [!NOTE]
    >  Como alternativa, puede presionar la tecla SUPR o haga clic en el vínculo en la página de cuadrícula correspondiente y haga clic en **eliminar** en el menú contextual.  
  
    > [!IMPORTANT]
    >  El vínculo de entrada se elimina silenciosamente. Siempre puede deshacer la eliminación si no está seguro de ella. Para obtener más información acerca de las operaciones de deshacer/rehacer, consulte [cómo deshacer o rehacer operaciones de usuario](../core/how-to-undo-or-redo-user-operations.md).  
  
### <a name="to-delete-existing-input-parameters-within-the-configure-functoid-functoid-dialog-box"></a>Para eliminar parámetros de entrada existentes en la configuración \<Functoid\> cuadro de diálogo de Functoid  
  
1.  En el **configurar \<Functoid\> Functoid** cuadro de diálogo, haga clic en las existentes de entrada de parámetro que desea eliminar.  
  
    > [!NOTE]
    >  Puede eliminar cualquier parámetro de entrada mediante esta técnica, incluso los que corresponden a un vínculo de entrada.  
  
2.  Haga clic en el ![eliminar la selección](../core/media/delete-button.gif "Delete_button") botón. El parámetro de entrada existente seleccionado se elimina de la lista de parámetros. Haga clic en **Aceptar**.  
  
     También puede seleccionar la fila que desea eliminar y presionar la tecla SUPRIMIR del teclado.  
  
    > [!IMPORTANT]
    >  El parámetro de entrada se elimina silenciosamente. Siempre puede deshacer la eliminación si no está seguro de ella. Para obtener más información acerca de las operaciones de deshacer/rehacer, consulte [cómo deshacer o rehacer operaciones de usuario](../core/how-to-undo-or-redo-user-operations.md).  
  
    > [!NOTE]
    >  El botón Eliminar no está habilitado cuando no hay parámetros de entrada en la lista de parámetros.  
  
## <a name="to-set-labels-and-comments-for-functoids"></a>Procedimiento para establecer etiquetas y comentarios para functoids  
 Puede establecer etiquetas y comentarios para functoids mediante el **configurar \<Functoid\> Functoid** cuadro de diálogo.  
  
1.  En el **configurar \<Functoid\> Functoid** cuadro de diálogo, haga clic en el **etiqueta y comentarios** ficha.  
  
2.  Tipo de la **etiqueta** y **comentarios**y, a continuación, haga clic en **Aceptar**.  
  
    > [!IMPORTANT]
    >  Para obtener más información acerca de cómo etiqueta y comentar functoids y/o vínculos, consulte [cómo etiquetar un vínculo](../core/how-to-label-a-link.md) y [cómo etiquetar y comentar un Functoid](../core/how-to-label-and-comment-a-functoid.md).  
  
## <a name="see-also"></a>Vea también  
 [Editar propiedades de functoid y parámetros de entrada](../core/editing-functoid-properties-and-input-parameters.md)