---
title: "Raíz nodos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2161f877-835e-434d-a8d1-2426f977d60e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2070982a6bca09e8bffb2bcc88e5997360c86851
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="root-nodes"></a>Nodos raíz
En el Editor de BizTalk, los nodos secundarios de la **esquema** nodo se conocen como **raíz** nodos. **Raíz** nodos son un tipo especial de **registro** nodo, y tienen algunas propiedades más que normal **registro** nodos. El **raíz** nodo representa el tipo de documento se describe el esquema y se pueden cambiar según corresponda. Por ejemplo, puede cambiar el nombre del **raíz** nodo, por lo que TI describe el tipo de mensaje que representa el esquema, como purchaseOrder, orderAcknowledgment o shipNotice.  
  
 Cuando se crea un nuevo esquema XML en el Editor de BizTalk, el **esquema** y un nodo **raíz** nodo se crean automáticamente. Puede crear más **raíz** nodos como elementos secundarios de la **esquema** nodo; Esto le permite crear una biblioteca de esquemas dentro de una única representación de lenguaje de definición (XSD) del esquema XML. Por ejemplo, puede crear una biblioteca de esquemas para describir los distintos esquemas de mensajes relacionados con el envío de pedidos, así como cambiar el nombre de varios nodos raíz a purchaseOrder, orderAcknowledgment y shipNotice.  
  
## <a name="xsd-representation"></a>Representación XSD  
 El ejemplo siguiente muestra las líneas en la representación XSD del esquema que corresponden a la **raíz** nodo en la vista de árbol del esquema.  
  
```  
<?xml version="1.0" encoding="utf-16" ?>  
<xs:schema xmlns="http://BizTalk_Server_Project1.Schema2"  
    xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
    targetNamespace="http://BizTalk_Server_Project1.Schema2"  
    xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:element name="Root">  
        <xs:complexType />   
    </xs:element>  
</xs:schema>  
```  
  
 **Raíz** nodos en el Editor de BizTalk representan el elemento principal de una instancia XML correspondiente del mensaje en cuestión. Por ejemplo, si la **raíz** se cambia el nombre de nodo de un esquema concreto a purchaseOrder, la representación XSD correspondiente tiene la siguiente estructura de alto nivel.  
  
```  
<?xml version="1.0" encoding="utf-16" ?>  
<xs:schema xmlns="http://BizTalk_Server_Project1.Schema2"  
    xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
    targetNamespace="http://BizTalk_Server_Project1.Schema2"  
    xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:element name="">  
        <xs:complexType>   
            ...  
        </xs:complexType>   
    </xs:element>  
</xs:schema>  
```  
  
 Un mensaje de instancia XML correspondiente debe tener la siguiente estructura básica.  
  
```  
<?xml version="1.0"?>  
<purchaseOrder ...>  
    ...  
</purchaseOrder>  
```  
  
> [!NOTE]
>  No pueden tener nodos raíz **campo** atributos. **Campo** atributos conectado a la **raíz** nodo no se guardan con el esquema.  
  
## <a name="see-also"></a>Vea también  
-  [Representación de esquemas de BizTalk](../core/biztalk-representation-of-schemas.md)   
-  [Propiedades de nodo](../core/node-properties.md)   
-  **Propiedades del nodo registro**  [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
-  [Cómo establecer propiedades de nodo](../core/how-to-set-node-properties.md)