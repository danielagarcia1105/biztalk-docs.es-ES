---
title: Nodos cualquier atributo de | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fa2d25bc-3a8f-4fd9-acad-341b8e80c737
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98cbd0ea288e14b68bc16f5e9a88f636bc229b9d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014485"
---
# <a name="any-attribute-nodes"></a>Nodos Cualquier atributo
En el Editor de BizTalk, puede usar un **cualquier atributo** nodo para indicar un elemento (conocido) dentro de un mensaje de instancia para el que pueden aparecer cero o más atributos desconocidos. Esto resulta útil para las situaciones en las que sabe que un elemento específico estará presente en una ubicación específica de un mensaje de instancia, pero no está seguro de qué atributos incluirá exactamente dicho elemento. Si coloca un **cualquier atributo** nodo dentro de la **registro** nodo asociado con el elemento correspondiente, BizTalk puede procesar dicho elemento, con el único requisito que se va a que son los atributos asociados sintácticamente correcto (attributeName = "attributeValue").  
  
> [!NOTE]
>  En el Editor de BizTalk, el **cualquier atributo** nodo se representa con la cadena \<AnyAttribute\> en la vista de árbol de esquema.  
> 
> [!NOTE]
>  Puede controlar el grado al que la parte desconocida del mensaje se valida como XML con formato correcto con el **Process Contents** propiedad. En muchos casos es posible que deba establecer el **Process Contents** propiedad **omitir** para el contenido de un mensaje de instancia en la ubicación de la **cualquier atributo** nodo procesarse . Conservar el valor predeterminado de **Strict** para el **Process Contents** propiedad impedirá instancia mensaje pasar la validación.  
> 
> Obtener más detalles sobre esta propiedad [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="xsd-representation"></a>Representación XSD  
 Cuando un **cualquier atributo** nodo se agrega a un **registro** nodo o a un **grupo de atributos** nodo, una etiqueta XML se agrega a la definición de esquema XML correspondiente lenguaje (XSD) representación del esquema. En el ejemplo siguiente, un nuevo **cualquier atributo** nodo, cuya representación XSD se muestra en negrita, se ha agregado a una existente **registro** nodo que ya contiene un **delelementodecampo** nodo.  
  
```  
<xs:element name="ExistingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="ExistingFieldElement" type="xs:string" />  
        </xs:sequence>  
        <xs:anyAttribute />  
    </xs:complexType>  
</xs:element  
```  
  
 En el ejemplo anterior, la representación XSD del nuevo **cualquier atributo** nodo agrega una **anyAttribute** elemento al final de la que contiene (**registro** nodo) **elemento** elemento, fuera la **secuencia** elemento y dentro del **complexType** elemento. Aquí es donde todos los **atributo** elementos, excepto aquellos con una **grupo de atributos** nodo, se agregan a los que contiene **elemento** elementos.  
  
 Ahora y suponiendo que el **Process Contents** propiedad de la **cualquier atributo** nodo se establece en **Skip**, en un mensaje de instancia regido por este fragmento de esquema, un  **ExistingRecord** se espera el elemento y puede contener cualquier atributo siempre y cuando estén bien formadas con respecto a la sintaxis XML. (Para que se ajuste al fragmento XSD en este ejemplo, también debe contener el **ExistingFieldElement** elemento también.)  
  
## <a name="see-also"></a>Vea también  
 [Representación de esquemas de BizTalk](../core/biztalk-representation-of-schemas.md)   
 [Propiedades de nodo](../core/node-properties.md)   
 [Cómo establecer las propiedades de nodo](../core/how-to-set-node-properties.md)   
 [Nodos Cualquier elemento](../core/any-element-nodes.md)