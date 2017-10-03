---
title: "Nodos de referencia de dirección URL de documento | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Document Reference URL nodes [Tracking Profile Editor]
- Tracking Profile Editor, node descriptions
- definition files [BAM], related documents
ms.assetid: 38c8ae50-ed56-451c-9549-db852d4770e5
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7939a7e74483b8df192530fd9da2deafeda0681
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="document-reference-url-nodes"></a><span data-ttu-id="b871b-102">Nodos de URL de referencia de documento</span><span class="sxs-lookup"><span data-stu-id="b871b-102">Document Reference URL Nodes</span></span>
<span data-ttu-id="b871b-103">Existen nodos de URL de referencia de documento en el archivo de definición de actividad que el programador importa desde el trabajador del conocimiento que creó el modelo de observación.</span><span class="sxs-lookup"><span data-stu-id="b871b-103">Document Reference URL nodes exist in the activity definition file that the developer imports from the knowledge worker created observation model.</span></span> <span data-ttu-id="b871b-104">Los nodos de URL de referencia de documento incluyen referencias a la ubicación que contiene un documento que está relacionado con esta actividad.</span><span class="sxs-lookup"><span data-stu-id="b871b-104">Document Reference URL nodes contain references to a location that contains a document that is related to this activity.</span></span> <span data-ttu-id="b871b-105">Puede ser cualquier tipo de documento, por ejemplo, una actividad que representa un flujo de trabajo de aprobación de pedido, y puede que la URL de referencia de documento señale al documento de pedido subyacente.</span><span class="sxs-lookup"><span data-stu-id="b871b-105">This can be any type of document, for example an activity that represents a purchase order approval work flow, the Document Reference URL might point to the underlying purchase order document.</span></span>  
  
## <a name="working-with-document-reference-url-nodes"></a><span data-ttu-id="b871b-106">Trabajar con nodos de URL de referencia de documento</span><span class="sxs-lookup"><span data-stu-id="b871b-106">Working with Document Reference URL nodes</span></span>  
 <span data-ttu-id="b871b-107">El origen de datos para la dirección URL de referencia de documento es normalmente la **MessageRefURL** propiedad del sistema BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="b871b-107">The data source for the Document Reference URL is typically the **MessageRefURL** BizTalk Server system property.</span></span> <span data-ttu-id="b871b-108">También puede utilizar esquemas personalizados que almacenen direcciones URL y que asignen la propiedad a la URL de referencia de documento desde el esquema personalizado.</span><span class="sxs-lookup"><span data-stu-id="b871b-108">You can also use custom schemas that store URLs and map the property to the Document Reference URL from the custom schema.</span></span>  
  
 <span data-ttu-id="b871b-109">Elementos a tener en cuenta de las direcciones URL de referencia de documento:</span><span class="sxs-lookup"><span data-stu-id="b871b-109">Items to note about Document Reference URLs:</span></span>  
  
-   <span data-ttu-id="b871b-110">Puede agregar una o más URL de referencia de documento, pero cada nodo debe tener un nombre único dentro de la actividad.</span><span class="sxs-lookup"><span data-stu-id="b871b-110">You can add one or more Document Reference URLs, but each node must have unique name within the activity.</span></span>  
  
-   <span data-ttu-id="b871b-111">El **MessageRefURL** propiedad necesario para rellenar un nodo Document Reference URL solo se rellena con un valor en el caso de los adaptadores de transporte WSS, archivo y FTP.</span><span class="sxs-lookup"><span data-stu-id="b871b-111">The **MessageRefURL** property needed to populate a Document Reference URL node is only populated with a value in the case of WSS, FILE, and FTP transport adapters.</span></span>  
  
-   <span data-ttu-id="b871b-112">Mientras que los usuarios empresariales finales pueden ver esta referencia en el portal de BAM, el propósito principal de la dirección URL de referencia es permitir que los desarrolladores de interfaz de usuario personalizada obtener acceso a información de documento asociada para que pueda presentar al usuario final.</span><span class="sxs-lookup"><span data-stu-id="b871b-112">While business end-users can view this reference in the BAM portal, the primary purpose of the reference URL is to allow custom user interface developers to gain access to associated document information so that they can present it to the end user.</span></span>  <span data-ttu-id="b871b-113">Para obtener más información acerca de cómo ver la referencia de documento en el portal de BAM, consulte [documentos relacionados](../core/related-documents.md).</span><span class="sxs-lookup"><span data-stu-id="b871b-113">For more information on viewing the document reference in the BAM portal, see [Related Documents](../core/related-documents.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b871b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b871b-114">See Also</span></span>  
 [<span data-ttu-id="b871b-115">Nodos de vista de actividad TPE</span><span class="sxs-lookup"><span data-stu-id="b871b-115">TPE Activity View Nodes</span></span>](../core/tpe-activity-view-nodes.md)