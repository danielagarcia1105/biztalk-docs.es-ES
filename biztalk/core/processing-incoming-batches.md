---
title: Procesamiento por lotes entrantes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98f47903-933a-4bde-b320-f7689c3d8366
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca3781d9b7c1ed2190a8334f272c04d304669ace
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="processing-incoming-batches"></a>Procesar lotes entrantes
Cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe un intercambio EDI de procesamiento por lotes, puede dividir el intercambio en conjuntos de transacciones, procesando cada una de forma independiente, o bien puede conservar el intercambio procesando los conjuntos de transacciones como grupo.  
  
 Determinar el procesamiento por lotes en el **configuración de Host Local** página de las fichas de acuerdo unidireccional en el **propiedades del acuerdo de** cuadro de diálogo para acuerdos x X12 y EDIFACT. Si conserva el intercambio, tiene la opción de suspender el intercambio o los conjuntos de transacciones si se produce un error.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Dividir un intercambio EDI por lotes](../core/splitting-a-batched-edi-interchange.md)  
  
-   [Dividir subdocumentos HIPAA](../core/splitting-hipaa-subdocuments.md)  
  
-   [Conservar un recibido el intercambio EDI por lotes](../core/preserving-a-received-batched-edi-interchange.md)