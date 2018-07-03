---
title: Nodos grupo de secuencias | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 139c3daa-a682-4bf7-bbb7-b5694ced0431
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c113d0cfd0f6055d55b0329bba3c1ec60bf835e8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019746"
---
# <a name="sequence-group-nodes"></a>Nodos Grupo de secuencias

## <a name="overview"></a>Información general
En el Editor de BizTalk, puede insertar un **grupo Sequence** nodo contenga otros nodos que deben aparecer en un mensaje de instancia en el mismo orden en que aparecen dentro de la **grupo de secuencias** nodo. Los nodos contenidos deben ser nodos que se correspondan con elementos XML, pero no pueden ser nodos que se correspondan con atributos XML.  

> [!NOTE]
>  En el Editor de BizTalk, el **grupo Sequence** nodo se representa de forma predeterminada con la cadena \<secuencia\> en la vista de árbol de esquema. Si establece una referencia a un **grupo Sequence** nodo, por ejemplo, x, se representa como \<Group: x\> en la vista de árbol de esquema.  

 Es posible que desee agregar un **grupo Sequence** para declarar un grupo de elementos globales.  

 Puede que necesite crear un esquema para XML como se indica a continuación.  

```  
<Root>  
    <Record1>  
        <GroupItem1/>  
        <GroupItem2/>  
        <NotAGroupItem>  
    </Record1>  
    <Record2>  
        <GroupItem1/>  
        <GroupItem2/>  
    </Record2>  
</Root>  

```  

 Ya que existen GroupItem1 y GroupItem2 en ambos casos, puede declarar un grupo de secuencias globales que sea un secundario tanto de Record1 como de Record2. Para obtener instrucciones paso a paso acerca de cómo declarar un grupo de secuencias globales, consulte [crear referencias a otro nodo o tipo](../core/how-to-create-references-to-another-node-or-type.md).  

 Un usuario puede cambiar el grupo oculto para que sea un **grupo de elecciones** nodo o un **todos los grupos** nodo (por lo que no es necesariamente un **grupo Sequence** nodo) cambiando la  **Group Order Type** propiedad. Obtener más detalles sobre esta propiedad [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].

## <a name="xsd-representation"></a>Representación XSD  
 Cuando un **grupo Sequence** nodo se inserta en un **registro** nodo, se inserta al final de cualquier otro nodo secundario dentro de la **secuencia**, **elección**, o **todas** elemento en el **registro** nodo. En el ejemplo siguiente se muestra un nuevo **grupo Sequence** nodo, en negrita, insertado al final de la **secuencia** elemento en un **registro** nodo (cuyos para aclarar sus identidad).  

```  
<xs:element name="ContainingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="ExistingFieldElement" type="xs:string" />  
        </xs:sequence>  
    </xs:complexType>  
</xs:element>  

```  

## <a name="see-also"></a>Vea también  
- [Representación de esquemas en BizTalk](../core/biztalk-representation-of-schemas.md)   
- [Propiedades de los nodos](../core/node-properties.md)   
- **Propiedades de nodo de grupo de secuencias** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
- [Cómo establecer las propiedades de nodo](../core/how-to-set-node-properties.md)
