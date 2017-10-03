---
title: Nodo de esquema | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7ea02c2a-ee00-4f44-9086-83d7ac4a8832
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dee662cb9cb6e86b85a7760daf45af832a447b5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="schema-node"></a>Esquema (nodo)

## <a name="overview"></a>Información general
En el Editor de BizTalk, la parte superior de la jerarquía del esquema es siempre el **esquema** nodo, que no se pueden cambiar. El **esquema** nodo corresponde a la **esquema** elemento en la representación del lenguaje de esquema XML (XSD) de la definición del esquema.  
  
> [!NOTE]
>  En el Editor de BizTalk, el **esquema** nodo se representa con la cadena \<esquema > en la vista de árbol de esquema.  
  
 En general, las propiedades de la **esquema** nodo corresponden a los atributos de la **esquema** elemento en la representación XSD del esquema. Para obtener información general acerca de las propiedades de nodo, vea [propiedades del nodo](../core/node-properties.md). Para obtener información de referencia acerca de las propiedades de la **esquema** nodo, consulte el **propiedades del nodo esquema** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
 Cuando se crea un nuevo esquema XML en el Editor de BizTalk, el **esquema** y un nodo **raíz** nodo se crean automáticamente.  
  
## <a name="xsd-representation"></a>Representación XSD  
 El siguiente ejemplo muestra, en negrita, las líneas en la representación XSD del esquema que corresponden a la  **\<esquema >** nodo en la vista de árbol del esquema.  
  
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
  
## <a name="see-also"></a>Vea también  
 [Representación de esquemas de BizTalk](../core/biztalk-representation-of-schemas.md)   
 [Propiedades de nodo](../core/node-properties.md)   
 [Establecer las propiedades de nodo](../core/how-to-set-node-properties.md)