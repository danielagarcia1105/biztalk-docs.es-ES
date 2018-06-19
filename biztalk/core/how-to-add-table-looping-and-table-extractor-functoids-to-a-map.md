---
title: Cómo agregar el bucle de tabla y Functoids de extractor de tablas a una asignación de tabla | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c837ab8-55db-471a-af26-9fbd0497d7d4
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4b7844260b7ac5ab29f204a538e61cb99b0d017
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249796"
---
# <a name="how-to-add-table-looping-and-table-extractor-functoids-to-a-map"></a>Cómo agregar functoids de bucle de tabla y de extractor de tablas a una asignación
El **bucle de tabla** y **Extractor de tablas** functoids se usan juntos. El **bucle de tabla** el functoid tiene una tabla interna configurable. Para cada entrada de registro o campo, el **bucle de tabla** functoid genera las filas de la tabla, de uno en uno. El **Extractor de tablas** functoid extrae el elemento deseado de una fila y lo pasa al mensaje de instancia de salida.  
  
 Para obtener información conceptual acerca de la **bucle de tabla** y **Extractor de tablas** functoids, consulte [bucle de tabla y Functoids de Extractor de tabla](../core/table-looping-and-table-extractor-functoids.md).  
  
### <a name="to-add-the-table-looping-and-table-extractor-functoids-to-a-map-and-configure-them"></a>Para agregar functoids de bucle de tabla y de extractor de tablas a fin de asignarlos y configurarlos  
  
1.  Con el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] haga clic en cuadro de herramientas activa, el **Functoids avanzados** tab para seleccionar esta categoría de functoids.  
  
     Aparece la lista de functoids avanzados de la categoría seleccionada.  
  
2.  Arrastre el **bucle de tabla** functoid (![](../core/media/advtablelooping.gif "advtablelooping")) en el cuadro de herramientas hasta la ubicación adecuada en una página de cuadrícula.  
  
    > [!NOTE]
    >  El functoid se colocará en la página de cuadrícula mostrada. Si desea colocar el functoid en una página de cuadrícula diferente, necesitará mostrar en primer lugar la página de cuadrícula.  
  
    > [!NOTE]
    >  Dado que la salida de la **bucle de tabla** functoid actúa como entrada para uno o varios asociados **Extractor de tablas** functoids, asegúrese de dejar espacio a la derecha de la **debucledetabla** functoid para el **Extractor de tablas** functoids.  
  
3.  Arrastre un registro o campo del esquema de origen a recién agregado **bucle de tabla** functoid. Como primer parámetro de entrada a la **bucle de tabla** functoid, el número de repeticiones de este registro o campo en un mensaje de instancia controlará el número de veces que este functoid produce un resultado. Por ejemplo, si un registro de bucle se arrastra hasta el functoid y se procesa un mensaje de instancia que tiene 10 repeticiones de este registro y se ha configurado la cuadrícula de tabla con una fila de los orígenes de datos de columna, el **bucle de tabla** iterará functoid 10 veces, generar 10 filas de salida por extracción mediante un **Extractor de tablas** functoid y permitir destino 10 registros a crearse fácilmente.  
  
    > [!NOTE]
    >  Si configura múltiples filas en la cuadrícula de tabla, cada fila se transferirán para cada iteración de la **bucle de tabla** functoid. Por lo tanto, el número de apariciones de un registro de entrada por el número de filas configuradas en la cuadrícula de tabla equivale al número de filas de tabla de salida disponibles para la extracción de datos.  
  
4.  Arrastre un registro o campo desde el esquema de destino para la **bucle de tabla** functoid. Este vínculo garantiza la creación del nodo en el esquema de destino.  
  
5.  Seleccione recién agregado **bucle de tabla** functoid y en el **propiedades** ventana, haga clic en el botón de puntos suspensivos (**...** ) asociado a su **parámetros de entrada** propiedad.  
  
    > [!NOTE]
    >  Como alternativa, puede seleccionar el functoid y presionar CTRL+M, CTRL+T del teclado. Para obtener una lista del asignador de consulte métodos abreviados de teclado [métodos abreviados de teclado del asignador de BizTalk](../core/biztalk-mapper-keyboard-shortcuts.md).  
  
6.  En el **configurar Functoid de bucle de tabla** cuadro de diálogo, haga clic en el ![agregar parámetros de entrada constantes a un functoid](../core/media/add-input-parameters.gif "Add_input_parameters") botón para crear el segundo parámetro de entrada. Escriba un número que representa el número de columnas que estarán disponibles en la tabla que se va a crear para esta **bucle de tabla** functoid.  
  
    > [!NOTE]
    >  El número máximo columnas en la tabla es 228.  
  
7.  En el **configurar Functoid de bucle de tabla** cuadro de diálogo, haga clic en el ![agregar parámetros de entrada constantes a un functoid](../core/media/add-input-parameters.gif "Add_input_parameters") para escribir cualquier constante valores que aparece en la cuadrícula de tabla configurada. El orden en que cree estas constantes no es importante en este cuadro de diálogo, dado que los valores del primer y del segundo parámetros, el número de filas y columnas respectivamente, mantienen sus posiciones al comienzo de la lista de parámetros de entrada. Cuando haya terminado, haga clic en **Aceptar**.  
  
     El **configurar Functoid de bucle de tabla** cierra el cuadro de diálogo.  
  
