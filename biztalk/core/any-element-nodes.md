---
title: Nodos cualquier elemento | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7e30fcf-31bc-4d48-9bc7-0be90e927127
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 905d6c25c5c2021840f4257c29df015d4bcb374e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002437"
---
# <a name="any-element-nodes"></a>Nodos Cualquier elemento
En el Editor de BizTalk, puede usar un **cualquier elemento** nodo para indicar una ubicación dentro de un mensaje de instancia donde pueden aparecer elementos desconocidos. Esto es útil para situaciones en las que se sabe que puede aparecer algún elemento en una ubicación concreta de un mensaje de instancia, pero se desconoce el nombre del elemento o lo complicado que puede ser. Si coloca un **cualquier elemento** nodo en la ubicación adecuada dentro del esquema, BizTalk puede procesar esas partes desconocidas del mensaje. El único requisito es que el XML correspondiente tenga un formato correcto.  
  
> [!NOTE]
>  En el Editor de BizTalk, el **cualquier elemento** nodo se representa con la cadena \<cualquier\> en la vista de árbol de esquema.  
> 
> [!NOTE]
>  Puede controlar el grado al que la parte desconocida del mensaje se valida como XML con formato correcto con el **Process Contents** propiedad. En muchos casos es posible que deba establecer el **Process Contents** propiedad **omitir** para el contenido de un mensaje de instancia en la ubicación de la **cualquier elemento** nodo procesarse. Conservar el valor predeterminado de **Strict** para el **Process Contents** propiedad impedirá instancia mensaje pasar la validación.  
> 
> Obtener más detalles sobre esta propiedad [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="xsd-representation"></a>Representación XSD  
 Cuando un **cualquier elemento** nodo se agrega a un **registro** nodo, o a otro nodo al que puede agregarse como un **grupo Sequence**, **grupo de elecciones**, o **todos los grupos** nodo, una etiqueta XML se agrega a la definición de esquema XML correspondiente representación del lenguaje (XSD) del esquema. En el ejemplo siguiente, un nuevo **cualquier elemento** nodo, cuya representación XSD se muestra en negrita, se ha agregado a una existente **registro** nodo que ya contiene un **delelementodecampo** nodo.  
  
```  
<xs:element name="ExistingRecord">  
    <xs:complexType>  
        <xs:sequence>  
             <xs:element name="ExistingFieldElement" type="xs:string" />  
            <xs:any />  
        </xs:sequence>  
    </xs:complexType>  
</xs:element>  
```  
  
 Suponiendo que el **Process Contents** propiedad de la **cualquier elemento** nodo se establece en **Skip**, en un mensaje de instancia regido por este fragmento de esquema, un **ExistingRecord** elemento se espera que contenga un **ExistingFieldElement** elemento que contiene datos de cadena, seguido de los elementos individuales de complejidad arbitraria.  
  
## <a name="see-also"></a>Vea también  
 [Representación de esquemas de BizTalk](../core/biztalk-representation-of-schemas.md)   
 [Propiedades de nodo](../core/node-properties.md)   
 [Cómo establecer las propiedades de nodo](../core/how-to-set-node-properties.md)   
 [Nodos Cualquier atributo](../core/any-attribute-nodes.md)