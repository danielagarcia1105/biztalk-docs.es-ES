---
title: Anidar sobres de mensajes XML | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e880cef1-4e73-4bce-a06e-8c4d23bc5a8c
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46b0f505dd9ba7da71df1cb460f9c9a6610763d3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="nested-xml-message-envelopes"></a>Sobres de mensajes XML anidados
Los sobres XML se pueden anidar para crear estructuras complejas de documentos. Los sobres XML anidados pueden aparecer de dos formas: flexible y canónica. En el siguiente ejemplo se muestra la forma flexible de documentos con doble cifrado, donde los documentos y los sobres (en negrita) pueden aparecer en el mismo nivel dentro de un sobre envolvente.  
  
```  
<envelope1>  
    <document1/>    <envelope2>  
        <document2/>  
        <document3/>  
    </envelope2>    <document4/>  
</envelope1>  
```  
  
 El siguiente ejemplo muestra un mensaje de instancia similar que se ajusta a la forma canónica de documentos con doble cifrado, donde todos los documentos aparecen en el mismo nivel dentro del sobre más interno.  
  
```  
<envelope1>  
    <envelope2>  
        <document1/>  
        <document2/>  
        <document3/>  
        <document4/>  
    </envelope2>  
</envelope1>  
  
```  
  
 Para un determinado mensaje de instancia con una de las formas descritas, el desensamblador XML producirá los documentos document1, document2, document3 y document4. El contexto del mensaje de cada uno de estos documentos incluye las propiedades promocionadas a partir del documento correspondiente, así como las propiedades promocionadas dentro de cada uno de los sobres envolventes. La tabla siguiente muestra las propiedades promocionadas que se incluirán en el contexto del mensaje de cada documento no incluido, para los ejemplos de forma flexible y canónica, según las promociones de propiedades que se especifiquen en la primera columna para los distintos sobres y documentos.  
  
|Promociones de propiedades especificadas|Propiedades del contexto del mensaje para el ejemplo de forma flexible|Propiedades del contexto del mensaje para el ejemplo de forma canónica|  
|-----------------------------------|---------------------------------------------------------------|----------------------------------------------------------------|  
|envelope1: p1<br /><br /> envelope2: p3<br /><br /> Document1: p2<br /><br /> Document2: p4 y p5<br /><br /> document3: ninguna promoción<br /><br /> document4: ninguna promoción|Document1: p1, p2<br /><br /> Document2: p1, p3, p4, p5<br /><br /> document3: p1, p3<br /><br /> document4: p1|Document1: p1, p2, p3<br /><br /> Document2: p1, p3, p4, p5<br /><br /> document3: p1, p3<br /><br /> document4: p1, p3|  
  
## <a name="see-also"></a>Vea también  
 [Sobres de mensajes XML](../core/xml-message-envelopes.md)   
 [Estructura de un mensaje XML](../core/structure-of-an-xml-message.md)   
 [Cómo crear esquemas de sobres](../core/how-to-create-schemas-for-envelopes.md)