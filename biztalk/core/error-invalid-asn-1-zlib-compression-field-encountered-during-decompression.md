---
title: "Campo de compresión ASN.1 ZLib no válido detectado durante el proceso de descompresión | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b7caf047-badd-49e8-b955-554e5ec7511f
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a347f63325e1c93497d178ffcc486ff8bd1c4f6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-asn1-zlib-compression-field-encountered-during-decompression-processing"></a>Campo de compresión ASN.1 ZLib no válido detectado durante el proceso de descompresión
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor AS2|  
|Nombre simbólico|InvalidOptionalZLibFieldEncountered|  
|Texto del mensaje|Campo de compresión ASN.1 ZLib no válido detectado durante el proceso de descompresión|  
  
## <a name="explanation"></a>Explicación  
 Este error hace referencia a la estructura ASN.1 de los datos comprimidos. El error indica al remitente de los datos comprimidos que ha estructurado incorrectamente los datos comprimidos o que se ha producido una manipulación (cambio sin autorización) del mensaje.  
  
## <a name="user-action"></a>Acción del usuario  
 Revise la estructura de los datos comprimidos y compruebe si hay evidencia de manipulación.