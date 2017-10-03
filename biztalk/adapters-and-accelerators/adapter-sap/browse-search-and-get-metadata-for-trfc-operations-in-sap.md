---
title: Examinar, buscar y obtener los metadatos de las operaciones de tRFC en SAP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tRFC operations
- tRFC operations, browsing
- searching, tRFC operations
- tRFC operations, searching
- browsing, tRFC operations
ms.assetid: cf4a16d1-7bbf-4dea-b54d-b5315fbcd552
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5124eb4b3a56df70ec55d157ee80a394d6bff83d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="browse-search-and-get-metadata-for-trfc-operations-in-sap"></a>Examinar, buscar y obtener los metadatos de las operaciones de tRFC en SAP
tRFCs no son un artefacto independiente en un sistema SAP. Estos se clasifican en un nodo independiente por el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] porque sus características de los metadatos son diferentes de las solicitudes de cambio. Sin embargo, la experiencia de exploración, búsqueda y recuperación de metadatos para tRFCs son idéntico de los documentos RFC. Hacer referencia a [exploración, búsqueda y metadatos de get para las operaciones de RFC en SAP](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md) para obtener información sobre el uso de la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para examinar, buscar y recuperar metadatos para tRFCs desde un sistema SAP.  
  
 Tenga en cuenta que la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone una operación especial **RfcConfirmTransID** en el **TRFC** nodo. El adaptador SAP usa esta operación para confirmar las llamadas de tRFC realizadas al servidor SAP. Para obtener más información acerca de esta operación, vea [operaciones en tRFCs en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).  
  
## <a name="see-also"></a>Vea también  
 [Obtiene los metadatos para operaciones de SAP en Visual Studio](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)