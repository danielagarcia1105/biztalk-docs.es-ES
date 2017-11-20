---
title: Documentos relacionados | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- queries [BAM], document references
- definition files [BAM], related documents
- Query Builder [BAM portal], viewing details
- document references [BAM]
- Query Builder [BAM portal], document references
- queries [BAM], viewing details
ms.assetid: 9c5f2175-fe7c-40ec-910d-1ac5c8142045
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30e21f2f102761dbfb332179c2754ea7ddea2d11
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="related-documents"></a><span data-ttu-id="1a4d6-102">Documentos relacionados</span><span class="sxs-lookup"><span data-stu-id="1a4d6-102">Related Documents</span></span>
<span data-ttu-id="1a4d6-103">El área de documentos relacionados de los detalles de los resultados de consulta muestra una lista de los documentos de referencia que están relacionados con la actividad.</span><span class="sxs-lookup"><span data-stu-id="1a4d6-103">The Related Documents area of the query results detail displays a list of documents that are reference documents that relate to the activity.</span></span> <span data-ttu-id="1a4d6-104">Los documentos pueden ser de cualquier tipo, incluso una imagen CAD, un archivo WAV o un pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="1a4d6-104">The documents can be of any type, including a CAD image, a .WAV file, or a purchase order.</span></span> <span data-ttu-id="1a4d6-105">Por ejemplo, una actividad de pedido de compra tendrá, por lo general, un pedido de compra como tipo de documento base.</span><span class="sxs-lookup"><span data-stu-id="1a4d6-105">For example, a Purchase Order activity will typically have a Purchase Order as a base document type.</span></span> <span data-ttu-id="1a4d6-106">La lista tendrá un vínculo al pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="1a4d6-106">The list will contain a link to the purchase order.</span></span>  
  
## <a name="adding-document-references"></a><span data-ttu-id="1a4d6-107">Agregar referencias de documento</span><span class="sxs-lookup"><span data-stu-id="1a4d6-107">Adding document references</span></span>  
 <span data-ttu-id="1a4d6-108">La lista de documentos relacionados se genera de una de las dos maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="1a4d6-108">The list of related documents is generated in one of two ways:</span></span>  
  
-   <span data-ttu-id="1a4d6-109">Cuando desarrolla su perfil de seguimiento, se incluye un nodo de URL de referencia de documento en el árbol de actividades y luego se asigna al documento físico desde el origen que contiene un puntero de referencia.</span><span class="sxs-lookup"><span data-stu-id="1a4d6-109">When you develop your tracking profile you include a Document Reference URL node in the activity tree and then map it from a source containing a reference pointer to the physical document.</span></span>  
  
-   <span data-ttu-id="1a4d6-110">Su programador de integraciones rellena mediante programación la lista llamando a su aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="1a4d6-110">Your integration developer programmatically populates the list by calling your custom application.</span></span>  
  
 <span data-ttu-id="1a4d6-111">Definir la referencia de documento mediante cualquiera de estos métodos agrega una fila en la \<activityname > _References tabla con la ubicación del documento.</span><span class="sxs-lookup"><span data-stu-id="1a4d6-111">Defining the document reference using either of these methods adds a row in the \<activityname>_References table with the document location.</span></span>  
  
 <span data-ttu-id="1a4d6-112">Si se ha realizado ninguna de estas tareas, el **documentos relacionados** área está en blanco.</span><span class="sxs-lookup"><span data-stu-id="1a4d6-112">If neither of these tasks has been performed, the **Related Document** area is blank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a4d6-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a4d6-113">See Also</span></span>  
 [<span data-ttu-id="1a4d6-114">Editor de perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="1a4d6-114">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)