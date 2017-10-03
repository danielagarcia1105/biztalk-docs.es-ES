---
title: "Cómo crear referencias a otro nodo o tipo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c60be9ad-01a9-40e7-b43b-8c3d09bbb32f
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 643f39b9a42e2566f77371096d7305f56e11a328
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="create-references-to-another-node-or-type"></a>Crear referencias a otro nodo o tipo
Puede usar nodos globales para crear tipos de datos reutilizables, fragmentos de estructura, que puede usar en todo el esquema siempre que esa estructura sea la adecuada. Solo puede usar los nodos que son elementos secundarios directos de la **esquema** nodo para crear tipos globales.  
  
 También puede crear referencias cíclicas con los tipos de datos de nodos que no sean descendientes directos de la **esquema** nodo. Esto resulta útil para representar estructuras recursivas en los esquemas.  
  
 Este tema proporciona instrucciones paso a paso para varios tipos de nodos globales y sobre cómo hacer referencia a ellos para utilizarlos.  
  
 **Crear declaraciones globales**  
  
 Se pueden crear tipos globales mediante registros, campos o atributos. Los tipos globales creados a partir de registros solo se pueden usar en registros; los tipos creados a partir de campos solo se pueden utilizar en campos; y los tipos de atributos, solo en atributos. Los siguientes procedimientos describen cómo definir y utilizar declaraciones globales.  
  
## <a name="create-a-global-declaration-from-a-node"></a>Crear una declaración global a partir de un nodo  
  
1.  Seleccione el **registro** , **atributo de campo**, o **elemento de campo** nodo cuyo tipo desea que esté disponible globalmente.  
  
2.  En el **propiedades** ventana, escriba un nombre en el **Data Structure Type** lista que se usará como el nombre del tipo complejo global y, a continuación, presione ENTRAR.  
  
## <a name="create-a-globally-defined-sequence-group-node-choice-group-node-or-all-group-node"></a>Crear un nodo grupo de secuencia definido globalmente, el nodo grupo de elecciones o el nodo todos los grupos  
  
1.  Seleccione el **registro** nodo en el que desea insertar el nodo de grupo definido globalmente.  
  
2.  En el **BizTalk** menú, elija **Insertar nodo de esquema**y, a continuación, haga clic en **grupo de secuencias**, **grupo de elecciones**, o **todos los Grupo**, según corresponda.  
  
3.  Cree una estructura en el grupo que acaba de insertar. Por ejemplo, insertar **registro** o **elemento de campo** nodos para expresar la estructura de los datos dentro del nodo de grupo.  
  
    > [!NOTE]
    >  Grupo de secuencias, **grupo de elecciones**, y **todos los grupos** nodos solo pueden contener nodos que corresponden a elementos XML y, por tanto, no pueden contener **atributo de campo** nodos.  
  
4.  Seleccione el nodo de grupo insertado en el paso 2.  
  
5.  En la ventana Propiedades, haga clic en **Group Reference**, escriba un nombre en el campo de valor y, a continuación, presione ENTRAR.  
  
     Al proporcionar un nombre en el **Group Reference** propiedad, ha definido globalmente nodo de grupo, después del cual puede asociar otros nodos de grupo con este tipo definido globalmente (estructura).  
  
## <a name="create-a-globally-defined-attribute-group-node"></a>Crear un nodo de grupo de atributos definido globalmente  
  
1.  Seleccione el **registro** nodo en el que desea insertar definido globalmente **grupo de atributos** nodo.  
  
2.  En el **BizTalk** menú, elija **Insertar nodo de esquema**y, a continuación, haga clic en **grupo de atributos**.  
  
     Esto agrega un **grupo de atributos** nodo al final de los nodos secundarios en seleccionado **registro** nodo.  
  
3.  Agregar adecuado **atributo de campo** o **grupo de atributos** nodos para su **grupo de atributos**.  
  
4.  Opcionalmente, si desea cambiar el nombre de la **grupo de atributos** nodo, seleccione el **grupo de atributos** nodo y cambie su **Group Reference** propiedad a un nuevo nombre de su elección.  
  
     Los grupos de atributos son siempre globales y se hace referencia a ellos a partir del punto de uso.  
  
