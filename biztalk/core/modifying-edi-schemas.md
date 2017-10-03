---
title: "Modificación de esquemas EDI | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6fa33c5e-17ca-4aaf-a1ca-1972a9bb45ac
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3336d472326dc5ceb8c17e30150039229c18cb77
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="modifying-edi-schemas"></a>Modificación de esquemas EDI
Puede modificar un esquema de EDI existente que se incluye en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Si usted y sus socios comerciales han acordado las modificaciones en esquemas estándar y, quizás, han cambiado el archivo Message Implementation Guideline (MIG) adecuado, puede modificar los esquemas en el Editor de BizTalk en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
> [!NOTE]
>  Algunas modificaciones de esquema (validación de campos cruzados y división de subdocumentos HIPAA) implican cambios en las anotaciones de un esquema EDI. Estos cambios no se pueden realizar en el Editor de BizTalk, pero se pueden realizar en un editor de texto, por ejemplo, Bloc de notas.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="schema-naming-convention"></a>Convención de nomenclatura de esquemas  
 Un esquema EDI se identifica por el nombre de raíz y el espacio de nombres. No puede implementar dos esquemas del mismo grupo de BizTalk con el mismo nombre de raíz y espacio de nombres. No es posible modificar el nombre de raíz de ningún esquema EDI o agregarlo al nombre de raíz, ya que el nombre de raíz debe contener la versión y el tipo de documento con una convención de nomenclatura estándar. Como resultado, si desea implementar dos esquemas en el mismo grupo de BizTalk con el mismo nombre de raíz, debe usar un espacio de nombres distinto para cada uno.  
  
 Es habitual para una compañía implementar en el mismo grupo de BizTalk una versión distinta del mismo esquema para dos o más socios comerciales distintos. En este caso, los dos esquemas tienen la misma versión y el mismo tipo de documento. Para implementar estos dos esquemas, es necesario disponer de distintos espacios de nombre para cada uno de los esquemas.  
  
## <a name="edi-schema-changes"></a>Cambios del esquema EDI  
 Puede realizar los siguientes cambios en un esquema EDI en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]:  
  
