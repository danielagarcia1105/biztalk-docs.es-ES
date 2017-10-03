---
title: "Expresiones de configuración de interceptor | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2695f509-fece-40b8-aa00-fa3c0c0f19c5
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a28af058ac4750426f66dc6e290bc6a02bf2efd6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="interceptor-configuration-expressions"></a>Expresiones de configuración de interceptor
El archivo de configuración de interceptor de BAM usa expresiones de filtro para identificar una actividad y usa expresiones de datos para construir un elemento de datos para el almacenamiento, usar un Id. de correlación o un token de continuación, o propósitos similares. Independientemente del propósito, las expresiones individuales se identifican en el archivo de configuración de interceptor por el elemento `expression` y contienen una o varias operaciones que usan la Notación polaca inversa, que se conoce también como notación de polaco inverso.  
  
## <a name="about-reverse-polish-notation"></a>Acerca de la Notación polaca inversa  
 En la Notación polaca inversa (RPN), los operandos preceden al operador, con lo que se elimina la necesidad de usar paréntesis como operadores de precedencia. Una pila se usa para contener valores y todas las operaciones, tanto valores de insertar en la pila como de retirar (quitar) de la pila, o para realizar una combinación de insertar y retirar para completar una operación.  
  
 Por ejemplo, si deseara evaluar la expresión  
  
 `5 + (10 - 2)`  
  
 Convertir esto a los resultados RPN equivalentes en  
  
 `5 10 2 - +`  
  
 Esto se evaluaría de la siguiente forma:  
  
|Entrada|Operación|Pila|  
|-----------|---------------|-----------|  
|5|Inserción|5|  
|10|Inserción|5, 10|  
|2|Inserción|5, 10, 2|  
|-|Subtract|5, 8|  
|+|Agregar|13|  
  
 Suponiendo que el sistema RPN admitiera la operación de concatenación de cadenas, podría también evaluar la expresión  
  
 `"The quick brown " + "fox " + "jumped over the lazy " + "dog."`  
  
 Convertir esto al rendimiento de notación de RPN equivalente:  
  
 `"The quick brown " "fox " "jumped over the lazy " "dog" + + +`  
  
 Esto se evaluaría de la siguiente forma:  
  
|Entrada|Operación|Pila|  
|-----------|---------------|-----------|  
|"A caballo"|Inserción|"The quick brown "|  
|"fox"|Inserción|"The quick brown ", "fox "|  
|"jumped over the lazy"|Inserción|"The quick brown ", "fox ", "jumped over the lazy "|  
|"dog."|Inserción|"The quick brown ", "fox ", "jumped over the lazy ", "dog."|  
|+|Concatenate|"The quick brown ", "fox ", "jumped over the lazy dog."|  
|+|Concatenate|"The quick brown ", "fox jumped over the lazy dog."|  
|+|Concatenate|"The quick brown fox jumped over the lazy dog."|  
  
 Como puede ver, se admite un número arbitrario de operaciones, incluidas la comparación, las operaciones booleanas y las operaciones personalizadas que recuperan valores apropiados para las operaciones en las que participan. Los valores se acumulan en la pila y se insertan y quitan en función de las operaciones individuales.  
  
## <a name="reverse-polish-notation-in-the-interceptor-configuration-file"></a>Notación polaca inversa en el archivo de configuración de interceptor  
 Escribirá dos tipos de expresiones en el interceptor de archivo de configuración: filtrar expresiones y expresiones de datos. Las expresiones de filtro esperan que el resultado de la expresión de RPN sea un valor booleano `true` o `false`, mientras que las expresiones de datos esperan un único valor en la pila.  
  
### <a name="filter-expressions"></a>Expresiones de filtro  
 Las expresiones de filtro se evalúan como valor booleano `true` o `false`, y se usan para identificar un evento concreto, del cual se realiza un seguimiento en la aplicación WF o WFC. En aplicaciones WF, es común filtrar en función del nombre de la actividad y del evento. Por ejemplo, puede que desee seleccionar el **FoodAndDrinksPolicy** actividad cuando resulta **cerrado**. Mediante el uso de operaciones de WF, puede expresar el filtro como:  
  
 `(GetActivityName = "FoodAndDrinksPolicy") && (GetActivityEvent = "Closed")`  
  
 Convertir en rendimiento de RPN:  
  
 `GetActivityName "FoodAndDrinksPolicy" == GetActivityEvent "Closed" == &&`  
  
 La conversión de esta expresión a la expresión equivalente para el archivo de configuración de interceptor da como resultado el siguiente XML:  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>FoodAndDrinksPolicy</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <wf:Operation Name="GetActivityEvent"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <ic:Operation Name="And"/>  
  </ic:Expression>  
