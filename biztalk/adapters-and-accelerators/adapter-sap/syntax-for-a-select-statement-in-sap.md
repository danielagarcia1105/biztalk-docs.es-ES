---
title: Sintaxis de una instrucción SELECT de SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SELECT statement, syntax for
ms.assetid: 47120d74-bf41-4622-a6bc-7b8ddc959305
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92b3cb47df9b151de741b0e64f21041a60b9c90d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970717"
---
# <a name="syntax-for-a-select-statement-in-sap"></a>Sintaxis de una instrucción SELECT de SAP
Las secciones siguientes describen las especificaciones de gramática para implementar consultas SELECT sobre la [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]. Tenga en cuenta que en algunos casos, la sintaxis es un poco diferente de la sintaxis básica de Transact-SQL.  
  
```  
SELECT {TOP <const> }[0,1] <select_list>  {INTO FILE [‘file_name’ | “file_name”]   
{DELIMITED}[0,1]}[0,1]  FROM table_name  {AS alias_name }[0,1]    
{INNER JOIN table_name {AS alias_name}[0,1] ON  <Join_Condition>}[0,1]  
{ WHERE <predicate> } [0,1] {;}[0,1]   
[OPTION 'no_conversion' | 'batchsize <size>' | 'disabledatavalidation'  
```  
  
 Donde:  
  
- **<select_list>** = `[ {table_name.}[0,1]column_name { AS alias_name } [0,1] } [ 1, …n ]`  
  
- **<Join_Condition>** = `[Alias_name.|table_name.]column_name <expr> [Alias_name.|table_name.]column_name`  
  
- **\<predicado\>** = `[ predicate [AND|OR] predicate [between|not between] predicate |  NOT predicate |  ‘(‘ predicate ‘)’ | condition ]`  
  
  Las condiciones admitidas y las expresiones son:  
  
- **\<condición\>** = `[ expr | expr [NOT | ] BETWEEN const AND const | expr [NOT | ] LIKE const ]`  
  
- **\<expr\>** = `[ const | column_name [= | ! = | > | > = | ! > | < | < = | ! < ] const | column_name | - const  | const | column_name ]`  
  
  Donde  **\<const\>** = `integer | real | string | ? | NULL | xml_element`.  
  
  **Valores de la palabra clave de opción**  
  
  Puede especificar las opciones como `OPTION '<option>'`, donde `<option> = 'no_conversion' | 'batchsize <size>' | 'disabledatavalidation'`  
  
- El **no_conversion** opción:  
  
  -   Si el **no_conversion** opción se utiliza, a continuación, los campos en la tabla se exponen mediante los tipos de .NET equivalente. Para obtener información sobre el equivalente de .NET de los tipos de datos SAP, consulte [básica de los tipos de datos de SAP](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md).  
  
  -   Si el **no_conversion** no se utiliza la opción, y si un campo no tiene una conversión de salida definido, a continuación, esos campos en la tabla se exponen mediante los tipos de .NET equivalente. Para obtener información sobre el equivalente de .NET de los tipos de datos SAP, consulte [básica de los tipos de datos de SAP](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md).  
  
  -   Cuando el **no_conversion** no se utiliza la opción, y si un campo tiene una conversión de salida definido, a continuación, esos campos en la tabla se exponen como cadenas de. NET.  
  
- Cuando se establece en **batchsize \<tamaño\>**, la ejecución de la instrucción SELECT hace que varias llamadas a realizarse en el sistema SAP y en cada llamada, solo \<tamaño\> es el número de registros puede recuperar. Por ejemplo, si especifica ' batchsize 100', la consulta SELECT que recupera 100 registros en cada llamada al sistema SAP. Si **batchsize \<tamaño\>**  no se especifica, se supone que el valor predeterminado de 10 000 el tamaño de lote. Tenga en cuenta que debe especificar un valor óptimo para el tamaño del lote basándose en la memoria física del equipo y el número de filas en el sistema SAP. Error al especificar un valor para tamaño de lote óptimo puede producir excepciones de memoria insuficiente.  
  
