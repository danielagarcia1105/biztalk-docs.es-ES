---
title: Cómo crear definiciones de vocabulario | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, vocabularies
- vocabularies, creating
- vocabularies, definitions
ms.assetid: 6f8fc4c2-2c46-4a7d-a02f-89de0396e3e2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff9fdfc7cd444a97d1a24353c13d93460c00d4ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250564"
---
# <a name="how-to-create-vocabulary-definitions"></a>Cómo crear definiciones de vocabulario
Puede utilizar el Asistente para definición de vocabulario para crear definiciones de vocabulario. Es posible definir una definición de vocabulario como un valor, un rango de valores, un conjunto de valores constantes o elementos de un ensamblado .NET, un documento XML o una tabla de base de datos. Si selecciona una variable pública, habrá **obtener** y **establecer** opciones al igual que en el Asistente para definición de base de datos y XML.  
  
 Como alternativa, puede crear una nueva definición de vocabulario seleccionando un hecho de una de las tres pestañas: por ejemplo, una columna de base de datos, un nodo XML o un miembro de una clase .NET: arrastrar el hecho de sobre para el **vocabularios** ficha, y colocándolo en una versión no publicada de un vocabulario.  
  
> [!NOTE]
>  No es posible agregar una definición de vocabulario a una versión de vocabulario ya publicada.  
  
### <a name="to-define-a-vocabulary-definition-as-a-constant-value"></a>Para definir una definición de vocabulario como un valor constate  
  
1.  Haga clic en la versión de vocabulario y, a continuación, haga clic en **agregar nueva definición**.  
  
    > [!NOTE]
    >  También puede arrastrar y colocar elementos desde otras pestañas del explorador de hechos: esquemas XML, bases de datos y las clases de .NET  
  
2.  En el Asistente para definición de vocabulario, seleccione **valor constante, rango de valores o conjunto de valores**y, a continuación, haga clic en **siguiente**.  
  
3.  Edite el nombre de definición y la descripción de definición.  
  
    > [!NOTE]
    >  La longitud máxima que se mostrará de un nombre de definición es de 512 caracteres.  
  
4.  Seleccione **valor constante**y, a continuación, haga clic en **siguiente**.  
  
5.  Seleccione un tipo de definición de la lista desplegable de tipos de sistema disponibles.  
  
6.  Editar el nombre para mostrar y el valor y, a continuación, haga clic en **finalizar**.  
  
### <a name="to-define-a-vocabulary-definition-as-a-range-of-values"></a>Para definir una definición de vocabulario como rango de valores  
  
1.  Haga clic en la versión de vocabulario y, a continuación, haga clic en **agregar nueva definición**.  
  
2.  En el Asistente para definición de vocabulario, seleccione **valor constante, rango de valores o conjunto de valores**y, a continuación, haga clic en **siguiente**.  
  
3.  Edite el nombre de definición y la descripción de definición.  
  
4.  Seleccione **rango de valores**y, a continuación, haga clic en **siguiente**.  
  
5.  Seleccione un tipo de definición en la lista desplegable.  
  
6.  Haga clic en **rango bajo**y, a continuación, haga clic en **editar** para especificar los valores del rango bajo. Se abrirá el cuadro de diálogo de definición de parámetros.  
  
7.  Seleccione **usar valor constante** y escriba un valor constante o seleccione **usar definición de vocabulario publicado** y vaya a una definición de vocabulario y, a continuación, haga clic en **Aceptar**.  
  
8.  Repita los pasos 6 y 7 para **rango alto**.  
  
    > [!NOTE]
    >  El **rango alto** valor puede superar el **rango bajo** valor.  
  
9. Escriba la cadena de formato de presentación o haga clic en **predeterminado** para volver a la cadena de formato de presentación predeterminado y, a continuación, haga clic en **finalizar**.  
  
    > [!NOTE]
    >  La cadena de formato debe incluir índices de parámetro entre llaves, por ejemplo, "{0}" y "{1}"—to actúan como marcadores de posición para los parámetros de rango alto y bajo.  
  
     ![Las definiciones de vocabulario](../core/media/3db84492-d6b8-4059-9d2c-a720ccc207b6.gif "3db84492-d6b8-4059-9d2c-a720ccc207b6")  
