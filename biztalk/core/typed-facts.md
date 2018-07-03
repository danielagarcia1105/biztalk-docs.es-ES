---
title: Con el tipo de hechos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RuleEngine library
- Business Rule Composer, typed facts
- ITypedFact interface
- DataConnection class
- facts, typed
- TypedDataTable class
- TypedDataRow class
- TypedXmlDocument class
ms.assetid: 8207bfd5-ebd2-45ac-8992-795acdf3ba4c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56fd7d05f6970d8086b9180b0af867c0dcf84119
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000141"
---
# <a name="typed-facts"></a>Hechos con tipo
*Con el tipo de hechos* son clases que implementan la **ITypedFact** interfaz: **TypedXmlDocument**, **DataConnection**, **TypedDataTable** , y **TypedDataRow**.  

## <a name="typedxmldocument"></a>TypedXmlDocument  
 El **TypedXmlDocument** clase representa el tipo de documento XML en el marco de trabajo de reglas de negocios. Cuando se usa un nodo de un documento XML como un argumento en una regla, se crean dos expresiones de XPath: los enlaces de Selector y campo.  

 Si el nodo no tiene ningún nodo secundario, un *enlace de Selector* (también conocido como un enlace XmlDocument) se crea para el nodo primario del nodo y un *enlace de campo* (también denominado enlace XmlDocumentMember) se crea en el nodo en Sí. Este enlace de campo depende del enlace de selector. Si el nodo tiene nodos secundarios, se crea un enlace de selector en el nodo y no se crea ningún enlace de campo.  

 Supongamos que tiene el siguiente esquema.  

 ![Esquema de ejemplo mostrado en el Explorador de hechos](../core/media/xmldocumentbrowser.gif "xmldocumentbrowser")  
Case.xsd  

 Si se selecciona el nodo Income, únicamente se crea un enlace de selector porque el nodo tiene nodos secundarios. La expresión XPath de forma predeterminada en el **Selector XPath** contiene la propiedad del panel de propiedades:  

```  
/*[local-name()='Root' and namespace-uri()='http://LoansProcessor.Case']/*[local-name()='Income' and namespace-uri()='']  
```  

 Sin embargo, si se selecciona el nodo Name, se crean tanto un enlace de selector como un enlace de campo. La información de enlace es similar a la siguiente.  


|      Property      |                                    Valor                                    |
|--------------------|-----------------------------------------------------------------------------|
|  **Campo XPath**   |               \*[local-name () = 'Name' y espacio ='']                |
| **Selector XPath** | /\*[local-name () = 'Root' y espacio ='<http://LoansProcessor.Case>'] |

 Las expresiones XPath predeterminadas para los nodos XML se pueden cambiar antes de arrastrar el nodo a un argumento de regla y colocar la información de enlace nueva en la directiva. No obstante, tenga en cuenta que cualquier cambio realizado a las expresiones XPath debe volver a especificarse en el Compositor de reglas de negocio al volver a cargar el esquema.  

 Cuando se crean definiciones de vocabulario para los nodos XML, las expresiones XPath para los enlaces tienen valores predeterminados similares basados en las reglas descritas anteriormente, aunque se pueden modificar en el Asistente para definición de vocabulario. Los cambios realizados a las expresiones se ubican en la definición de vocabulario y se ven reflejados en cualquier argumento de regla creado a partir de las definiciones.  

## <a name="dataconnection"></a>DataConnection  
 **DataConnection** se proporciona una clase .NET en el **RuleEngine** biblioteca. Contiene .NET **SqlConnection** instancia y un **DataSet** nombre. El **DataSet** nombre le permite crear un identificador único para el **SqlConnection** y se utiliza en la definición del tipo resultante.  

 El **DataConnection** clase proporciona una optimización del rendimiento al motor de reglas de negocios. En vez de imponer en las tablas del motor de base de datos muy grande (**TypedDataTable** clase) que puede contener muchas filas de la base de datos (**TypedDataRow** clase) que no están relacionados con la directiva, puede imponer un ligera **DataConnection**. Cuando el motor evalúa una directiva, crea una consulta SELECT según los predicados o acciones de regla y las consultas dinámicamente el **DataConnection** en ejecución. Por ejemplo, supongamos la siguiente regla:  

```  
IF NorthWind.Products.UnitPrice >= 0   
THEN <do something>  
```  

 La siguiente consulta SQL la genera la regla:  

```  
Select * From [Product] Where [UnitPrice] >= 0  
```  

 Los resultados de la consulta se imponen en el motor en forma de filas de datos.  

> [!NOTE]
>  El uso de un **OleDbConnection** en un **DataConnection** no se admite actualmente.  

 Cuando se selecciona una tabla o columna de base de datos para usar en una acción o condición de regla, puede elegir enlazar al objeto mediante **DataConnection** o **TypedDataTable** seleccionando "Conexión de datos" o " La base de datos tabla o fila"desde el **tipo de enlace de la base de datos**cuadro desplegable en la ventana de propiedades para el **bases de datos** pestaña del explorador de hechos.  

> [!NOTE]
>  El enlace DataConnection se usa de forma predeterminada.  

## <a name="typeddatatable"></a>TypedDataTable  
 Puede imponer un ADO.NET **DataTable** objeto en el motor, pero se tratará como cualquier otro objeto. NET. En la mayoría de los casos en su lugar desea imponer la clase del motor de reglas **TypedDataTable**.  

 **TypedDataTable** es una clase de contenedor que contiene un ADO.NET **DataTable**. El constructor simplemente toma un **DataTable**. Cada vez que una tabla o columna de tabla se utiliza como un argumento de regla, la expresión se evalúa con respecto a la persona **TypedDataRow** contenedores y no con el **TypedDataTable**.  

## <a name="typeddatarow"></a>TypedDataRow  
 Se trata de un contenedor de hechos con tipo para ADO **DataRow** objeto. Arrastrar una tabla o columna a un argumento de regla en el Compositor de reglas basadas en el valor devuelto da como resultado **TypedDataRow** contenedores.  

## <a name="see-also"></a>Vea también  
 [Hechos](../core/facts.md)