- Cuando se establece en **disabledatavalidation**, el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] no valida los valores presentes en las columnas de DAT, TIM y NUMC pero expone en su lugar como cadena.  
  
   Esto es útil en escenarios donde los clientes ADO.NET no recuperar los datos de una tabla SAP con datos no válidos en columnas DAT, TIM y NUMC. Puesto que SAP permite a los datos no válidos en columnas DAT, TIM y NUMC, al intentar leer los datos de clientes ADO.NET no será capaces de analizar los datos no válidos y producen una excepción. Si el **disabledatavalidation** opción está establecida en la consulta SELECT, la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] no analiza los datos no válidos pero extrae como cadenas.  
  
> [!IMPORTANT]
>  Siempre debe proporcionar los valores de la palabra clave de opción entre comillas simples, por ejemplo, '*disabledatavalidation*'.  
  
 Por ejemplo, vea [ejemplos para la instrucción SELECT](../../adapters-and-accelerators/adapter-sap/examples-for-select-statement.md).  
  
## <a name="predicates-syntax"></a>Sintaxis de los predicados  
 El ejemplo siguiente especifica la gramática para el uso de predicados en una instrucción SELECT:  
  
 `Predicate`:  
  
```  
Predicates [AND | OR] Predicates [between|not between] Predicates | [NOT] Predicates | '(' Predicates ')' | Condition  
```  
  
 `Condition`:  
  
```  
Expr | LExpr [NOT] BETWEEN RExpr AND RExpr | LExpr [NOT] LIKE Const  
```  
  
 `Expr`:  
  
```  
LExpr [=|!=|>|>=|!>|<|<=|!<] RExpr>  
```  
  
 `LExpr`:  
  
```  
ColumnName  
```  
  
 `RExpr`:  
  
```  
Const | PlaceHolder  
```  
  
 `ColumnName`:  
  
```  
Column | TableName.Column | '['Column']'  
```  
  
 `Tablename`:  
  
```  
Table | '['Table']'  
```  
  
## <a name="considerations-when-calling-a-select-statement"></a>Consideraciones al llamar a una instrucción SELECT  
 Esta sección enumeran los puntos que debe tener en cuenta al usar la instrucción SELECT con [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].  
  
- Al especificar valores de fecha y hora en parámetros o consultas, proporcione los valores como una cadena. Proporcionar las cadenas de fecha y hora en el formato de fecha y hora SAP.  
  
  - `SAP date format`: AAAAMMDD  
  
     Por ejemplo, la fecha de 2004 del 10 de noviembre en una consulta SAP es expresado '20041110'.  
  
     La fecha de 2004 del 10 de noviembre en un p1 SAPParameter es la cadena de p1. Valor = '20041110'.  
  
  - `SAP time format`: HHMMSS  
  
     Por ejemplo, la hora 10:34:32 en una consulta SAP es expresado '103432'.  
  
     La hora 10:34:32 en SAPParameter p2 es la cadena de p2. Valor = '103432'.  
  
    Para una instrucción SELECT, la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] devuelve `DATE` valores de campo como .NET `System.DateTime` objetos y devuelve `TIME` campo valores como `System.TimeSpan` objetos. Si el valor de SAP `DATE` objeto es menor que el valor mínimo permitido de SQL Server (`1/1/1753`), el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] devuelve este valor mínimo, `1/1/1753`.  
  
- En la cláusula TOP de una consulta SELECT, al utilizar los caracteres especiales "#", "^", "&" y "%" antes o después de un entero, se omiten los caracteres especiales, aunque no se genera ningún mensaje de error. Por ejemplo, se omiten las siguientes en la cláusula TOP de una consulta SELECT:  
  
   \#5, 5 ^, %5%, o & 5  
  
   Sin embargo, con estos caracteres entre los números enteros, como en 5 5$, se produce un error.  
  
- Nombres de columna devueltos en un esquema para una tabla se devuelven como todos los caracteres en mayúsculas. Por ejemplo, Establece el resultado de una consulta en el campo `Last Name` devuelve el encabezado de columna `LAST NAME`. Para evitar la unicidad, conviene conflictos, con todas las letras mayúsculas en instrucciones SELECT.  
  
- En la cláusula LIKE de una consulta SELECT, solo el signo de porcentaje "%" (para cualquier cadena de cero o más caracteres) y carácter de subrayado, **"_"** (para cualquier carácter individual) son caracteres especiales permitidos. Todos los demás caracteres especiales se consideran valores de cadena y se omiten.  
  