Rango de valores con cadenas de formato  
  
### <a name="to-define-a-vocabulary-definition-as-a-set-of-values"></a>Para definir una definición de vocabulario como conjunto de valores  
  
1.  Haga clic en la versión de vocabulario y, a continuación, haga clic en **agregar nueva definición**.  
  
2.  En el Asistente para definición de vocabulario, seleccione **valor constante, rango de valores o conjunto de valores**y, a continuación, haga clic en **siguiente**.  
  
3.  Edite el nombre de definición y la descripción de definición.  
  
4.  Seleccione **conjunto de valores**y, a continuación, haga clic en **siguiente**.  
  
5.  Seleccione el tipo de definición y escriba el nombre para mostrar.  
  
6.  Para agregar un miembro al conjunto, seleccione **usar valor constante** y escriba un valor constante o seleccione **usar definición de vocabulario publicado** y vaya a una definición de vocabulario y, a continuación, haga clic en **Agregar**.  
  
7.  Repita el paso 6 con cualquier combinación de definiciones de vocabulario o constantes en tantos elementos como desee incluir en el conjunto.  
  
8.  Para mover un elemento en el orden relativo del conjunto, selecciónelo y, a continuación, haga clic en **una** o **hacia abajo**.  
  
9. Para quitar un miembro del conjunto, selecciónelo y, a continuación, haga clic en **quitar**.  
  
10. Cuando se haya completado el conjunto, haga clic en **finalizar**.  
  
     ![Las definiciones de vocabulario](../core/media/461d0d70-52ed-4f43-927d-3efb1fbfb934.gif "461d0d70-52ed-4f43-927d-3efb1fbfb934")  
Conjunto de valores  
  
### <a name="to-define-a-vocabulary-definition-as-a-net-class-or-class-member"></a>Para definir una definición de vocabulario como miembro de clase y clase .NET  
  
1.  Haga clic en la versión de vocabulario y, a continuación, haga clic en **agregar nueva definición**.  
  
2.  En el Asistente para definición de vocabulario, seleccione **clase .NET o miembro de clase**y, a continuación, haga clic en **siguiente**.  
  
3.  Editar la **nombre de definición de** y **descripción** campos.  
  
4.  Haga clic en **Examinar**.  
  
5.  En el **ensamblados .NET** cuadro de diálogo, seleccione un ensamblado y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Los ensamblados tienen que estar en la caché de ensamblados global (GAC). El Compositor de reglas de negocio carga un ensamblado .NET al buscar el ensamblado de .NET en el **Explorador de hechos** ventana o en la **clase .NET o una definición de miembro de clase** página de la **vocabulario Definición de** ventana.  Si actualiza el ensamblado en la GAC, cierre el Compositor de reglas de negocios y reinícielo para cargar el ensamblado .NET actualizado. El Compositor de reglas de negocio no actualiza el ensamblado de forma automática.  
  
6.  Expanda el nodo del ensamblado.  
  
7.  Seleccione una clase, o expanda una clase y seleccione un miembro de clase y, a continuación, haga clic en **Aceptar**.  
  
8.  Haga clic en **siguiente**y especifique el nombre para mostrar.  
  
     Para obtener más información, consulte más adelante en este tema "Para especificar el formato de presentación de una definición de vocabulario mediante parámetros".  
  
9. Haga clic en **Finalizar**.  
  
     ![Las definiciones de vocabulario](../core/media/4259101f-26dd-488f-81c0-f8d225e4016e.gif "4259101f-26dd-488f-81c0-f8d225e4016e")  
Definición de vocabulario de objeto Net  
  
### <a name="to-define-a-vocabulary-definition-as-an-xml-document-element-or-attribute"></a>Para definir una definición de vocabulario como un atributo o elemento de documento XML  
  
1.  Haga clic en la versión de vocabulario y, a continuación, haga clic en **agregar nueva definición**.  
  
2.  En el Asistente para definición de vocabulario, seleccione **atributo o elemento de documento XML**y, a continuación, haga clic en **siguiente**.  
  
3.  Escriba un nombre de definición y una descripción de la definición.  
  
4.  Haga clic en **examinar** para buscar un archivo de esquema y especificar un atributo o elemento de documento.  
  
