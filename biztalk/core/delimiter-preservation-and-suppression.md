---
title: Conservar y suprimir delimitadores | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 30985b94-625e-411a-8137-1c129bc197bf
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1195e153eb94215bf8861b4856e4d2135b24443e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="delimiter-preservation-and-suppression"></a>Supresión y conservación de delimitador

## <a name="overview"></a>Información general
Hay dos propiedades que se aplican a los registros delimitados: **conservar delimitador para datos vacíos** y **[Suprimir delimitadores finales**. Utilice estas propiedades para controlar la forma en que el ensamblador de archivo sin formato utiliza delimitadores asociados con datos que no existen y delimitadores finales. Al establecer el **conservar delimitador para datos vacíos** propiedad **Sí** (que es el valor predeterminado), los delimitadores se incluyen en el mensaje de archivo sin formato traducido de:  
  
-   Los campos sin datos  
  
-   Los registros inmediatamente subordinados sin datos que no tienen una etiqueta asociada a ellos  
  
 Al establecer el **conservar delimitador para datos vacíos** propiedad **n**, delimitadores no se incluyen en el archivo sin formato traducido para los registros y campos sin datos. Además, independientemente de la configuración de la **conservar delimitador para datos vacíos** propiedad delimitadores no se incluirá en el mensaje de archivo sin formato traducido de registros inmediatamente subordinados sin datos para el que se define una etiqueta.  
  
 Al establecer el **Suprimir delimitadores finales** propiedad **No** (que es el valor predeterminado), uno o más delimitadores finales pueden incluirse en el mensaje de archivo sin formato traducido. Al establecer el **Suprimir delimitadores finales** propiedad **Sí**, finales delimitadores no se incluyen en el mensaje de archivo sin formato traducido.  

## <a name="special-scenarios"></a>Escenarios especiales  
 Hay algunos casos especiales en los comportamientos ocasionados por la configuración de la **conservar delimitador para datos vacíos** y **Suprimir delimitadores finales** propiedades pueden entrar en conflicto. En tales casos, los comportamientos asociados con la última propiedad, **Suprimir delimitadores finales**, tendrá prioridad. Además, en algunos casos especiales, se le advertirá de que pueden existir conflictos potenciales entre los valores configurados para estas dos propiedades.  
  
 Por ejemplo, considere un **registro** nodo definido con los valores de propiedad siguientes:  
  
-   Nombre de nodo = MyRec  
  
-   Identificador de etiquetas = Rec  
  
-   Delimitador secundario = ,  
  
-   Orden secundario = Infijo  
  
 Y definido para contener cinco **elemento de campo** nodos con los siguientes nombres (también podrían ser **atributo de campo** nodos o subordinado **registro** nodos):  
  
-   FieldElem1  
  
-   FieldElem2  
  
-   FieldElem3  
  
-   FieldElem4  
  
-   FieldElem5  
  
 A continuación, se supone que la siguiente principalmente vacía fragmento XML, que representa este **registro** nodo, se pasa para el ensamblador de archivo sin formato.  
  
```  
<MyRec>  
    <FieldElem1 />  
    <FieldElem2 />  
    <FieldElem3>Val</FieldElem3>  
    <FieldElem4 />  
    <FieldElem5 />  
</MyRec>  
  
```  
  
 En la tabla siguiente muestra el resultado generado y la propiedad adicional asociada establecer requisitos para los nodos de esquema correspondiente, según la configuración para la **conservar delimitador para datos vacíos** (PDFED) y **Suprimir delimitadores finales** propiedades (STD).  
  
|Configuración de PDFED|Configuración de STD|Salida|Requisitos adicionales del nodo|  
|---|---|---|---|  
|Sí|No|Rec,,,Val,,|Ninguno.|  
|No|Sí|Rec,Val|Todos los **elemento de campo** nodos deben estar configurados como opcionales.|  
|Sí|Sí|Rec,,,Val|Nodos denominados **FieldElem4** y **FieldElem5** se deben configurar como opcionales.|  
|No|No|Rec,Val,,|Todos los **elemento de campo** nodos deben estar configurados como opcionales.|  
  
 Si la configuración de estas propiedades especifica que los delimitadores no se deben conservar o suprimir, se generará un mensaje de advertencia para indicar que puede que no sea posible analizar los datos de archivo sin formato serializados mediante el mismo esquema en los dos casos siguientes:  
  
-   Cuando el **registro** nodo para el que el **conservar delimitador para datos vacíos** propiedad está establecida en **No** o **Suprimir delimitadores finales**propiedad está establecida en **Sí**, respectivamente, contiene subordinados **elemento de campo** nodos, **atributo de campo** nodos, o **registro**  nodos para el que no se ha especificado ninguna etiqueta.  
  
-   Cuando el subordinado **elemento de campo** nodos, **atributo de campo** nodos, y **registro** para el que no se ha especificado ninguna etiqueta no están configurados para que sean opcionales (estableciendo la **Min Occurs** propiedad establecida en cero) en el esquema. Cuando el **Suprimir delimitadores finales** propiedad está establecida en **Sí**, solo la última esos nodos subordinados debe configurarse como opcional. Cuando el **conservar delimitador para datos vacíos** propiedad está establecida en **No**, al final de todos los nodos subordinados debe configurarse como opcional.  
  
> [!NOTE]
>  Siempre se conservan los delimitadores cuando el elemento XML asociado a un (presumiblemente opcional) **registro**, **elemento de campo**, o **atributo de campo** nodo son falta por completo en la representación XML del documento empresarial, excepto cuando un registro sigue a un campo opcional ausente. En otras palabras, cuando faltan los datos y las etiquetas XML que los rodean, el delimitador correspondiente siempre se incluye en la representación de archivo sin formato del documento empresarial.  
  
 Ahora, cambie el esquema para incluir un registro secundario con dos Elemento de campo que sigan inmediatamente a un Elemento de campo ausente. Los elementos del registro secundario se configuran para usar la &#124; carácter (barra vertical) como delimitador.  
  
```  
<MyRec>  
    <FieldElem1 />  
    <FieldElem2 />  
    <FieldElem3>Val</FieldElem3>  
    <!-- <FieldElem4 /> -->  
    <ChildRec>  
        <InnerFieldElement1>Inner1</InnerFieldElement1>   
        <InnerFieldElement2>Inner2</InnerFieldElement1>  
    </ChildRec>  
    <FieldElem5 />  
</MyRec>  
  
```  
  
 Si lo anterior se pasa al desensamblador de archivos sin formato, los delimitadores de FieldElem4 no se conservarán, aunque los registros posteriores se delimitarán según lo esperado.  
  
```  
,,Val,,Inner1,Inner2,,  
```  
  
## <a name="see-also"></a>Vea también  
-  [Consideraciones de registro delimitadas](../core/delimited-record-considerations.md)   
-  **Conservar delimitador para datos vacíos (propiedad de nodo de esquemas de archivo sin formato)** y **Suprimir delimitadores (propiedad de nodo de esquemas de archivo sin formato) finales**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]