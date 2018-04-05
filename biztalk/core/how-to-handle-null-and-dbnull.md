---
title: Cómo controlar valores Null y DBNull | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, NULL
ms.assetid: d235c265-4947-470b-9f2d-9936ae1b88a1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b07ac74828a858b368cac5d401081a58b8602323
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-handle-null-and-dbnull"></a>Cómo controlar valores Null y DBNull
En este tema se describen los comportamientos esperados al trabajar con valores NULL asociados a los diferentes tipos, además de las opciones que permiten comprobar valores nulos o la existencia de un campo o miembro concreto.  
  
## <a name="xml"></a>XML  
 La siguiente información se aplica a XML:  
  
-   Un valor XML nunca será devuelto de un documento como NULL. Se tratará de una cadena vacía o de un error del tipo "no existe". Cuando se trata de una cadena vacía, se puede producir un error durante la conversión de determinados tipos, como por ejemplo, los campos especificados como tipo entero al crear reglas.  
  
-   El Compositor de reglas de negocio no permite establecer un campo como null, o para establecer el tipo de un campo para **objeto**.  
  
-   Mediante el modelo de objetos puede establecer el tipo en **objeto**. En este caso, el valor devuelto es el tipo al que se evalúa la expresión XPath: **float**, **booleano**, o **cadena**, en función de la expresión XPath.  
  
## <a name="net-classes"></a>clases .NET  
 La siguiente información se aplica a las clases .NET:  
  
-   No se puede comparar con null si el tipo de valor devuelto no es un **objeto** tipo.  
  
-   Puede pasar NULL como parámetro en aquellos parámetros que no sean tipos de valores aunque, dependiendo de la implementación del miembro, es posible que se produzca un error en tiempo de ejecución.  
  
-   Puede establecer campos de tipos derivados de **objeto** en null.  
  
## <a name="data-connection"></a>Conexión de datos  
 La siguiente información se aplica a una conexión de datos:  
  
-   Puede comparar cualquier columna de la tabla de base de datos en null, si la tabla admite valores NULL en la columna y el tipo de columna no es **texto**, **ntext**, y **imagen**.  
  
    > [!NOTE]
    >  El Compositor de reglas de negocios le permite usar las columnas de tipo, **texto** y **ntext**, en las condiciones. Sin embargo, al ejecutar la directiva, recibirá un mensaje de error que indica: "No se pueden comparar ni ordenar los tipos de datos text, ntext e image, excepto cuando se utiliza el operador IS NULL o LIKE".  
  
-   Puede establecer cualquier columna de la tabla de la base de datos como NULL si dicha tabla admite valores NULL en la columna.  
  
-   El Compositor de reglas de negocio establece automáticamente el tipo de miembro en el enlace **objeto**, si comparar ni establecer como null para un tipo de valor; cambia al tipo original si restablece o reemplaza el argumento.  
  
-   Para un tipo de cadena, se cambia el tipo a **objeto** si establece en null, pero deja como una cadena si se compara con null.  
  
-   No se puede comparar ni establecer como **DBNull.Value** desde el Compositor de reglas de negocios, ya que no cambiará el tipo de columna **objeto**.  
  
-   El motor convertirá un valor DBNull en NULL para realizar una comparación, y convertirá el valor NULL a un valor DBNull para realizar una operación de inserción en la base de datos.  
  
-   Las pruebas omitirán los valores NULL (así es como funciona SQL Server). Por ejemplo, si tiene la regla "IF db.column > 5 THEN .", solo se prueban las filas que tengan un valor en db.column y se omiten las filas con valores NULL.  
  
## <a name="typeddatatable-and-typeddatarow"></a>TypedDataTable y TypedDataRow  
 La siguiente información se aplica a TypedDataTable y a TypedDataRow:  
  
-   El Compositor de reglas de negocio cambia el tipo de campo a **objeto** en la misma manera que con **DataConnection**s.  
  
-   Las pruebas generarán un error con los valores NULL, a menos que la comparación se realice con valores NULL. Por ejemplo, habrá un error en la regla "IF db.column > 5 THEN", si las filas impuestas tiene un valor null.  
  
     Tenga en cuenta que, dado que las condiciones se evalúan en paralelo, como pruebas "IF db.column! = NULL AND db.column > 5 THEN" seguirán generando errores porque ambas pruebas se evalúan potencialmente en cada fila.  
  
## <a name="checking-for-null-or-existence"></a>Comprobar la existencia de campos o de valores NULL  
 Al crear reglas de negocios, lo natural es comprobar si un campo existe antes de realizar una comparación con su valor. Sin embargo, si el campo es NULL o no existe, la comparación con el valor generará un error. Imagine que tiene la siguiente regla:  
  
 Si no existe Product/Quantity AND Product/Quantity > 1  
  
 Se producirá un error en la regla si no existe Product/Quantity. Una de las formas de evitar este problema consiste en transferir un nodo primario a un método auxiliar que devuelva el valor del elemento en caso de que exista, o bien cualquier otro valor si no existe. Consulte las siguientes reglas.  
  
 **Regla 1**  
  
 IF EXISTS(Product/Quantity) THEN ASSERT(CREATEOBJECT(typeof(Helper), Product/Quantity)  
  
 **Regla 2**  
  
 IF Helper.Value == X THEN...  
  
 Otra posible solución consiste en crear una regla similar a la siguiente:  
  
 IF Product/Quantity Exist Then CheckQuantityAndDoSomething(Product/Quantity)  
  
 En el ejemplo anterior, la función CheckQuantityAndDoSomething comprobará el valor del parámetro y se ejecutará si se cumple la condición.  
  
> [!NOTE]
>  Como alternativa, puede modificar la expresión XPath **campo** propiedad del hecho XML para detectar los errores, pero no es el enfoque recomendado.