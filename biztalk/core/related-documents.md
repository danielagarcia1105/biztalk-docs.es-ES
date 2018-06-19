---
title: Documentos relacionados | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- queries [BAM], document references
- definition files [BAM], related documents
- Query Builder [BAM portal], viewing details
- document references [BAM]
- Query Builder [BAM portal], document references
- queries [BAM], viewing details
ms.assetid: 9c5f2175-fe7c-40ec-910d-1ac5c8142045
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b87f0d31010a8bf80e09c59f05f2f9302a510e2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970074"
---
# <a name="related-documents"></a><span data-ttu-id="b79d5-102">Documentos relacionados</span><span class="sxs-lookup"><span data-stu-id="b79d5-102">Related Documents</span></span>
<span data-ttu-id="b79d5-103">El área de documentos relacionados de los detalles de los resultados de consulta muestra una lista de los documentos de referencia que están relacionados con la actividad.</span><span class="sxs-lookup"><span data-stu-id="b79d5-103">The Related Documents area of the query results detail displays a list of documents that are reference documents that relate to the activity.</span></span> <span data-ttu-id="b79d5-104">Los documentos pueden ser de cualquier tipo, incluso una imagen CAD, un archivo WAV o un pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="b79d5-104">The documents can be of any type, including a CAD image, a .WAV file, or a purchase order.</span></span> <span data-ttu-id="b79d5-105">Por ejemplo, una actividad de pedido de compra tendrá, por lo general, un pedido de compra como tipo de documento base.</span><span class="sxs-lookup"><span data-stu-id="b79d5-105">For example, a Purchase Order activity will typically have a Purchase Order as a base document type.</span></span> <span data-ttu-id="b79d5-106">La lista tendrá un vínculo al pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="b79d5-106">The list will contain a link to the purchase order.</span></span>  
  
## <a name="adding-document-references"></a><span data-ttu-id="b79d5-107">Agregar referencias de documento</span><span class="sxs-lookup"><span data-stu-id="b79d5-107">Adding document references</span></span>  
 <span data-ttu-id="b79d5-108">La lista de documentos relacionados se genera de una de las dos maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="b79d5-108">The list of related documents is generated in one of two ways:</span></span>  
  
-   <span data-ttu-id="b79d5-109">Cuando desarrolla su perfil de seguimiento, se incluye un nodo de URL de referencia de documento en el árbol de actividades y luego se asigna al documento físico desde el origen que contiene un puntero de referencia.</span><span class="sxs-lookup"><span data-stu-id="b79d5-109">When you develop your tracking profile you include a Document Reference URL node in the activity tree and then map it from a source containing a reference pointer to the physical document.</span></span>  
  
-   <span data-ttu-id="b79d5-110">Su programador de integraciones rellena mediante programación la lista llamando a su aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="b79d5-110">Your integration developer programmatically populates the list by calling your custom application.</span></span>  
  
 <span data-ttu-id="b79d5-111">Definir la referencia de documento mediante cualquiera de estos métodos agrega una fila en la \<activityname\>tabla _References con la ubicación del documento.</span><span class="sxs-lookup"><span data-stu-id="b79d5-111">Defining the document reference using either of these methods adds a row in the \<activityname\>_References table with the document location.</span></span>  
  
 <span data-ttu-id="b79d5-112">Si se ha realizado ninguna de estas tareas, el **documentos relacionados** área está en blanco.</span><span class="sxs-lookup"><span data-stu-id="b79d5-112">If neither of these tasks has been performed, the **Related Document** area is blank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b79d5-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b79d5-113">See Also</span></span>  
 [<span data-ttu-id="b79d5-114">Editor de perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="b79d5-114">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)