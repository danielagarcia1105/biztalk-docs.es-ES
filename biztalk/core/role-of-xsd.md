---
title: Rol de XSD | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1fe08f6b-563f-4bae-a5be-551e487b2a6d
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ad2f99b60de5ebb2a3cd7e102a2f3f7b787d1ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="role-of-xsd"></a><span data-ttu-id="85b2f-102">Rol de XSD</span><span class="sxs-lookup"><span data-stu-id="85b2f-102">Role of XSD</span></span>
<span data-ttu-id="85b2f-103">El lenguaje de definición de esquemas XML (XSD) proporciona la sintaxis subyacente de los esquemas de mensaje definidos en BizTalk.</span><span class="sxs-lookup"><span data-stu-id="85b2f-103">The XML Schema definition (XSD) language provides the underlying syntax of the message schemas defined within BizTalk.</span></span> <span data-ttu-id="85b2f-104">Aunque las vistas de árbol del Editor de BizTalk y el Asignador de BizTalk utilizan una jerarquía gráfica específica de BizTalk para los nodos de registro y de campo (entre otros tipos de nodos), cada uno con su propio conjunto de propiedades, dichas jerarquías se crean y mantienen como XSD.</span><span class="sxs-lookup"><span data-stu-id="85b2f-104">Although the tree views in BizTalk Editor and BizTalk Mapper use a BizTalk-specific graphical hierarchy of record and field nodes (among other types of nodes), each with its own set of properties, such hierarchies are constructed and persisted as XSD.</span></span> <span data-ttu-id="85b2f-105">El Editor de BizTalk proporciona una vista XSD de solo lectura en la que se puede ver la definición XSD creada cuando se agregan o quitan varios nodos de la representación gráfica del esquema en la vista de árbol y cuando se modifican los valores de las propiedades asociadas con esos nodos.</span><span class="sxs-lookup"><span data-stu-id="85b2f-105">BizTalk Editor provides a read-only XSD view in which you can see the XSD that is constructed as various nodes are added to or removed from the graphic representation of the schema in the tree view, and as the values of the properties associated with those nodes are changed.</span></span> <span data-ttu-id="85b2f-106">Aunque por lo general no es necesario conocer los detalles de XSD para crear correctamente esquemas sencillos con el Editor de BizTalk, si analiza los cambios de XSD que aparecen al realizar modificaciones en la jerarquía del esquema en la vista de árbol, aprenderá a usar el lenguaje XSD.</span><span class="sxs-lookup"><span data-stu-id="85b2f-106">Although it is usually not necessary to understand the details of XSD to successfully construct simple schemas with BizTalk Editor, if you study the XSD changes as you make changes to the schema hierarchy in the tree view, you will learn to use XSD.</span></span>  
  
 <span data-ttu-id="85b2f-107">La característica de anotación de esquema de XSD, con el amplio conjunto de anotaciones definidas por BizTalk Server, permite ampliar de un modo eficaz la definición XSD para que sea compatible con la semántica necesaria para representar los mensajes que no son XML, como los archivos sin formato.</span><span class="sxs-lookup"><span data-stu-id="85b2f-107">The schema annotation feature within XSD, with the extensive set of annotations defined by BizTalk Server, effectively allows XSD to be extended to support the necessary semantics for representing non-XML messages such as flat files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85b2f-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="85b2f-108">See Also</span></span>  
 <span data-ttu-id="85b2f-109">[Recursos XSD en Internet](../core/xsd-resources-on-the-web.md) </span><span class="sxs-lookup"><span data-stu-id="85b2f-109">[XSD Resources on the Web](../core/xsd-resources-on-the-web.md) </span></span>  
 [<span data-ttu-id="85b2f-110">Acerca de los esquemas</span><span class="sxs-lookup"><span data-stu-id="85b2f-110">About Schemas</span></span>](../core/about-schemas.md)