8.  Arrastre cero o más nodos de registro o campo del esquema de origen a la **bucle de tabla** functoid que ha agregado recientemente. Todos estos nodos de registro o de campo se agregan al final de la lista de parámetros de entrada y, por lo tanto, estarán disponibles cuando la cuadrícula de tabla esté configurada en un paso posterior. Al igual que ocurría con las constantes de datos de tabla agregadas previamente (no las constantes de números de filas y columnas), el orden en que se agregan estos nodos de registros y de campos no es importante en última instancia.  
  
9. Para etiquetar un vínculo, siga estos pasos:  
  
    -   Seleccione un vínculo en la página de cuadrícula mostrada.  
  
    -   En el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades, proporcione un nombre descriptivo para la **etiqueta** propiedad. Por ejemplo, puede dar un nombre como "link2ndAuthor" a un vínculo procedente de un campo llamado "Segundo autor".  
  
10. Seleccione recién agregado **bucle de tabla** functoid y en el **propiedades** ventana, haga clic en el botón de puntos suspensivos (**...** ) asociado a la **cuadrícula de bucle de tabla** propiedad asociada a este functoid.  
  
     El **configurar Functoid de bucle de tabla** aparece el cuadro de diálogo con el **cuadrícula de bucle de tabla** pestaña seleccionada.  
  
    > [!NOTE]
    >  O bien, haga clic en el functoid y, a continuación, haga clic en **configurar cuadrícula de bucle de tabla** en el menú contextual. El **configurar Functoid de bucle de tabla** aparece el cuadro de diálogo con el **cuadrícula de bucle de tabla** pestaña seleccionada.  
  
11. Use las listas desplegables asociadas a cada celda de la tabla para configurar al menos una (o quizá varias) de las filas de la cuadrícula. Las opciones disponibles en las listas desplegables son las constantes y vínculos que se hayan configurado en los pasos 6 a 8 como parámetros de entrada 3 y hasta el **bucle de tabla** functoid. (Los parámetros de entrada 1 y 2 no aparecen en estas listas desplegables). Cuando haya terminado, haga clic en **Aceptar**.  
  
     El **configurar Functoid de bucle de tabla** cierra el cuadro de diálogo.  
  
    > [!NOTE]
    >  Cada fila es una repetición de la estructura de salida, en combinación con el número de apariciones del registro o campo especificado como primer parámetro de entrada de la **bucle de tabla** functoid. Para obtener más información, vea el paso 3.  
  
    > [!NOTE]
    >  Debe seleccionar un valor para cada columna que se va a tener acceso mediante un **Extractor de tablas** functoid. Si no se utiliza una columna por un **Extractor de tablas** functoid, debe considerar quitar, en lugar de mantener esa columna.  
  
    > [!NOTE]
    >  El orden en que se rellene la cuadrícula de tabla no tiene importancia.  
  
12. Arrastre tantas **Extractor de tablas** functoids (![](../core/media/advtableextractor.gif "advtableextractor")) en el cuadro de herramientas a la página de cuadrícula mostrada según sea necesario.  
  
    > [!NOTE]
    >  Dado que la entrada de estos **Extractor de tablas** functoids procede de la **bucle de tabla** functoid agregado en un paso anterior, asegúrese de que se coloca el **Extractor de tablas** functoids a la derecha de la **bucle de tabla** functoid en la página de cuadrícula mostrada.  
  
13. Para crear el primer parámetro de entrada para uno de los **Extractor de tablas** functoids que agregó en el paso 9, arrástrelo a la correspondiente **bucle de tabla** functoid hacia su izquierda.  
  
14. Para crear el segundo parámetro de entrada para el mismo **Extractor de tablas** functoid, seleccione el functoid y en el **propiedades** ventana, haga clic en el botón de puntos suspensivos (**...** ) asociado a su **parámetros de entrada** propiedad.  
  
     El **configurar Functoid de Extractor de tabla** aparece el cuadro de diálogo.  
  
15. Haga clic en el ![agregar parámetros de entrada constantes a un functoid](../core/media/add-input-parameters.gif "Add_input_parameters") botón para crear el segundo parámetro de entrada. Escriba el número de la columna en la cuadrícula de tabla de los correspondientes **bucle de tabla** functoid desde el que desea extraer datos. Haga clic en **Aceptar**.  
  
     El **configurar Functoid de Extractor de tabla** cierra el cuadro de diálogo.  
  
    > [!NOTE]
    >  Los números de columna empiezan en 1.  
  
16. Para usar el resultado de la **Extractor de tablas** functoid, arrastre el **Extractor de tablas** functoid a un nodo registro o campo en el esquema de destino, o arrastre un nodo registro o campo del esquema de destino para el  **Extractor de tabla** functoid. El valor de atributo o elemento de un mensaje de instancia de destino correspondiente a este nodo de registro o de campo del esquema de destino se completará con el valor de la celda especificada en la cuadrícula de tabla (en el caso de constantes) o con el valor indicado también en esa celda (en el caso de vínculos).  
  
17. Repita los pasos 12, 13, 14 y 15 para cada uno de los **Extractor de tablas** functoids que agregó en el paso 11.  
  
## <a name="see-also"></a>Vea también  
 [Agregar Functoids avanzados a un mapa](../core/adding-advanced-functoids-to-a-map.md)