|Para|Haga esto|  
|----------------|-------------|  
|Cambiar una enumeración<br /><br /> (por ejemplo, la lista de valores de una lista de códigos)|En las propiedades de un elemento, abra el **Editor de enumeración** y agregar un valor, o elimine un valor de la lista de enumeración.|  
|Cambiar la opcionalidad de un elemento de datos|Cambiar el **Min Occurs** propiedad. Cámbielo a 0 para hacer que el campo sea opcional o a 1 para que sea obligatorio.|  
|Cambiar el número máximo de veces que un elemento de datos puede aparecer en el archivo|Cambiar el **Max Occurs** propiedad.|  
|Cambiar el número de caracteres del elemento de datos|Cambiar el **longitud** propiedad.|  
|Cambiar el tipo de datos de un elemento de datos|Cambiar el **Base Data Type** o **Date (tipo)** propiedad.|  
|Agregar un campo personalizado|Inserte un nodo de esquema de elemento de campo secundario y establezca las propiedades. **Nota:** agregar un atributo de campo secundario a un registro de un esquema EDI no está permitido, porque no se garantiza la secuencia de los elementos. Si intenta agregar un atributo de campo secundario, obtendrá como resultado un esquema no válido. Sólo se puede agregar un elemento de campo secundario a un registro de un esquema EDI.|  
|Agregar un registro personalizado|Inserte un nodo de esquema de registro secundario, establezca las propiedades y agregue elementos de campo secundarios.|  
|Eliminar un campo o registro personalizado|Elimine un campo o registro personalizado con los elementos de campo secundarios.|  
|Habilitar validación de campos cruzados|Establecer la marca de validación de campos cruzados en la anotación en la sección appinfo del esquema al **Sí**. Esta marca es **X12ConditionDesignator_Check** (para esquemas X12 o HIPAA) o **EdifactDependencyRule_Check** (para esquemas EDIFACT).<br /><br /> Habilite la validación de campos cruzados para un elemento específico mediante la especificación de las condiciones relacionales (X12 e HIPAA) o las reglas de dependencia (EDIFACT). Para obtener más información, consulte [configuración de validación de campos cruzados](../core/configuring-cross-field-validation.md).<br /><br /> También debe establecer el **validación de tipo Edi** propiedad **Sí**.<br /><br /> Validación entre campos está habilitada de forma predeterminada para los esquemas HIPAA.|  
|Habilitar división de subdocumento HIPAA|En uno de los esquemas HIPAA que se puede establecer la división de subdocumentos, establezca el **subdocument_break** y **Split_Without_Sibling_Data** propiedades para el esquema como **Sí** y el **subdocument_creation_break** propiedad para un elemento específico en el esquema para **Sí**.<br /><br /> También debe establecer el **opción de procesamiento por lotes de entrada** propiedad de acuerdo a **dividir intercambio como conjuntos de transacciones**.<br /><br /> Para obtener más información, consulte [dividir subdocumentos HIPAA](../core/splitting-hipaa-subdocuments.md).|  
|Agregar campos desencadenadores a un documento HIPAA|Puede permitir que el desensamblador de EDI cree registros XML exclusivos para un segmento de su documento HIPAA basándose en un elemento de calificación conocido como campo desencadenador. Debe especificar los atributos que describen el segmento y el valor desencadenador de modo que se cree un registro XML exclusivo para el segmento. Para obtener más información, consulte [anotaciones de campo desencadenador HIPAA esquema](../core/hipaa-schema-trigger-field-annotations.md).|  
|Agregar un segmento a un conjunto de transacciones X12|Cuando agrega un segmento nuevo a un conjunto de transacciones X12, los tres primeros caracteres del nombre del segmento se usan como identificador del segmento. Por tanto, recomendamos que asigne al segmento un nombre tal que los tres primeros caracteres sean únicos.|  
|Agregar un bucle a un conjunto de transacciones HIPAA|Al agregar un nuevo bucle a un conjunto de transacciones HIPAA, recomendamos asignar nombre al bucle para incluir “Bucle” en el n ombre. Un formato de ejemplo para un bucle es “TS837_2010AB_Loop”. **Nota:** el primer segmento en un bucle es obligatorio (minOccurs del segmento debe ser igual a 1) con el fin de evitar la ambigüedad.|  
|Agregar un ‘bucle en cualquier orden’ a un conjunto de transacciones HIPAA|Cuando un conjunto de transacciones tiene segmentos equivalentes con diferente semántica, debe definirlos en un subbucle. Un subbucle con la anotación XML \<xs: all > permite que segmentos equivalentes tengan lugar en cualquier orden.<br /><br /> Recomendamos asignar nombre al ‘bucle en cualquier orden’ de modo que se incluya “SubLoop” en el nombre. Un ejemplo de formato es "TS837Q1_2010A_SubLoop" **Nota:** los elementos de un bucle en cualquier orden solo deben aparecer una vez dentro del bucle. Los hermanos de un subbucle deben tener maxOccurs configurado en 1, para evitar ambigüedades.|  
  
### <a name="to-modify-an-existing-edi-schema-in-biztalk-editor"></a>Para modificar un esquema EDI existente en el Editor de BizTalk  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], agregue el esquema que desea modificar a un proyecto y abra el esquema en BizTalk Editor.  
  
    > [!NOTE]
    >  Puede ver el esquema en formato gráfico haciendo clic en el **EDI** ficha en la parte inferior de la pantalla del Editor de esquemas. Es mucho más sencillo desplazarse por los nodos del esquema con este formato tabular.  
  
2.  Para cambiar las propiedades de un elemento de datos o de un registro, haga clic en el nodo correspondiente del panel izquierdo del Editor de BizTalk y cambie las propiedades en la ventana Propiedades.  
  
3.  Para cambiar los valores de una enumeración, seleccione la enumeración en el **propiedades** panel y, a continuación, haga clic en el botón de puntos suspensivos para abrir el **Editor de enumeración**. Agregar o eliminar datos de la lista de valores, según sea necesario, asegurándose de que hay un valor en cada línea en el **valores** panel. Haga clic en **Aceptar**.  
  
