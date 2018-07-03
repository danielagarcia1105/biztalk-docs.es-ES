---
title: ASN.1 CMS ausentes o no es válido bytes de estructura comprimen durante la descompresión | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b73ce58-d827-4ffc-b2d7-78836298efc8
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 768fb1aa2ada6fb6c585e29db1f19cf04a1bd118
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991317"
---
# <a name="invalid-or-missing-trailing-asn1-cms-compressed-structure-bytes-during-decompression-processing"></a>ASN.1 CMS ausentes o no es válido bytes de estructura comprimen durante el proceso de descompresión
## <a name="details"></a>Detalles  
  
|                 |                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------|
|  Nombre del producto   |        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]        |
| Versión del producto |                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                    |
|    Identificador del evento     |                                                -                                                 |
|  Origen del evento   |      EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]      |
|    Componente    |                                            Motor AS2                                            |
|  Nombre simbólico  |                                                -                                                 |
|  Texto del mensaje   | ASN.1 CMS ausentes o no es válido bytes de estructura comprimen durante el proceso de descompresión |
  
## <a name="explanation"></a>Explicación  
 Este error hace referencia a la estructura ASN.1 de los datos comprimidos. El error indica al remitente de los datos comprimidos que ha estructurado incorrectamente los datos comprimidos o que se ha producido una manipulación (cambio sin autorización) del mensaje.  
  
## <a name="user-action"></a>Acción del usuario  
 Revise la estructura de los datos comprimidos y compruebe si se ha producido una manipulación del mensaje.