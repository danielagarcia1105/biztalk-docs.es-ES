---
title: Nodos de grupo de secuencias | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 139c3daa-a682-4bf7-bbb7-b5694ced0431
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2465ad10e6598a4b9e1afa88190de4c1711c1f86
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sequence-group-nodes"></a>Nodos Grupo de secuencias

## <a name="overview"></a>Información general
En el Editor de BizTalk, puede insertar un **grupo de secuencias** nodo para contener otros nodos que deben aparecer en un mensaje de instancia en el mismo orden en que aparecen en la **grupo de secuencias** nodo. Los nodos contenidos deben ser nodos que se correspondan con elementos XML, pero no pueden ser nodos que se correspondan con atributos XML.  
  
> [!NOTE]
>  En el Editor de BizTalk, el **grupo de secuencias** nodo se representa de forma predeterminada con la cadena \<secuencia > en la vista de árbol de esquema. Si establece una referencia a un **grupo de secuencias** nodo, por ejemplo, x, se representa como \<Group: x > en la vista de árbol de esquema.  
  
 Puede que desee agregar un **grupo de secuencias** para declarar un grupo de elementos globales.  
  
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
  
 Ya que existen GroupItem1 y GroupItem2 en ambos casos, puede declarar un grupo de secuencias globales que sea un secundario tanto de Record1 como de Record2. Para obtener instrucciones paso a paso sobre cómo declarar un grupo de secuencias globales, consulte [crear referencias a otro nodo o tipo](../core/how-to-create-references-to-another-node-or-type.md).  
  
 Un usuario puede cambiar el grupo oculto para que sea un **grupo de elecciones** nodo o un **todos los grupos** nodo (por lo que no es necesariamente un **grupo de secuencias** nodo) cambiando el  **Tipo de orden de grupo** propiedad. Para obtener más información acerca de esta propiedad [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="xsd-representation"></a>Representación XSD  
 Cuando un **grupo de secuencias** nodo se inserta en un **registro** nodo, se inserta al final de cualquier otro nodo secundario dentro de la **secuencia**, **opción**, o **todos los** elemento en el **registro** nodo. En el ejemplo siguiente se muestra un nuevo **grupo de secuencias** nodo, en negrita, insertado al final de la **secuencia** elemento en un **registro** nodo (con nodos de nombre que deja clara su identidad).  
  
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
-  [Representación de esquemas de BizTalk](../core/biztalk-representation-of-schemas.md)   
-  [Propiedades de nodo](../core/node-properties.md)   
-  **Propiedades de nodo de grupo de secuencias**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
-  [Cómo establecer propiedades de nodo](../core/how-to-set-node-properties.md)