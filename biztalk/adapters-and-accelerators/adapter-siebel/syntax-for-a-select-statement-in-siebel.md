---
title: Sintaxis de una instrucción SELECT en Siebel | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for Siebel, searching and sorting data using
- Data Provider for Siebel, SELECT statement
- SELECT statement, syntax for
ms.assetid: 8528b115-d6f3-420d-8617-0e56dc8922bf
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3eeb0a6d4a1fceebe7e16b3f71566f848e4a20f
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="syntax-for-a-select-statement-in-siebel"></a>Sintaxis de una instrucción SELECT de Siebel
Mediante la [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], los clientes ADO.NET pueden realizar una consulta SELECT en componentes empresariales de Siebel mediante la especificación de una cláusula WHERE que representa una especificación de búsqueda de Siebel válida. La sintaxis de la instrucción SELECT es:  
  
```  
SELECT  
<column name 1> AS <column alias 1>,  
<column name 2> AS <column alias 2>,  
…  
FROM  
<Business object name>.<Business component name> AS <table alias>  
WHERE  
<filter condition>  
OPTION  
'ViewMode <value>'  
```  
  
 En la sintaxis anterior, la opción ViewMode corresponde al sistema Siebel modos de vista, que es un mecanismo de filtrado para restringir el conjunto de registros que coinciden con la consulta. Para el conjunto de valores permitido, consulte la documentación de Siebel.  
  
> [!NOTE]
>  Si los nombres de campo en la cláusula WHERE contienen caracteres especiales ni espacios en blanco, asegúrese de que siempre incluye los nombres de campo entre corchetes.  
  
> [!NOTE]
>  En las consultas SELECT que contiene los nombres de alias con caracteres especiales, asegúrese de que incluir los nombres de alias entre corchetes.  
  
> [!NOTE]
>  El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] alias admite nombres para las tablas en la cláusula SELECT, pero no en la cláusula WHERE.  
  
## <a name="searching-and-sorting-data-using-the-data-provider-for-siebel"></a>Buscar y ordenar los datos mediante el proveedor de datos para Siebel  
 El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] es compatible con una condición de filtro en las instrucciones de SQL basadas en las especificaciones de búsqueda admitidas por el sistema Siebel.  
  
 Las reglas para la especificación de búsqueda son:  
  
-   Operadores de comparación estándar deben utilizarse para comparar un campo con una constante o un campo a otro campo. Puede tratarse de =,! =, >, <>, =, y < =.  
  
    ```  
    Example: [Revenue] > 5000  
    ```  
  
-   Constantes de cadena deben ir entre comillas dobles y los valores de cadena deben distinguir mayúsculas de minúsculas.  
  
    ```  
    Example: [Type] != "COST LIST"  
    ```  
  
-   Los operadores lógicos AND, OR y no debe utilizarse para negar o combinar expresiones. Se omite la distinción entre mayúsculas y en estos operadores; Por ejemplo, "y" es igual a "AND".  
  
    ```  
    Example: [Competitor] IS NOT NULL and [Competitor] != "N"  
    ```  
  
-   Un nombre de campo en una especificación de búsqueda debe incluirse entre corchetes.  
  
    ```  
    Example: [Conflict Id] = 0  
    ```  
  
-   El operador LIKE se puede utilizar para crear expresiones de comparación en el que un campo se compara con una constante de cadena de texto o un campo a otro campo y una búsqueda de coincidencias en los primeros caracteres varias es obligatorio. Los caracteres comodín "*"y"?" debe utilizarse para indicar cualquier número de caracteres y un carácter único, respectivamente.  
  
-   Los clientes ADO.NET pueden especificar objetos de negocios de Siebel originales, los componentes empresariales y nombres de campo del componente de negocio. Estos nombres deben incluirse entre corchetes si contienen espacios en blanco ni caracteres especiales. Ejemplos de consultas que se admiten son:  
  
    ```  
    SELECT [Name], [Postal Code] FROM Account.Account where [Postal Code] != '11065'  
    SELECT [Name], [Postal Code], Id From Account.Account where [Postal Code] != '60626' Order BY Id ASC, Name DESC  
    SELECT * FROM [Admin Price List].[Price Book Items]  
    ```  
  
 El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] admite ordenar especificaciones en instrucciones SQL basándose en la especificación de ordenación compatible con Siebel. Las reglas para la especificación de clasificación son:  
  
-   Use comas para separar los nombres de campo en una especificación de ordenación; Por ejemplo, nombre, la ubicación  
  
-   Para indicar que un campo en la lista se ordena en orden descendente, incluir (DESC) después del nombre de campo, como en "Fecha de inicio (DESC)." Si no se especifica ningún criterio de ordenación, se utiliza el orden ascendente. Para especificar explícitamente el orden ascendente, utilice la palabra clave (ASC).  
  
-   La expresión de la especificación de ordenación debe ser 255 caracteres o menos.  
  
## <a name="see-also"></a>Vea también  
 [Usar el proveedor de datos de .NET Framework para aplicaciones de negocio electrónico de Siebel](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)