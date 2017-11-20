---
title: "Error: referencia raíz de esquema no existe | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.edit.error.rootRefNonExistent
ms.assetid: 84eaa5fb-f0b5-4a41-b935-e6d3ed734aba
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d391af259d7e91f73e1979cc9515469f96a4f0c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---schema-root-reference-nonexistent"></a><span data-ttu-id="17b99-102">Error: referencia raíz de esquema no existe</span><span class="sxs-lookup"><span data-stu-id="17b99-102">Error - Schema Root Reference Nonexistent</span></span>
<span data-ttu-id="17b99-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="17b99-103">**Error Code**</span></span>  
  
 <span data-ttu-id="17b99-104">BEC2006</span><span class="sxs-lookup"><span data-stu-id="17b99-104">BEC2006</span></span>  
  
 <span data-ttu-id="17b99-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="17b99-105">**Explanation**</span></span>  
  
 <span data-ttu-id="17b99-106">El **referencia raíz** propiedad de la **esquema** nodo hace referencia a un nodo raíz que no existe.</span><span class="sxs-lookup"><span data-stu-id="17b99-106">The **Root Reference** property of the **Schema** node is referencing a nonexistent root node.</span></span> <span data-ttu-id="17b99-107">El nodo raíz que se hace referencia puede han eliminado o cambiado el nombre después de haberse establecido como el **referencia raíz** valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="17b99-107">The referenced root node may have been deleted or renamed after it was set as the **Root Reference** property value.</span></span>  
  
 <span data-ttu-id="17b99-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="17b99-108">**User Action**</span></span>  
  
 <span data-ttu-id="17b99-109">Establecer el **referencia raíz** propiedad de la **esquema** nuevo nodo.</span><span class="sxs-lookup"><span data-stu-id="17b99-109">Set the **Root Reference** property of the **Schema** node again.</span></span> <span data-ttu-id="17b99-110">La lista desplegable de la propiedad incluye todas las elecciones válidas actuales para los nodos raíz.</span><span class="sxs-lookup"><span data-stu-id="17b99-110">The drop-down list for that property includes all currently valid choices for root nodes.</span></span>