</ic:Filter>  
```  
  
 Por último, esta expresión se evaluará como sigue suponiendo que **GetActivityName** devuelto "DessertPolicy" y **GetActivityEvent** devuelto "Closed":  
  
|Entrada|Operación|Pila|  
|-----------|---------------|-----------|  
||GetActivityName|"DessertPolicy"|  
|"FoodAndDrinksPolicy"|Constante|"DessertPolicy", "FoodAndDrinksPolicy"|  
|Es igual a|Comparación|False|  
||GetActivityEvent (operación)|False, Closed|  
|"Closed"|Constante|False, "Closed", "Closed"|  
|Es igual a|Comparación|False, True|  
|And|Logical And|False|  
  
 El valor que se ha dejado en la pila es booleano `False`. Esto provocará que el evento correspondiente no se active. Si el nombre de actividad fuera "FoodAndDrinksPolicy", se habría evaluado como un valor booleano `True`.  
  
 Puede construir una expresión similar (con una evaluación similar). Para ello, utilice operaciones de WCF `GetEndpointName` y `GetOperationName`.  
  
### <a name="data-expressions"></a>Expresiones de datos  
 Las expresiones de datos se usan para definir un único valor de datos de cadena. Una expresión de datos se considera cualquier expresión que no se incluye en un elemento de `Filter`. Las expresiones de datos las usan los elementos de `OnEvent` `CorrelationID`, `ContinuationToken`, `Reference` y `Update`.  
  
 Un requisito habitual suele ser actualizar la base de datos de actividad de BAM con una marca de tiempo sin etiqueta. Por ejemplo, desea capturar el tiempo que se inicia un evento con una formato de cadena como "iniciar: \<EventTime >". Para hacerlo, debe usar una expresión similar a la siguiente (donde + representa la concatenación):  
  
 `"Start: " + GetContextProperty(EventTime)`  
  
 Convertir en rendimiento de RPN:  
  
 `"Start: " GetContextProperty(EventTime) +`  
  
 La conversión de esta expresión a la expresión equivalente para un elemento `Update` en el archivo de configuración de interceptor da como resultado el siguiente XML:  
  
```  
<ic:Update DataItemName="NewOrderCreateTime" Type="NVARCHAR">  
  <ic:Expression>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Start:</ic:Argument>  
    </ic:Operation>  
    <wf:Operation Name="GetContextProperty">  
      <wf:Argument>EventTime</wf:Argument>  
    </wf:Operation>  
    <ic:Operation Name="Concatenate" />  
  </ic:Expression>  
</ic:Update>  
```  
  
 La siguiente tabla muestra cómo debe interpretarse esta expresión si la hora del evento fuera "12:00 PM".  
  
|Entrada|Operación|Pila|  
|-----------|---------------|-----------|  
|"Inicio:"|Constante|"Inicio:"|  
|GetContextProperty(EventTime)|Inserción|"Inicio:", "2006-09-27T12:00:34.000Z"|  
|Concatenate|Concatenate|"Inicio: 2006-09-27T12:00:34.000Z"|  
  
 El valor utilizado por el comando de actualización sería "iniciar: 2006-09-27T12:00:34.000Z".  
  
> [!NOTE]
>  No use las operaciones de comparación "And" o "Equals" en expresiones de datos. De hacerlo, recibirá un error cuando implemente el archivo de configuración de interceptor.  
  
## <a name="in-this-section"></a>En esta sección  
 [Operaciones de interceptor](../core/interceptor-operations.md)  
  
## <a name="see-also"></a>Vea también  
 [Estructura de un archivo de configuración de Interceptor](../core/structure-of-an-interceptor-configuration-file.md)