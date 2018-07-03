---
title: Nodos grupo de atributos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea02fae8-4e03-486a-8d9d-185ae230d3a0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7314c14a611096f92c8fd2f95b300832d6b44a0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017268"
---
# <a name="attribute-group-nodes"></a>Nodos Grupo de atributos

## <a name="overview"></a>Información general
En el Editor de BizTalk, puede agregar un **grupo de atributos** nodo a un **registro** nodo o a otro **grupo de atributos** nodo contenga un grupo de atributos que se esperan que use con más que uno **registro** nodo. Agregar un **grupo de atributos** nodo a otro **grupo de atributos** nodo logra el anidamiento de grupos de atributos. Esto le permite definir un grupo de atributos en un mismo lugar que se puede usar en varios **registro** o **grupo de atributos** nodos. Cualquier modificación que se realice posteriormente en el grupo de atributos se propagará a todos los nodos que tengan asociado dicho grupo de atributos, con independencia del contexto de nodo en el que se realicen las modificaciones.  

> [!NOTE]
>  En el Editor de BizTalk, el **AttributeGroup** nodo se representa de forma predeterminada con la cadena \<AttribGroup:attribGroup*N* \> en la vista de árbol de esquema, donde  *N* es un número de progresión. Puede cambiar el attribGroup*N* parte de su nombre escribiendo un nuevo nombre único en su **Group Reference** propiedad.  

 Al crear inicialmente un **grupo de atributos** nodo, lo inserta en una de las **registro** o **grupo de atributos** nodos en el que se usará y, opcionalmente, cambiar su nombre en su **Group Reference** propiedad. Hay dos maneras de utilizar el mismo grupo de atributos en otro **registro** o **grupo de atributos** nodo:  

- Puede copiar existente **grupo de atributos** nodo y, a continuación, péguelo en el que otras **registro** nodo.  

- Puede insertar un nuevo **grupo de atributos** nodo en que otras **registro** nodo y, después, establezca el **Group Reference** propiedad del nuevo **delgrupodeatributos** nodo para hacer referencia a una existente **grupo de atributos** nodo.  

  A partir de entonces, puede modificar el **grupo de atributos** nodo: por ejemplo, mediante Agregar o eliminar un **atributo de campo** nodo, en el contexto de cualquier **registro** o  **Grupo de atributos** nodo en el que haya pegado. Que el cambio se propagará a todos los demás **registro** o **grupo de atributos** nodos que está asociado el grupo de atributos.  

  Tendría sentido agregar un **grupo de atributos** nodo sin agregar al menos un nodo pertinente, donde se incluyen los nodos pertinentes **atributo de campo** nodos, **cualquier atributo**nodos y (anidada) **grupo de atributos** nodos. De hecho, un grupo de atributos que solo contiene un único atributo está en cierto modo mal concebido, salvo si planea agregar más atributos en el futuro.  

  **Grupo de atributos** nodos pueden anidarse, lo que permite más posibilidades en cómo se pueden construir y combinar grupos de atributos. **Grupo de atributos** nodos también pueden contener el **cualquier atributo** nodo, lo que permite un grupo de atributos para que contenga las capacidades de carácter comodín con respecto a las instancias de atributo y puede acomodar.  

## <a name="xsd-representation"></a>Representación XSD  
 Cuando un **grupo de atributos** nodo se agrega primero a un **registro** nodo o a otro **grupo de atributos** nodos, dos áreas distintas de la definición de esquemas XML (XSD) correspondiente representación de lenguaje del esquema se ven afectados. En el ejemplo siguiente, un nuevo **grupo de atributos** nodo, en negrita, se ha agregado a una existente **registro** nodo que ya contiene una existente **elemento de campo** nodo.  

```  
        ...  
        <xs:element name="ExistingRecord">  
            <xs:complexType>  
                <xs:sequence>  
                    <xs:element name="ExistingFieldElement" type="xs:string" />  
                </xs:sequence>  
                <xs:attributeGroup ref="attrGroup0" />  
            </xs:complexType>  
        </xs:element>  
        ...   
    <xs:attributeGroup name="attrGroup0" />  
</xs:schema>  
```  

 Tenga en cuenta cómo el **attributeGroup** dentro de la representación XSD del elemento de la **registro** nodo hace referencia a un global **attributeGroup** elemento que se agrega como elemento secundario de la **esquema** elemento. Esta definición global del grupo de atributos en la representación XSD del esquema permite hacer referencia al grupo de atributos en varias ubicaciones del esquema.  

> [!NOTE]
>  Nombres de grupo de atributos predeterminados que se proporcionan de forma automática tienen el formato attrGroup*N*, donde *N* es un número de progresión. Puede cambiar el nombre de un grupo de atributos al proporcionar un nombre nuevo y único en su **Group Reference** propiedad. No se puede cambiar el nombre de un grupo de atributos, en la posición actual, en el árbol de esquema.  

## <a name="see-also"></a>Vea también  
- [Representación de esquemas en BizTalk](../core/biztalk-representation-of-schemas.md)   
- [Propiedades de los nodos](../core/node-properties.md)   
- **Propiedades de nodo de grupo de secuencias** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]  
- [Cómo establecer las propiedades de nodo](../core/how-to-set-node-properties.md)   
- [Nodos Atributo de campo](../core/field-attribute-nodes.md)   
- [Nodos Cualquier atributo](../core/any-attribute-nodes.md)
