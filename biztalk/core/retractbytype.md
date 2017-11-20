---
title: RetractByType | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RetractByType function [Business Rules Engine], TypedXMLDocument
- RetractByType function [Business Rules Engine]
- RetractByType function [Business Rules Engine], .NET objects
- RetractByType function [Business Rules Engine], TypedData table
- RetractByType function [Business Rules Engine], DataConnection
- .NET objects
ms.assetid: e8867553-ee3c-46be-84cd-d5373eaf3337
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da8cd4581007ad2bd93ed66ebce4f5de6378280c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="retractbytype"></a><span data-ttu-id="15c9d-102">RetractByType</span><span class="sxs-lookup"><span data-stu-id="15c9d-102">RetractByType</span></span>
<span data-ttu-id="15c9d-103">El **RetractByType** función extrae todas las instancias de un tipo especificado en la memoria de trabajo, mientras que la **Retract**función retira solo elementos específicos de un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="15c9d-103">The **RetractByType** function retracts all instances of a specified type in the working memory, whereas the **Retract**function retracts only specific items of a certain type.</span></span> <span data-ttu-id="15c9d-104">Los siguientes párrafos describen cómo **RetractByType** función funciona con entidades de tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="15c9d-104">The following paragraphs describe how the **RetractByType** function works with entities of different types.</span></span>  
  
## <a name="net-objects"></a><span data-ttu-id="15c9d-105">Objetos .NET</span><span class="sxs-lookup"><span data-stu-id="15c9d-105">.NET Objects</span></span>  
 <span data-ttu-id="15c9d-106">Todos los objetos de una clase determinada se retiran de la memoria de trabajo.</span><span class="sxs-lookup"><span data-stu-id="15c9d-106">All objects for a given class type are retracted from working memory.</span></span> <span data-ttu-id="15c9d-107">Basta con arrastrar la clase desde el panel de datos de las clases de .NET en el **RetractByType** (función).</span><span class="sxs-lookup"><span data-stu-id="15c9d-107">You simply drag the class from the .NET Classes fact pane into the **RetractByType** function.</span></span>  
  
## <a name="typedxmldocument"></a><span data-ttu-id="15c9d-108">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="15c9d-108">TypedXmlDocument</span></span>  
 <span data-ttu-id="15c9d-109">Se retiran todas las instancias.</span><span class="sxs-lookup"><span data-stu-id="15c9d-109">All instances are retracted.</span></span> <span data-ttu-id="15c9d-110">Esto significa que todos los **TypedXmlDocument**s con el mismo **DocumentType.Selector** se retiran.</span><span class="sxs-lookup"><span data-stu-id="15c9d-110">This means that all **TypedXmlDocument**s with the same **DocumentType.Selector** are retracted.</span></span> <span data-ttu-id="15c9d-111">Debe arrastrar el nodo adecuado desde el panel de datos de esquemas XML en la **RetractByType** (función).</span><span class="sxs-lookup"><span data-stu-id="15c9d-111">You should drag the appropriate node from the XML Schemas fact pane into the **RetractByType** function.</span></span> <span data-ttu-id="15c9d-112">Coherente con la **Retract** funcione, si lleva a cabo una **RetractByType** en el nodo raíz del documento, no solo serán todos **TypedXmlDocuments** impone con ese  **DocumentType** se retira, pero todos los secundarios **TypedXmlDocuments** (**XmlNode**s en la jerarquía de árbol) asociadas con esos primario **TypedXmlDocuments**  también se puede retirarse.</span><span class="sxs-lookup"><span data-stu-id="15c9d-112">Consistent with the **Retract** function, if you perform a **RetractByType** on the document root node, not only will all **TypedXmlDocuments** asserted with that **DocumentType** be retracted, but all child **TypedXmlDocuments** (**XmlNode**s in the tree hierarchy) associated with those parent **TypedXmlDocuments** will also be retracted.</span></span>  
  
## <a name="typeddatatable-and-dataconnection"></a><span data-ttu-id="15c9d-113">TypedDataTable y DataConnection</span><span class="sxs-lookup"><span data-stu-id="15c9d-113">TypedDataTable and DataConnection</span></span>  
 <span data-ttu-id="15c9d-114">**Retirar** y **RetractByType** son equivalentes a ambos **TypedDataTable** y **DataConnection**.</span><span class="sxs-lookup"><span data-stu-id="15c9d-114">**Retract** and **RetractByType** are equivalent for both **TypedDataTable** and **DataConnection**.</span></span> <span data-ttu-id="15c9d-115">Dado que **DataSetName.DataTableName** es un identificador único para ambos tipos, hay sólo una instancia del motor de en cualquier momento en el tiempo.</span><span class="sxs-lookup"><span data-stu-id="15c9d-115">Because **DataSetName.DataTableName** is a unique identifier for both types, there is only one instance in the engine at any point in time.</span></span> <span data-ttu-id="15c9d-116">Al igual que con **Retract**, arrastre la tabla en la **RetractByType** (función).</span><span class="sxs-lookup"><span data-stu-id="15c9d-116">As with **Retract**, you drag the table into the **RetractByType** function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15c9d-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="15c9d-117">See Also</span></span>  
 [<span data-ttu-id="15c9d-118">Funciones de Control del motor</span><span class="sxs-lookup"><span data-stu-id="15c9d-118">Engine Control Functions</span></span>](../core/engine-control-functions.md)