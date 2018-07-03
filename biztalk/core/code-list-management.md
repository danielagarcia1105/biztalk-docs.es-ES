---
title: Administración de la lista de código | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a924c814-d077-4aea-bacb-bf2e8a3dee01
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a28126d7acdb7e5d97b6aaa9924cea455c5fad1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010733"
---
# <a name="code-list-management"></a>Administración de la lista de código

## <a name="overview"></a>Información general
Utilice XSD para especificar un conjunto específico de valores que sean válidos para un elemento o un atributo. Esta funcionalidad está disponible mediante la **enumeración** elemento. Al derivar un tipo de datos para un **elemento de campo** o **atributo de campo** nodo por restricción, una de las propiedades que pasa a estar disponibles en el **restricción** categoría es la **enumeración** propiedad. Con esta propiedad, puede abrir el **Editor de enumeración** cuadro de diálogo donde puede escribir los valores que deben considerarse válidos para el elemento o atributo correspondiente en los mensajes de instancia.  

 Microsoft BizTalk Server proporciona una forma alternativa más eficaz de administrar las enumeraciones de los esquemas denominada listas de códigos. Las listas de códigos utilizan una base de datos de Microsoft Access para almacenar las opciones de las distintas enumeraciones, lo que permite una administración más centralizada de ellas. Asimismo, si los valores de enumeración que deba usar constan de códigos numéricos no intuitivos, que deben escribirse en ese formulario mediante el **enumeración** propiedad, las tablas que cree una base de datos para usar con la lista de códigos funcionalidad incluyen descripciones textuales de esos valores numéricos. Se utilizan descripciones textuales en la **CodeList** cuadro de diálogo, en lugar de sus más ocultar equivalentes numéricos.  

## <a name="use-the-code-list"></a>Use la lista de código  
 Debe realizar varios pasos para usar la característica de lista de códigos, entre ellos:  

- Debe crear una base de datos de Access con una tabla que tenga un nombre adecuado y las columnas apropiadas, y rellenar los valores.  

  - El nombre de la tabla es una combinación de la **estándar** y **versión estándar** propiedades de la **esquema** nodo, separado por un carácter de subrayado (_). Por ejemplo, si ha establecido la **estándar** propiedad de la **esquema** nodo para XML y el **versión estándar** propiedad en MyVersion1, la base de datos de Access especificada por el **Base de datos de listas de códigos** propiedad debe tener una tabla denominada XML_MyVersion1.  

    Para obtener más detalles acerca de estas propiedades [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].

  - Esta tabla debe tener tres columnas, normalmente denominadas Código, Valor y Descripción. La primera columna identifica las filas que se relacionan entre sí, donde cada fila proporciona una de las opciones de enumeración que potencialmente se permiten para los datos que se corresponde con el texto seleccionado **elemento de campo** o **Atributo de campo** nodo. Todas las filas que tienen el mismo valor en la primera columna forman un grupo. Estos valores son normalmente enteros, pero pueden ser cualquier cadena que no contenga espacios.  

     La segunda y tercera columnas de cada fila de la tabla deben configurarse de modo que contengan el valor y la representación textual correspondiente de cada valor de enumeración posible, respectivamente.  

     Por ejemplo, la siguiente representación de una tabla de base de datos de Access, para usarse con la característica de lista de códigos, contiene dos conjuntos de tres valores de enumeración relacionados. Los valores específicos de la primera columna son arbitrarios y se utilizan para asociar filas relacionadas.  


    | código | Valor |  DESC  |
    |------|-------|--------|
    |  1   |  13   |  Rojo   |
    |  1   |  16   | Verde  |
    |  1   |  19   |  Azul  |
    |  2   |   1   | Pequeño  |
    |  2   |   2   | Media |
    |  2   |   3   | Grande  |


- Debe configurar correctamente tres propiedades de la **esquema** nodo:  

  -   El **base de datos de listas de códigos** propiedad debe establecerse en el nombre de la base de datos de Access que creó.  

  -   El **estándar** y **versión estándar** propiedades deben establecerse de modo que cuando se combinan con un carácter de subrayado (_) de separación, forman el nombre de la tabla correspondiente de la especificada Base de datos de Access.  

- Para realmente hacer uso de los valores de la base de datos de acceso para un determinado seleccionado **elemento de campo** o **atributo de campo** nodo, debe configurar dos de sus propiedades:  

  -   Debe establecer su **Derived By** propiedad **restricción**. La otra propiedad que deba configurar, **CodeList**, no se habilitará hasta que realice este paso.  

  -   Debe escribir un valor en el **CodeList** propiedad que corresponde al valor de la primera columna (la **código** columna) de una o varias filas en la base de datos de acceso especificada. Esta acción identifica el conjunto de valores de enumeración que desea que tengan una correspondencia seleccionada **elemento de campo** o **atributo de campo** nodo.  

       Debe hacer clic en el botón de puntos suspensivos (**...** ) situado a la derecha de la **CodeList** campo de valor de propiedad para abrir el **CodeList** cuadro de diálogo. Mediante las casillas de verificación en este cuadro de diálogo, seleccione los valores que desea admitir como valores permitidos para los datos del mensaje de instancia que corresponde a la seleccionada **elemento de campo** o **atributo de campo** nodo. Solo puede seleccionar un subconjunto de los valores disponibles. Por ejemplo, utilizando el anterior ejemplo de tabla, si escribe el valor 1 en el **CodeList** propiedad, el **CodeList** cuadro de diálogo contendrá las opciones rojo, verde y azul. Si selecciona las casillas de verificación de rojo y verde y no active la casilla de verificación azul, solo los colores anteriores aparecerán en el XSD como los valores válidos para el **elemento de campo** o **atributo de campo** nodo.  

> [!NOTE]
>  El **CodeList** y **base de datos de listas de códigos** propiedades se usan en tiempo de diseño solo y se almacenan en el XSD como valores correspondientes para el **enumeración** propiedad. En tiempo de ejecución, se comprueban todos los valores con el **enumeración** solo para la propiedad.  

> [!CAUTION]
>  Para un determinado **elemento de campo** o **atributo de campo** nodo, no use tanto la **enumeración** propiedad y el **CodeList** propiedad. Si usa esta última propiedad, puede que se sobrescriban los valores especificados con la primera propiedad.  

## <a name="see-also"></a>Vea también  
 [Consideraciones al crear esquemas](../core/considerations-when-creating-schemas.md)