- El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] la RFC Z_EXTRACT_DATA_OO se usa para realizar consultas SELECT en el sistema SAP. La RFC admite la lectura de datos de tablas que cumplen las condiciones siguientes:  
  
  - TabClass para la tabla es TRANSP, clúster o grupo.  
  
  - TabClass es la vista y ViewClass es D o P.  
  
    Asegúrese de que la instrucción SELECT lee los datos de las tablas que se cumplen estas condiciones.  
  
- Los valores de tipos de datos que pueden tardar más de 255 caracteres, por ejemplo cadenas, RAWSTRING, LRAW, VARC y LCHAR no se puede usar en una consulta SELECT. El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] usa una RFC personalizada que se incluye con el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], Z_EXTRACT_DATA_OO, para realizar consultas SELECT en el sistema SAP. Este RFC personalizada no es compatible con cualquier tipo de datos que puede tener más de 255 caracteres.  
  
- El número máximo de columnas o campos que se admiten en una instrucción SELECT es 1000.  
  
- El número máximo de predicados que se admiten en una cláusula WHERE es 100.  
  
- No se admite la selección de varias veces el mismo campo en la misma instrucción SELECT. La RFC (Z_EXTRACT_DATA_OO) personalizado utilizado por el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] quita los campos duplicados de la instrucción antes de ejecutar. Por ejemplo, esta instrucción:  
  
   `SELECT BUKRS, BUKRS, BUKRS from T001`  
  
   se ejecuta como si se escribe como esta instrucción:  
  
   `SELECT BUKRS from T001`  
  
- [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] no admite nombres de alias duplicados en una instrucción SELECT. Por lo tanto, la siguiente instrucción SELECT produce un error:  
  
  ```  
  SELECT KUNNR AS [MYKNA1], JMJAH AS MYKNA1 from KNA1 where KUNNR LIKE 'T-S62A08' AND JMJAH=1995  
  ```  
  
- [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] no se admite una instrucción SELECT con nombres de columna duplicados. Por lo tanto, la siguiente instrucción SELECT produce un error:  
  
  ```  
  SELECT KUNNR AS [MYKNA1], KUNNR AS MYKNA2 from KNA1 where MYKNA2='T-S62A08'  
  ```  
  
- SAP no almacena los valores NULL en las tablas. Como resultado, el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] no es compatible con un valor "IS NULL" en una instrucción SELECT. Por lo tanto, la siguiente instrucción SELECT produce un error:  
  
  ```  
  SELECT NAME1, PSTLZ  from KNA1 where CITY IS NULL AND NAME1 LIKE '%MODE%'  
  ```  
  
- [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] no admite una cláusula ORDER BY en una instrucción SELECT. Por lo tanto, la siguiente instrucción SELECT produce un error:  
  
  ```  
  SELECT NAME1  AS [MYNAME],  LAND1, KUNNR  from KNA1 where NAME1 LIKE '%MODE%'  ORDER BY NAME1  ASC  
  ```  
  
- [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] no se admite la especificación de un asterisco (*) para seleccionar todos los campos de una tabla SAP. Por lo tanto, la siguiente instrucción SELECT produce un error:  
  
  ```  
  SELECT spfli.* from spfli inner join sflight on spfli.carrid = sflight.carrid  
  ```  
  
   Para seleccionar todos los campos, debe especificar los nombres de campo de forma individual.  
  
- Como parte de la instrucción SELECT, puede especificar un archivo al que se escribirá la salida de la instrucción SELECT. Sin embargo, si el archivo de salida está en un recurso compartido de red, asegúrese de que la cuenta de servicio SAP en la que se está ejecutando el servicio SAP tiene permiso de escritura al recurso compartido de red. Por ejemplo:  
  
  ```  
  SELECT * into file '\\share\output.txt' from spfli inner join sflight on spfli.carrid = sflight.carrid  
  ```  
  
   En el ejemplo anterior, la cuenta de servicio SAP debe tener permiso de escritura al recurso compartido de red con el nombre "recurso compartido."  
  