5.  Seleccione en la lista desplegable un tipo compatible con el tipo de atributo o elemento del esquema.  
  
    > [!NOTE]
    >  Si no puede llevarse a cabo una conversión válida (en cualquiera de los dos sentidos) entre el tipo especificado y el tipo de atributo o elemento de documento, se producirá un error en tiempo de ejecución.  
  
6.  Seleccione un tipo de operación para indicar si pretende obtener el valor del atributo o elemento (Get) o bien establecer su valor (Set).  
  
7.  Si decide establecer el valor, haga clic en **siguiente**y, a continuación, especifique el formato de presentación.  
  
8.  Haga clic en **Finalizar**.  
  
     ![Las definiciones de vocabulario](../core/media/fd81b534-ec41-4147-b716-1e10ffc01d6f.gif "fd81b534-ec41-4147-b716-1e10ffc01d6f")  
Definición de vocabulario XML  
  
> [!NOTE]
>  La existencia del elemento definido y del tipo de documento no se valida nunca. Si el documento impuesto no contiene el elemento, se producirá un error en tiempo de ejecución. Si impone un documento con un tipo de documento desconocido, se omitirá.  
  
#### <a name="to-define-a-vocabulary-definition-as-a-database-table-or-database-table-column"></a>Para definir una definición de vocabulario como tabla o columna de base de datos  
  
1.  Haga clic en la versión de vocabulario y, a continuación, haga clic en **agregar nueva definición**.  
  
2.  En el Asistente para definición de vocabulario, seleccione **tabla de base de datos o la definición de columna de tabla de base de datos**y, a continuación, haga clic en **siguiente**.  
  
3.  Escriba un nombre de definición y una descripción de definición.  
  
4.  Haga clic en **Examinar**.  
  
5.  Seleccione un equipo de servidor SQL Server al que conectarse. Si el equipo de SQL Server no está iniciado, seleccione el **iniciar SQL Server si está detenido** casilla de verificación.  
  
6.  Seleccione un tipo de autenticación. Si selecciona autenticación de SQL Server, escriba el nombre de inicio de sesión y contraseña y, a continuación, haga clic en **Aceptar**.  
  
7.  Seleccione la tabla o columna de tabla que desea enlazar y, a continuación, haga clic en **Aceptar**.  
  
8.  Si ha seleccionado una columna de tabla, seleccione si desea obtener su valor (Get) o establecerlo (Set). Si escoge obtener su valor, escriba el nombre para mostrar. Si decide establecer su valor, haga clic en **siguiente** para especificar el formato de presentación.  
  
     Para obtener más información, consulte más adelante en este tema "Para especificar el formato de presentación de una definición de vocabulario mediante parámetros".  
  
9. Si ha seleccionado una tabla, escriba un nombre para mostrar.  
  
10. Haga clic en **Finalizar**.  
  
    > [!NOTE]
    >  De forma predeterminada, **DataConnection** se usa el enlace  
  
     ![Las definiciones de vocabulario](../core/media/f8121306-cd73-4997-adc4-71a055dfd824.gif "f8121306-cd73-4997-adc4-71a055dfd824")  
Definición de vocabulario de base de datos  
  
#### <a name="to-specify-the-display-format-of-a-vocabulary-definition-by-using-parameters"></a>Para especificar el formato de presentación de una definición de vocabulario mediante parámetros  
  
1.  Seleccione un parámetro de la lista de **parámetros** en el Asistente para definición de vocabulario y, a continuación, haga clic en **editar**.  
  
2.  Seleccione **usar valor constante** y escriba un valor constante o seleccione **usar definición de vocabulario publicado** y vaya a una definición de vocabulario y, a continuación, haga clic en **Aceptar**.  
  
3.  Escriba la cadena de formato de presentación o haga clic en **predeterminado** para volver a la cadena de formato de presentación predeterminado y, a continuación, haga clic en **finalizar**.  
  
    > [!NOTE]
    >  La cadena de formato debe incluir índices de parámetro entre llaves, por ejemplo, "{0}" y "{1}"—to actúan como marcadores de posición para los parámetros.  
  
     ![Las definiciones de vocabulario](../core/media/822f78f4-278a-4211-83ad-44032fa81f13.gif "822f78f4-278a-4211-83ad-44032fa81f13")  
Definición de vocabulario mediante parámetros