## <a name="use-a-type-or-group-that-has-been-globally-defined"></a>Usar un tipo o un grupo definido globalmente  
  
1.  Seleccione el nodo para el que desea utilizar un tipo definido globalmente.  
  
2.  En la ventana Propiedades, seleccione el tipo definido globalmente en la lista desplegable de la **Data Structure Type** propiedad (**registro** nodos), **tipo de datos** propiedad ( **Elemento de campo** y **atributo de campo** nodos), o **Group Reference** (**grupo de secuencias**, **grupo de elecciones**, **Todos los grupos**, y **grupo de atributos** nodos). Para obtener más información acerca de estas propiedades [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
    > [!NOTE]
    >  Los cambios posteriores al tipo o grupo definido globalmente se pueden hacer en cualquiera de las ubicaciones del esquema en las que aparece. Estos cambios se aplicarán a todas las ubicaciones (igual que si los realizase en las ubicaciones arbitrarias individuales).  
  
 Tras crear un declaración global, no se puede eliminar en un solo paso. Sin embargo, puede eliminar mediante el **limpiar tipos de datos globales** cuadro de diálogo cuando se guarda el esquema, mediante el procedimiento siguiente.  
  
## <a name="delete-a-global-declaration"></a>Eliminar una declaración global  
  
1.  Elimine todos los nodos en los que se use este tipo o grupo global, o bien, especifique un tipo o grupo diferente para usarlo en todos estos nodos, o alguna combinación de los mismos. Para obtener instrucciones paso a paso para eliminar un nodo, vea [eliminar nodos](../core/how-to-delete-nodes.md).  
  
2.  Al guardar su especificación, el **limpiar tipos de datos globales** aparece el cuadro de diálogo. Seleccione la declaración global que desea eliminar completamente de su especificación y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  El **limpiar tipos de datos globales** aparece el cuadro de diálogo cada vez que guarde un esquema con tipos de datos no usados. Si no se muestra este cuadro de diálogo, se utilizan todos los tipos de datos en alguna parte del esquema o no se ha modificado el esquema desde que se abrió (en este último caso, todavía podría incluir tipos de datos no usados que se guardaron anteriormente).  
  
## <a name="create-cyclical-references-to-another-node"></a>Crear referencias cíclicas a otro nodo  
 Puede crear referencias cíclicas a un nodo para representar elementos de esquema recursivos. Para hacerlo, se crea un nodo cuyo tipo está definido por un registro envolvente. Por ejemplo, suponga un mensaje de instancia que está envuelto por un número arbitrario de sobres con la misma estructura. Con las referencias cíclicas, puede crear un esquema que defina tales mensajes de instancia.  
  
### <a name="create-a-cyclical-reference"></a>Crear una referencia cíclica  
  
1.  Seleccione un **registro** nodo para el que desea crear una referencia recursiva. Éste es el nodo que representa la parte superior de la estructura recursiva.  
  
2.  En la ventana Propiedades, compruebe que la **Data Structure Type** tiene un valor.  
  
     Comprobar que la **registro** nodo tiene un conjunto con nombre tipo asociado con él es necesario porque estructuras recursivas se definen cuando un tipo se incluye a sí mismo. Los tipos solo pueden incluirse a sí mismos mediante el uso anidado de tipos globales con nombre.  
  
3.  Seleccione un elemento secundario **registro** nodo o insertar un elemento secundario **registro** nodo.  
  
4.  Para el elemento secundario **registro** nodo, en la ventana Propiedades, en la **Data Structure Type** , seleccione la estructura de datos identificada en el paso 2.  
  
> [!IMPORTANT]
>  - El **Min Occurs** propiedad para el nodo repetido debe establecerse en cero (**0**). Si se establece en uno (**1**) produce un bucle infinito.  
>
>  - Si importa un esquema que incluya un elemento recursivo, el Editor de BizTalk no comprueba automáticamente que el elemento recursivo sea válido.  
  
## <a name="see-also"></a>Vea también  
 [Administrar los nodos de un esquema](../core/managing-the-nodes-within-a-schema.md)