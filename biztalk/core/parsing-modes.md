---
title: Modos de análisis | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], code samples
- pipeline components [custom], parsing
ms.assetid: b1188720-e5ae-47ae-ab8e-16d7ed08b778
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf8f9b2618b8cafd7813f08217457227a0f21809
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263308"
---
# <a name="parsing-modes"></a>Modos de análisis
El modo de análisis es un atributo en el registro schemaInfo que tiene dos modos: velocidad y complejidad. La propiedad Optimización del analizador se puede configurar dentro del Editor de esquemas de BizTalk.  
  
## <a name="example"></a>Ejemplo  
  
```  
<b:schemaInfo count_positions_by_byte="false" standard="Flat File"   
root_reference="document" parser_optimization="complexity" />.  
```  
  
 En el modo de velocidad, el analizador intenta ajustar datos conforme éstos aparecen en la secuencia. Por ejemplo, dado el esquema siguiente.  
  
```  
<schema>  
   Root ("," prefix)  
      Field1   opt  
      Field2   opt  
      Field3   opt  
      Field4   opt  
      Record ("," infix)  
            Field5  
            Field6  
</schema>  
```  
  
 y el mensaje de entrada.  
  
```  
,1,2,3,4  
```  
  
 con el modo de velocidad se obtiene el siguiente documento XML.  
  
```  
<Root>  
   <Field1>1</Field1>  
   <Field2>2</Field2>  
   <Field3>3</Field3>  
   <Field4>4</Field4>  
</Root>  
```  
  
 Con el modo de complejidad, el mismo esquema produce la siguiente salida.  
  
```  
<Root>  
   <Field1>1</Field1>  
   <Field2>2</Field2>  
      <Record>  
         <Field5>3</Field5>  
         <Field6>4</Field6>  
      </Record>  
</Root>  
```  
  
 En el modo de complejidad, el motor de análisis del archivo sin formato utiliza tanto el análisis en orden descendente como ascendente e intenta ajustar datos con más precisión. En el modo de velocidad, el analizador intenta ajustar datos conforme éstos aparecen en la secuencia.  
  
 Si tiene elementos opcionales con elementos necesarios, por ejemplo.  
  
```  
<schema>  
   Root  
      Record1 (required)  
  
      Record2 (optional)  
  
      Record3 (required)  
  
```  
  
 Debe utilizar el modo de complejidad para analizar correctamente los datos, ya que el analizador representa el esquema internamente de la siguiente forma.  
  
```  
<schema>  
   Root  
      Record1 (required)  
      <sequence> (optional)  
         Record2 (required)  
         Record3 (required)  
```  
  
## <a name="see-also"></a>Vea también  
 [Usar el motor de análisis de archivo sin formato](../core/using-the-flat-file-parsing-engine.md)