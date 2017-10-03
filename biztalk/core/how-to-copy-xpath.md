---
title: "Cómo copiar XPath | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 404599d4-0fb3-4c7c-91e6-1295d9d0965e
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb282c5c32d8da62a9da6d7a9c900c798e44eee7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-copy-xpath"></a><span data-ttu-id="e813c-102">Copia de XPath</span><span class="sxs-lookup"><span data-stu-id="e813c-102">How to Copy XPath</span></span>
<span data-ttu-id="e813c-103">El lenguaje de definición de esquemas XML (XSD) proporciona la sintaxis subyacente de los esquemas de mensaje definidos en BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="e813c-103">The XML Schema definition (XSD) language provides the underlying syntax of the message schemas defined within BizTalk Server.</span></span> <span data-ttu-id="e813c-104">Aunque las vistas de árbol del Asignador de BizTalk utilizan una jerarquía gráfica específica de BizTalk para los nodos de registro y de campo (entre otros tipos de nodos), cada uno con su propio conjunto de propiedades, dichas jerarquías se crean y mantienen como XSD.</span><span class="sxs-lookup"><span data-stu-id="e813c-104">Although the tree views in BizTalk Mapper use a BizTalk-specific graphical hierarchy of record and field nodes (among other types of nodes), each with its own set of properties, such hierarchies are constructed and persisted as XSD.</span></span>  
  
 <span data-ttu-id="e813c-105">En escenarios donde las asignaciones son complejas y abarcan varias páginas de cuadrícula, localizar el principal de un nodo de esquema puede resultar complicado.</span><span class="sxs-lookup"><span data-stu-id="e813c-105">In scenarios where maps are complex and span across grid pages, locating the parent of a schema node can be difficult.</span></span> <span data-ttu-id="e813c-106">La ruta de acceso XSD será útil aquí.</span><span class="sxs-lookup"><span data-stu-id="e813c-106">The XSD path will be of use here.</span></span> <span data-ttu-id="e813c-107">Puede usar la ruta de acceso XSD para obtener información acerca de la profundidad de los nodos de esquema.</span><span class="sxs-lookup"><span data-stu-id="e813c-107">You can use the XSD path to get information about the depth of schema nodes.</span></span> <span data-ttu-id="e813c-108">Además, puede volver a usar esta ruta de acceso en otra página de cuadrícula para identificar la relación.</span><span class="sxs-lookup"><span data-stu-id="e813c-108">Also, you can reuse this path in another grid page to identify the relationship.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e813c-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="e813c-109">Prerequisites</span></span>  
 <span data-ttu-id="e813c-110">Estas instrucciones requieren que se está ejecutando el asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e813c-110">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-copy-the-xsd-path-xpath"></a><span data-ttu-id="e813c-111">Para copiar la ruta de acceso XSD (XPath)</span><span class="sxs-lookup"><span data-stu-id="e813c-111">To copy the XSD path (XPath)</span></span>  
  
1.  <span data-ttu-id="e813c-112">Haga clic en el nodo de esquema para el que desea que la ruta de acceso XSD y, a continuación, haga clic en **Copiar XPath**.</span><span class="sxs-lookup"><span data-stu-id="e813c-112">Right-click the schema node for which you want the XSD path, and then click **Copy XPath**.</span></span>  
  
2.  <span data-ttu-id="e813c-113">Abra un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="e813c-113">Open a text editor.</span></span> <span data-ttu-id="e813c-114">En el menú **Editar** , haga clic en **Pegar**.</span><span class="sxs-lookup"><span data-stu-id="e813c-114">On the **Edit** menu, click **Paste**.</span></span> <span data-ttu-id="e813c-115">Ahora puede ver la ruta de acceso XSD.</span><span class="sxs-lookup"><span data-stu-id="e813c-115">You can now see the XSD path.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e813c-116">Como alternativa, puede presionar CTRL+V para pegar la ruta de acceso en un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="e813c-116">Alternatively, you can press CTRL+V to paste the path in a text editor.</span></span>  
  
     <span data-ttu-id="e813c-117">El siguiente código muestra la ruta de acceso XSD para el nodo de esquema seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e813c-117">The code below displays the XSD path for the selected schema node.</span></span>  
  
    ```  
    /*[local-name()='<Schema>']/*[local-name()='Shipment']/*[local-name()='DataCollection']  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e813c-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e813c-118">See Also</span></span>  
 <span data-ttu-id="e813c-119">[Uso de características mejoradas en el asignador de BizTalk](../core/using-enhanced-features-in-biztalk-mapper.md) </span><span class="sxs-lookup"><span data-stu-id="e813c-119">[Using Enhanced Features in BizTalk Mapper](../core/using-enhanced-features-in-biztalk-mapper.md) </span></span>  
 <span data-ttu-id="e813c-120">[Cómo reemplazar esquemas](../core/how-to-replace-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="e813c-120">[How to Replace Schemas](../core/how-to-replace-schemas.md) </span></span>  
 <span data-ttu-id="e813c-121">[Cómo expandir y contraer los árboles de esquema](https://msdn.microsoft.com/library/ee253802(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="e813c-121">[How to Expand and Collapse the Schema Trees](https://msdn.microsoft.com/library/ee253802(v=bts.10).aspx)</span></span>