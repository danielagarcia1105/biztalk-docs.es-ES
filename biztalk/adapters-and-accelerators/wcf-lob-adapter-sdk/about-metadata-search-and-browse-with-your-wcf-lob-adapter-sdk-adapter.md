---
title: Acerca de la búsqueda de metadatos y examinar con el adaptador de SDK de adaptador LOB de WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1dc529ba-86ce-4f83-a4f8-73f5765308e2
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 215199bec64562a302c9550bc5526a8758e4843a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983437"
---
# <a name="about-metadata-search-and-browse-with-your-wcf-lob-adapter-sdk-adapter"></a><span data-ttu-id="90142-102">Acerca de la búsqueda de metadatos y examinar con el adaptador de SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="90142-102">About metadata search and browse with your WCF LOB Adapter SDK adapter</span></span>
<span data-ttu-id="90142-103">A diferencia de un servicio estático creado mediante el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], adaptadores generada mediante el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] puede proporcionar información dinámica sobre los tipos y las operaciones disponibles en un sistema de línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="90142-103">Unlike a static service built using the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], adapters built using the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] can provide dynamic information about the types and operations available in a line-of-business system.</span></span> <span data-ttu-id="90142-104">Los desarrolladores pueden admitir las operaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="90142-104">Developers can support the following operations:</span></span>  
  
- <span data-ttu-id="90142-105">**Exploración de metadatos**, permitir que el usuario revisar una lista de todas las operaciones y los tipos disponibles en el sistema de línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="90142-105">**Metadata Browse**, enabling the user to review a list of all operations and types available in the line-of-business system.</span></span>  
  
- <span data-ttu-id="90142-106">**Búsqueda de metadatos**, que permite al usuario buscar operaciones con distintos criterios que a menudo se basa en la línea del sistema de negocio.</span><span class="sxs-lookup"><span data-stu-id="90142-106">**Metadata Search**, enabling the user to search for operations using different criteria often based on the line of business system.</span></span> <span data-ttu-id="90142-107">Por ejemplo, el usuario podría buscar en "* CUST\*" para recuperar todas las operaciones que tienen "CUST" en cualquier lugar en su nombre.</span><span class="sxs-lookup"><span data-stu-id="90142-107">For example, the user could search on "*CUST\*" to retrieve all operations that have "CUST" anywhere in their name.</span></span>  
  
- <span data-ttu-id="90142-108">**Recuperación de metadatos**, que proporciona información acerca de una lista específica de los tipos de datos o las operaciones compatibles.</span><span class="sxs-lookup"><span data-stu-id="90142-108">**Metadata Retrieval**, which supplies information about a specific list of supported operations or data types.</span></span>  
  
  <span data-ttu-id="90142-109">Si la línea del sistema de negocio contiene cientos o miles de operaciones, que proporciona la capacidad de buscar para operaciones específicas o ciertos grupos de información puede mejorar la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="90142-109">If the line of business system contains hundreds or thousands of operations, providing the ability to search for specific operations or browse certain groups of information can enhance the user experience.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90142-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="90142-110">See Also</span></span>  
 [<span data-ttu-id="90142-111">Planear y diseñar el adaptador mediante el SDK de adaptador LOB de WCF </span><span class="sxs-lookup"><span data-stu-id="90142-111">Plan and Design your Adapter using the WCF LOB Adapter SDK </span></span>](plan-and-design-your-adapter-using-the-wcf-lob-adapter-sdk.md)