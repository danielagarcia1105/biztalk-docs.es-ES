---
title: Examinar, buscar y obtener los metadatos de las operaciones de tRFC en SAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tRFC operations
- tRFC operations, browsing
- searching, tRFC operations
- tRFC operations, searching
- browsing, tRFC operations
ms.assetid: cf4a16d1-7bbf-4dea-b54d-b5315fbcd552
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5124eb4b3a56df70ec55d157ee80a394d6bff83d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217172"
---
# <a name="browse-search-and-get-metadata-for-trfc-operations-in-sap"></a><span data-ttu-id="8a334-102">Examinar, buscar y obtener los metadatos de las operaciones de tRFC en SAP</span><span class="sxs-lookup"><span data-stu-id="8a334-102">Browse, search, and get metadata for tRFC operations in SAP</span></span>
<span data-ttu-id="8a334-103">tRFCs no son un artefacto independiente en un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="8a334-103">tRFCs are not a separate artifact in an SAP system.</span></span> <span data-ttu-id="8a334-104">Estos se clasifican en un nodo independiente por el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] porque sus características de los metadatos son diferentes de las solicitudes de cambio.</span><span class="sxs-lookup"><span data-stu-id="8a334-104">These are categorized under a separate node by the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] because their metadata characteristics are different from that of RFCs.</span></span> <span data-ttu-id="8a334-105">Sin embargo, la experiencia de exploración, búsqueda y recuperación de metadatos para tRFCs son idéntico de los documentos RFC.</span><span class="sxs-lookup"><span data-stu-id="8a334-105">However, the experience of browsing, searching, and retrieving metadata for tRFCs is identical to that of the RFCs.</span></span> <span data-ttu-id="8a334-106">Hacer referencia a [exploración, búsqueda y metadatos de get para las operaciones de RFC en SAP](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md) para obtener información sobre el uso de la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para examinar, buscar y recuperar metadatos para tRFCs desde un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="8a334-106">Refer to [Browse, search, and get metadata for RFC operations in SAP](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md) for information about using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to browse, search, and retrieve metadata for tRFCs from an SAP system.</span></span>  
  
 <span data-ttu-id="8a334-107">Tenga en cuenta que la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone una operación especial **RfcConfirmTransID** en el **TRFC** nodo.</span><span class="sxs-lookup"><span data-stu-id="8a334-107">Note that the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces a special operation **RfcConfirmTransID** under the **TRFC** node.</span></span> <span data-ttu-id="8a334-108">El adaptador SAP usa esta operación para confirmar las llamadas de tRFC realizadas al servidor SAP.</span><span class="sxs-lookup"><span data-stu-id="8a334-108">The SAP adapter uses this operation to commit tRFC calls made to the SAP server.</span></span> <span data-ttu-id="8a334-109">Para obtener más información acerca de esta operación, vea [operaciones en tRFCs en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).</span><span class="sxs-lookup"><span data-stu-id="8a334-109">For more information about this operation, see [Operations on tRFCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a334-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a334-110">See Also</span></span>  
 [<span data-ttu-id="8a334-111">Obtiene los metadatos para operaciones de SAP en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8a334-111">Get Metadata for SAP Operations in Visual Studio</span></span>](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)