---
title: Sintaxis de una instrucción SELECT en Siebel | Microsoft Docs
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
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 543445fe6958a156894bb6c0d268d9b3b5814b23
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022666"
---
# <a name="syntax-for-a-select-statement-in-siebel"></a>Sintaxis de una instrucción SELECT de Siebel
Mediante el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], los clientes de ADO.NET pueden realizar una consulta SELECT en componentes empresariales de Siebel mediante la especificación de una cláusula WHERE que representa una especificación válida de búsqueda de Siebel. La sintaxis de la instrucción SELECT es:  
  
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
  
 En la sintaxis anterior, la opción de ViewMode corresponde al sistema Siebel modos de vista, que es un mecanismo de filtrado para restringir el conjunto de registros que coinciden con la consulta. Para el conjunto de valores permitido, consulte la documentación de Siebel.  
  
> [!NOTE]
>  Si los nombres de campo en la cláusula WHERE contiene caracteres especiales ni espacios vacíos, asegúrese de que siempre incluya los nombres de campo dentro de corchetes.  
> 
> [!NOTE]
>  En las consultas SELECT que contiene los nombres de alias con caracteres especiales, asegúrese de que incluir los nombres de alias entre corchetes.  
> 
> [!NOTE]
>  El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] alias admite nombres de tablas en la cláusula SELECT, pero no en la cláusula WHERE.  
  
## <a name="searching-and-sorting-data-using-the-data-provider-for-siebel"></a>Búsqueda y ordenación de datos con el proveedor de datos para Siebel  
 El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] es compatible con una condición de filtro en las instrucciones SQL según las especificaciones de búsqueda compatibles con el sistema Siebel.  
  
 Las reglas para la especificación de búsqueda son:  
  
- Operadores de comparación estándar deben usarse para comparar un campo a una constante o un campo a otro campo. Estos incluyen =,! =, >, <>, =, y < =.  
  
  ```  
  Example: [Revenue] > 5000  
  ```  
  
- Las constantes de cadena deben incluirse entre comillas dobles y los valores de cadena deben distinguir mayúsculas de minúsculas.  
  
  ```  
  Example: [Type] != "COST LIST"  
  ```  
  
- Los operadores lógicos AND, OR y no debe utilizarse para invalidar o combinar expresiones. Mayúsculas y minúsculas se omiten en estos operadores; Por ejemplo, "y" es igual que "AND".  
  
  ```  
  Example: [Competitor] IS NOT NULL and [Competitor] != "N"  
  ```  
  
- Un nombre de campo en una especificación de búsqueda debe estar entre corchetes.  
  
  ```  
  Example: [Conflict Id] = 0  
  ```  
  
- El operador LIKE puede usarse para crear expresiones de comparación en la que se compara un campo con una constante de cadena de texto o un campo a una coincidencia en los primeros caracteres varios y de otro campo es obligatorio. Los caracteres comodín "*"y"?" debe usarse para indicar cualquier número de caracteres y un único carácter, respectivamente.  
  
- Los clientes ADO.NET pueden especificar objetos de negocios de Siebel originales, los componentes empresariales y los nombres de campo del componente de negocio. Estos nombres deben incluirse entre corchetes si contienen caracteres especiales ni espacios en blanco. Ejemplos de consultas que se admiten son:  
  
  ```  
  SELECT [Name], [Postal Code] FROM Account.Account where [Postal Code] != '11065'  
  SELECT [Name], [Postal Code], Id From Account.Account where [Postal Code] != '60626' Order BY Id ASC, Name DESC  
  SELECT * FROM [Admin Price List].[Price Book Items]  
  ```  
  
  El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] admite ordenar especificaciones en instrucciones SQL según la especificación de ordenación admitida por Siebel. Las reglas para la especificación de clasificación son:  
  
- Use comas para separar los nombres de campo en una especificación de clasificación; Por ejemplo, nombre, ubicación  
  
- Para indicar que un campo en la lista se ordena en orden descendente, incluya (DESC) después del nombre de campo, como en "Fecha de inicio (DESC)." Si no se especifica ningún criterio de ordenación, se utiliza el orden ascendente. Para especificar explícitamente el orden ascendente, use la palabra clave (ASC).  
  
- La expresión de la especificación de ordenación debe tener 255 caracteres o menos.  
  
## <a name="see-also"></a>Vea también  
 [Usar el proveedor de datos de .NET Framework para aplicaciones de negocio electrónico de Siebel](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)