---
title: Combinar documentos XML | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML, documents
- process management solution tutorial, merging XML documents
ms.assetid: 444c983a-397a-4342-85e1-80bb152986d9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94684cd9bf1992a592efd7b97c46838c9c9a3134
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262644"
---
# <a name="merging-xml-documents"></a><span data-ttu-id="257ed-102">Combinar documentos XML</span><span class="sxs-lookup"><span data-stu-id="257ed-102">Merging XML Documents</span></span>
<span data-ttu-id="257ed-103">Uno de los mensajes que el **OrderBroker** orquestación crea consta de uno o actualizar la base de datos de historial de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="257ed-103">One of the messages that the **OrderBroker** orchestration creates is one to update the SQL Server history database.</span></span> <span data-ttu-id="257ed-104">Este mensaje contiene campos del mensaje de pedido así como del mensaje de pedido original.</span><span class="sxs-lookup"><span data-stu-id="257ed-104">This message contains fields from the order message as well as the original order message.</span></span> <span data-ttu-id="257ed-105">El pedido original aparece en este mensaje en forma de cadena.</span><span class="sxs-lookup"><span data-stu-id="257ed-105">The original order appears in this message a string.</span></span> <span data-ttu-id="257ed-106">Esto coincide con el tipo de datos del historial de pedidos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="257ed-106">This matches the data type for the order history in the database.</span></span>  
  
 <span data-ttu-id="257ed-107">No es posible tomar un mensaje, convertirlo en una cadena y situarlo en otro mensaje con una asignación.</span><span class="sxs-lookup"><span data-stu-id="257ed-107">It isn't possible to take a message, convert it to a string, and place it in another message with a map.</span></span> <span data-ttu-id="257ed-108">La orquestación utiliza una función auxiliar, **InsertOrderBody**, para agregar el mensaje de pedido original como una cadena para el mensaje de historial base.</span><span class="sxs-lookup"><span data-stu-id="257ed-108">The orchestration uses a helper function, **InsertOrderBody**, to add the original order message as a string to the base history message.</span></span>  
  
 <span data-ttu-id="257ed-109">El **OrderBroker** orquestación utiliza la asignación, **CSR_OrderRequest_To_SQLHistoryInsert**, para convertir el mensaje de pedido en el mensaje de historial base.</span><span class="sxs-lookup"><span data-stu-id="257ed-109">The **OrderBroker** orchestration uses the map, **CSR_OrderRequest_To_SQLHistoryInsert**, to convert the order message into the base history message.</span></span> <span data-ttu-id="257ed-110">Aparece la información de un pedido como atributos de un **OrderLog** elemento.</span><span class="sxs-lookup"><span data-stu-id="257ed-110">The information for an order appears as attributes of an **OrderLog** element.</span></span> <span data-ttu-id="257ed-111">El mensaje original aparece como otro atributo de este elemento.</span><span class="sxs-lookup"><span data-stu-id="257ed-111">The original message appears as another attribute of this element.</span></span>  
  
 <span data-ttu-id="257ed-112">El **InsertOrderBody** método toma como argumentos el mensaje de pedido original, el mensaje de historial base y devuelve el mensaje de historial completado.</span><span class="sxs-lookup"><span data-stu-id="257ed-112">The **InsertOrderBody** method takes as arguments the original order message, the base history message, and returns the completed history message.</span></span> <span data-ttu-id="257ed-113">El siguiente código muestra las partes del método que insertan el mensaje en forma de cadena:</span><span class="sxs-lookup"><span data-stu-id="257ed-113">The following code shows the portions of the method that inserts the message as a string:</span></span>  
  
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
  
 <span data-ttu-id="257ed-114">Después de comprobar que recibió ambos argumentos, la **InsertOrderBody** método encuentra el nodo raíz del mensaje de actualización de historial.</span><span class="sxs-lookup"><span data-stu-id="257ed-114">After verifying that it received both arguments, the **InsertOrderBody** method finds the root node of the history update message.</span></span> <span data-ttu-id="257ed-115">A continuación, crea un nodo que contiene el **OriginalMsg** de atributo y asigna el mensaje de pedido original para el valor del atributo.</span><span class="sxs-lookup"><span data-stu-id="257ed-115">It then creates a node containing the **OriginalMsg** attribute and assigns the original order message to the attribute's value.</span></span> <span data-ttu-id="257ed-116">En este punto, el nodo solamente existe.</span><span class="sxs-lookup"><span data-stu-id="257ed-116">At this point, the node simply exists.</span></span> <span data-ttu-id="257ed-117">Aún no forma parte de un elemento.</span><span class="sxs-lookup"><span data-stu-id="257ed-117">It is not yet part of a element.</span></span>  
  
 <span data-ttu-id="257ed-118">Después de crear el nodo de atributo, el método encuentra el nodo donde adjuntará el atributo mediante una expresión XPath.</span><span class="sxs-lookup"><span data-stu-id="257ed-118">After creating the attribute node, the method finds the node where it will attach the attribute using an XPath expression.</span></span> <span data-ttu-id="257ed-119">Después de encontrar el nodo, el método agrega el nodo de atributo a la colección de atributos del nodo.</span><span class="sxs-lookup"><span data-stu-id="257ed-119">After it locates the node, the method adds the attribute node to the attributes collection of the node.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="257ed-120">Aunque la **OriginalMsg** atributo no existe inicialmente en el mensaje de historial base, es, por supuesto, especificada en el esquema.</span><span class="sxs-lookup"><span data-stu-id="257ed-120">Although the **OriginalMsg** attribute does not initially exist in the base history message, it is, of course, specified in the schema.</span></span> <span data-ttu-id="257ed-121">Los elementos XML que agregue a sus mensajes en código se deben especificar en los esquemas para tales mensajes.</span><span class="sxs-lookup"><span data-stu-id="257ed-121">XML elements that you add to your messages in code should be specified in the schemas for those messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="257ed-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="257ed-122">See Also</span></span>  
 [<span data-ttu-id="257ed-123">Aspectos destacados de la implementación de la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="257ed-123">Implementation Highlights of the Business Process Management Solution</span></span>](../core/implementation-highlights-of-the-business-process-management-solution.md)