---
title: Combinar documentos XML | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML, documents
- process management solution tutorial, merging XML documents
ms.assetid: 444c983a-397a-4342-85e1-80bb152986d9
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94684cd9bf1992a592efd7b97c46838c9c9a3134
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="merging-xml-documents"></a>Combinar documentos XML
Uno de los mensajes que el **OrderBroker** orquestación crea consta de uno o actualizar la base de datos de historial de SQL Server. Este mensaje contiene campos del mensaje de pedido así como del mensaje de pedido original. El pedido original aparece en este mensaje en forma de cadena. Esto coincide con el tipo de datos del historial de pedidos de la base de datos.  
  
 No es posible tomar un mensaje, convertirlo en una cadena y situarlo en otro mensaje con una asignación. La orquestación utiliza una función auxiliar, **InsertOrderBody**, para agregar el mensaje de pedido original como una cadena para el mensaje de historial base.  
  
 El **OrderBroker** orquestación utiliza la asignación, **CSR_OrderRequest_To_SQLHistoryInsert**, para convertir el mensaje de pedido en el mensaje de historial base. Aparece la información de un pedido como atributos de un **OrderLog** elemento. El mensaje original aparece como otro atributo de este elemento.  
  
 El **InsertOrderBody** método toma como argumentos el mensaje de pedido original, el mensaje de historial base y devuelve el mensaje de historial completado. El siguiente código muestra las partes del método que insertan el mensaje en forma de cadena:  
  
```  
public static XmlDocument InsertOrderBody( XmlDocument orderDoc,   
                                    XmlDocument historyInsertDoc)  
{  
...  
    XmlNode root = historyInsertDoc.FirstChild;  
  
    //Create a new attribute.  
    XmlNode attr = historyInsertDoc.CreateNode(XmlNodeType.Attribute,  
                                     "OriginalMsg", root.NamespaceURI);  
    attr.Value = orderDoc.OuterXml;  
  
    try  
    {  
        // XPath expression not shown for formatting reasons and  
        // replaces ".." in the following code  
        XmlNode destnode = historyInsertDoc.SelectSingleNode("..");  
        //Add the attribute to the document.  
        destnode.Attributes.SetNamedItem(attr);  
    }  
...  
  
    return historyInsertDoc;  
}  
```  
  
 Después de comprobar que recibió ambos argumentos, la **InsertOrderBody** método encuentra el nodo raíz del mensaje de actualización de historial. A continuación, crea un nodo que contiene el **OriginalMsg** de atributo y asigna el mensaje de pedido original para el valor del atributo. En este punto, el nodo solamente existe. Aún no forma parte de un elemento.  
  
 Después de crear el nodo de atributo, el método encuentra el nodo donde adjuntará el atributo mediante una expresión XPath. Después de encontrar el nodo, el método agrega el nodo de atributo a la colección de atributos del nodo.  
  
> [!NOTE]
>  Aunque la **OriginalMsg** atributo no existe inicialmente en el mensaje de historial base, es, por supuesto, especificada en el esquema. Los elementos XML que agregue a sus mensajes en código se deben especificar en los esquemas para tales mensajes.  
  
## <a name="see-also"></a>Vea también  
 [Aspectos destacados de la implementación de la solución de administración de procesos empresariales](../core/implementation-highlights-of-the-business-process-management-solution.md)