- Una instrucción SELECT que usa [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] es compatible con los nombres de parámetro para los valores de argumento en una consulta SELECT. Sin embargo, asegúrese de que seguir estas reglas con respecto a los nombres de parámetro:  
  
  -   En la consulta SELECT, una "\@" símbolo debe preceder el nombre del parámetro.  
  
  -   El "\@" símbolo debe ir seguido por un carácter alfabético (A-z o a-z).  
  
  -   El nombre del parámetro puede contener caracteres alfanuméricos (A-z, a-z o 0-9) y caracteres especiales. Los únicos caracteres especiales que pueden incluirse en el nombre del parámetro son un carácter de subrayado "_" y "#" hash.  
  
- Al ejecutar una consulta SELECT en una vista, asegúrese de que todas las columnas de clave principales de la tabla base también están presentes en la vista. Además, como práctica, debe marcar las columnas como columnas de clave principal en la vista también.  
  
   Si no están presentes en la vista de las columnas de clave principales, una consulta SELECT en la vista se producirá una excepción.  
  
- Al ejecutar una consulta SELECT en una tabla para seleccionar los campos de tipo LRAW, asegúrese de que seleccionar el campo PREC correspondiente. Además, el campo PREC debe aparecer inmediatamente antes del campo LRAW en la cláusula SELECT.  
  
   Cada campo LRAW en una tabla tiene un campo PREC correspondiente que almacena la longitud de datos en el campo LRAW. Especificar simplemente el campo LRAW en la cláusula SELECT sin el campo PREC puede dar lugar a que se va a extraer los datos incorrectos.  
  
- En un sistema SAP, las comparaciones de caracteres distinguen mayúsculas de minúsculas. Por lo tanto, las siguientes dos consultas pueden devolver resultados diferentes.  
  
  ```  
  SELECT * FROM KNA1 WHERE LAND1 LIKE 'D%'  
  ```  
  
   And  
  
  ```  
  SELECT * FROM KNA1 WHERE LAND1 LIKE 'd%'  
  ```  
  
   Asegúrese de que utilizar el derecho de los casos cuando una consulta select de tramas. Además, en un sistema SAP, no todas las columnas pueden contener caracteres en mayúsculas o minúsculas. Puede usar la GUI de SAP para averiguar si una columna de una tabla almacena los caracteres en mayúsculas o minúsculas. Para obtener instrucciones sobre el uso de la GUI de SAP, consulte [determinar si una columna almacenes en minúsculas o mayúsculas valores](../../adapters-and-accelerators/adapter-sap/determining-whether-a-column-stores-lowercase-or-uppercase-values.md).  
  
- La condición WHERE solo se admite para la comparación de un valor de campo con algún valor de datos, y *no* con algún otro valor de campo de tabla. Dado que el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] consulta SELECT admite una única tabla, las consultas de campo de tabla en condiciones de combinación debe usar la condición de combinación para admitir el mismo.  
  
- Una condición de combinación debe contener un nombre de tabla.  
  
   La siguiente es una instrucción SELECT correcta  
  
  ```  
  select A.x, B.y from A inner join B on A.m = B.n  
  ```  
  
   La siguiente es una instrucción SELECT incorrecta  
  
  ```  
  select A.x, B.y from A inner join B on m = n  
  ```  
  
- En una condición de combinación, la tabla izquierda en una condición de combinación debe estar en el lado izquierdo de la condición y la tabla derecha de la condición de combinación debe especificarse en el lado derecho de la condición de combinación.  
  
   La siguiente es la forma correcta de especificar una condición de combinación:  
  
  ```  
  select A.x, B.y from A inner join B on A.m = B.n  
  ```  
  
   La siguiente es una manera de especificar una condición de combinación incorrecta:  
  
  ```  
  select A.x, B.y from A inner join B on B.n = A.m  
  ```  
  
- Una instrucción SELECT solo puede contener una condición de "igual a" en una cláusula JOIN. Por ejemplo:  
  
  ```  
  select * from spfli inner join sflight on spfli.carrid = sflight.carrid  
  ```  
  
- Una instrucción SELECT no recupera las columnas de tipo cadena desde el sistema SAP.  
  
- Una instrucción SELECT puede contener solo una combinación única. Por ejemplo:  
  
  ```  
  select * from spfli inner join sflight on spfli.carrid = sflight.carrid  
  ```  
  
## <a name="see-also"></a>Vea también  
 [Acerca del proveedor de datos de .NET Framework para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)