4.  Para agregar un campo personalizado para el esquema, haga clic en un nodo de registro en el árbol de consola del Editor de BizTalk, seleccione **Insertar nodo de esquema**y haga clic en **elemento de campo secundario**. Asigne un nombre al elemento de datos y, a continuación, arrastre el elemento de datos a la posición adecuada del registro. Establezca las propiedades para las propiedades del campo personalizado como necesarias.  
  
    > [!NOTE]
    >  No se permite agregar un atributo de campo secundario a un registro de un esquema EDI, ya que no se garantiza la secuencia de los elementos. Si intenta agregar un atributo de campo secundario, obtendrá como resultado un esquema no válido.  
  
5.  Para agregar un registro personalizado para el esquema, haga clic en un nodo de registro en el árbol de consola del Editor de esquemas, seleccione **Insertar nodo de esquema**y, a continuación, haga clic en **registro secundario**. Asigne un nombre al registro y arrastre el registro a la posición adecuada del esquema. Agregue como mínimo un elemento de datos al registro. Establezca las propiedades para el registro personalizado como necesarias.  
  
6.  Después de realizar los cambios deseados en el esquema, puede cambiar el espacio de nombres de destino que se aplica a la propiedad de esquema haciendo clic en el nodo raíz (\<esquema >) y, a continuación, cambie la **Target Namespace** propiedad.  
  
7.  Guarde el esquema.  
  
8.  Validar el esquema haciendo clic en el esquema en el Explorador de soluciones y haga clic en **Validar esquema**.  
  
    > [!NOTE]
    >  El **Validar esquema** comando validará el esquema EDI ya la **extensión del Editor de esquema** propiedad del nodo raíz (\<esquema >) se establece en **Editor de esquemas EDI Extensión**.  
  
### <a name="to-modify-annotation-properties-in-an-existing-edi-schema"></a>Para modificar propiedades de anotación en un esquema EDI existente  
  
1.  Abra el esquema en un editor de texto, como por ejemplo, Bloca de notas.  
  
2.  Para habilitar la validación de campos cruzados, haga lo siguiente. Para obtener más información, consulte [configuración de validación de campos cruzados](../core/configuring-cross-field-validation.md).  
  
    1.  En la anotación appinfo en la parte superior del esquema, establezca la marca de validación de campos cruzados (ya sea **X12ConditionDesignator_Check** para esquemas X12 o HIPAA o **EdifactDependencyRule_Check** para EDIFACT esquemas) a **Sí**.  
  
        > [!NOTE]
        >  La marca de validación de campos cruzados es **Sí** de forma predeterminada para [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] esquemas HIPAA.  
  
    2.  En la anotación de un elemento específico, especifique las condiciones relacionales (X12 o HIPAA) o las reglas de dependencia (EDIFACT) del elemento. Para obtener más información acerca de estas opciones, consulte [validación cruzada de segmentos de campos](../core/cross-field-segment-validation.md).  
  
        > [!NOTE]
        >  En el **validación** página (bajo la **configuración del conjunto de transacciones** sección) de la ficha de acuerdo unidireccional el **propiedades del acuerdo de** cuadro de diálogo acuerdo correspondiente, Asegúrese de que el **validación de tipo EDI** propiedad está seleccionada.  
  
3.  Para habilitar la división de subdocumentos HIPAA, haga lo siguiente. Para obtener más información, consulte [dividir subdocumentos HIPAA](../core/splitting-hipaa-subdocuments.md).  
  
    1.  En la anotación appinfo en la parte superior del esquema, establezca el **subdocument_break** y **Split_Without_Sibling_Data** marcas **Sí**.  
  
    2.  En la anotación appinfo para un elemento específico, consulte la **subdocument_creation_break** indicador en **Sí**.  
  
        > [!NOTE]
        >  En el **configuración de Host Local** página (bajo la **configuración de intercambio** sección) de la ficha de acuerdo unidireccional el **propiedades del acuerdo de** cuadro de diálogo correspondiente acuerdo, asegúrese de que el **opción de procesamiento por lotes de entrada** propiedad está establecida en **dividir intercambio como conjuntos de transacciones**.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollo de esquemas EDI](../core/developing-edi-schemas.md)