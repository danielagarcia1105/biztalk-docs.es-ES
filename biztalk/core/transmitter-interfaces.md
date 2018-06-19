---
title: Interfaces del transmisor | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ffa6db3b-739e-438c-b410-8823a20eed82
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e922cd2526002306928b2eae3418185986ed741
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279724"
---
# <a name="transmitter-interfaces"></a>Interfaces del transmisor
Además de las interfaces de adaptador obligatorias, transmitir adaptadores (envío), necesita implementar uno **IBTTransmitter** si están sin lotes o **IBTBatchTransmitter** si se procesan por lotes.  
  
 En la siguiente ilustración se muestran las interfaces que deben implementar los adaptadores de envío que se procesan por lotes y los que no se procesan por lotes.  
  
 ![](../core/media/transmitterinterfaces.gif "TransmitterInterfaces")