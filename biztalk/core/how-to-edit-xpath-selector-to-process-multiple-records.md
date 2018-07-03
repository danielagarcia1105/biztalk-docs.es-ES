---
title: Cómo editar el Selector XPath para procesar varios registros | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, editing multiple records
- Business Rules Framework, code samples
- Business Rules Framework, programming
ms.assetid: ef7e1f8d-2e29-4cef-b558-0090648bffc0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e69748feaeb877c816cc086ba978e53e8398baf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018356"
---
# <a name="how-to-edit-xpath-selector-to-process-multiple-records"></a>Cómo editar el selector XPath para procesar varios registros
Secundarios independientes TypedXmlDocuments se crean cuando se impone un TypedXmlDocument en el motor; consulte [Assert](../core/assert.md). El motor determina los TypedXmlDocuments secundarios que se van a crear según los selectores XPath que estén definidos en las reglas. Cuando genera reglas en el Compositor, el valor predeterminado del selector XPath es el nodo que hay por encima del nodo seleccionado en la pestaña Esquemas XML en el Explorador de hechos. El valor predeterminado es el valor XPath Field al nodo seleccionado, en relación con su nodo primario.  
  
 En algunas situaciones tal vez desee personalizar el XPath predeterminado que el Compositor crea cuando genera reglas. Observe el siguiente documento XML de ejemplo.  
  
```  
<Order>  
   <Orderline>  
      <Hat style="Baseball">                        
         <Cost>10</Cost>  
      </Hat>  
      <Shirt color="Black">  
         <Cost>20</Cost>  
      </Shirt>  
      <Total></Total>  
   </Orderline>  
   <Orderline>  
      <Hat style="Bowler">                        
         <Cost>20</Cost>  
      </Hat>  
      <Shirt color="Red">  
         <Cost>20</Cost>  
      </Shirt>  
      <Total></Total>  
   </Orderline>  
</Order>  
```  
  
 Suponga que desea generar una regla que calcule el valor Total para cada Orderline. Su regla tendría el siguiente aspecto.  
  
 IF 1==1  
  
 A continuación, <strong>/Order/Orderline/</strong>Total = (<strong>/Order/Orderline/Hat/</strong>costo + <strong>/Order/Orderline/camisa/</strong>costo)  
  
 La parte en negrita de los XPath indica la parte del Selector y el resto representa el XPath de campo. Estos son los valores predeterminados que genera el Compositor. Si ejecuta esta directiva, sin embargo, daría como resultado la creación de 6 objetos: 2 objetos de Orderline, 2 objetos Hat y 2 objetos camisa. Los totales de Orderline se calcularán para cada combinación de objetos Hat y Shirt, y los totales siempre se establecerán con el mismo valor, que se obtuvo de la última ejecución de la regla. La regla se activará 8 veces. Esto no es lo que se pretende en este escenario.  
  
 Una solución sería editar los valores de XPath de la siguiente manera.  
  
 IF 1==1  
  
 A continuación, <strong>/Order/Orderline/</strong>Total = (<strong>/Order/Orderline/</strong>Hat y costo + <strong>/Order/Orderline/</strong>camisa/costo)  
  
 Los valores del selector XPath para los tres campos se han establecido con el mismo valor /Order/Orderline y los valores de XPath de campo se han editado en consecuencia. Esto se realiza cambiando los valores de campo de selector XPath y XPath en la ventana Propiedades cuando se selecciona un nodo en la pestaña Esquemas XML. Este cambio debe hacerse antes de arrastrar el campo al argumento de la regla.  
  
 Si ejecuta la directiva con este cambio, el valor de Total se calcularía correctamente para cada Orderline según los valores de Cost de los nodos Shirt y Hat dentro de esa Orderline.