---
title: Functoid de copia masiva | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- anyAttribute node
- Mass Copy functoids, about Mass Copy functoids
- any node
- Mass Copy functoids
ms.assetid: 228ff569-2e21-4e81-b564-6936241cdf6b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fe0a9bc65369327a17591fb6adecb6bd6105333
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="mass-copy-functoid"></a>Copia masiva (functoid)
El **copia masiva** functoid permite que las asignaciones usen esquemas que incluyen **cualquier** y **anyAttribute** elementos. Estos elementos son, fundamentalmente, caracteres comodín proporcionados en el lenguaje de definición de esquemas XML para coincidir con estructuras o atributos desconocidos.  
  
 Además de controlar datos de estructura desconocida, el **copia masiva** functoid permite simplificar el desarrollo de esquemas: solo las partes de un esquema que se procesarán deben especificarse en detalle.  
  
 El **copia masiva** functoid copia el elemento en el mensaje de instancia de entrada correspondiente al nodo de esquema de origen conectado a la **copia masiva** functoid. El functoid también copia toda la subestructura y vuelve a crearla en el mensaje de instancia de salida en el nodo vinculado del esquema de destino. Por lo tanto, también puede usar el **copia masiva** functoid para copiar los registros de origen y de destino que tenga subestructuras idénticas.  
  
 La siguiente ilustración muestra la **copia masiva** usado en una asignación de functoid.  
  
 ![Mapa que ilustra el uso del functoid de copia masiva](../core/media/masscopyfunctoid.gif "masscopyfunctoid")  
Asignación de functoid de copia masiva  
  
 Imagine el siguiente mensaje de instancia de entrada.  
  
```  
<ns0:Root xmlns:ns0="http://MassCopy.ComplexDocument">  
    <PurchaseOrder>  
        <From>Kevin F. Browne</From>  
        <To>Northwind Traders</To>  
        <LineItems>  
            <Item>  
                <Product>Laptop Computer</Product>  
                <Description>Thin profile laptop</Description>  
                <Price>1999.95</Price>  
                <Quantity>1</Quantity>  
            </Item>  
        </LineItems>  
    </PurchaseOrder>  
</ns0:Root>  
```  
  
 Si la asignación anterior se utilizara para procesar este mensaje, el mensaje de instancia de salida sería idéntico al mensaje de instancia de entrada.  
  
## <a name="see-also"></a>Vea también  
 [Cómo agregar Functoids de copia masiva a un mapa](../core/how-to-add-mass-copy-functoids-to-a-map.md)   
 [Functoids avanzados](../core/advanced-functoids.md)   
 [Functoids básicos](../core/basic-functoids.md)   
 [Vínculos a y desde el elemento Any y anyAttribute nodos](../core/links-to-and-from-the-any-element-and-anyattribute-nodes.md)