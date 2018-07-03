---
title: Suma de comprobación Adler32 no válida encontrada | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa47a208-0f33-496e-8dbe-b50be9979bf2
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: acaa60e9d6f1bda4161832cb5ddb34c4e2e9ae93
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987269"
---
# <a name="invalid-adler32-checksum-encountered"></a>Suma de comprobación Adler32 no válida encontrada
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor AS2                                       |
|  Nombre simbólico  |                     InvalidAdler32ChecksumInCompressedMessageError                     |
|  Texto del mensaje   |                          Suma de comprobación Adler32 no válida encontrada                          |
  
## <a name="explanation"></a>Explicación  
 Este error hace referencia a la estructura ASN.1 de los datos comprimidos. El error indica al remitente de los datos comprimidos que ha estructurado incorrectamente los datos comprimidos o que se ha producido una manipulación (cambio sin autorización) del mensaje.  
  
## <a name="user-action"></a>Acción del usuario  
 El uso de **suma de comprobación Adler32 no válida encontrada** indica una alta probabilidad de manipulación. Compruebe si ve ha producido una manipulación **suma de comprobación Adler32 no válida encontrada**.