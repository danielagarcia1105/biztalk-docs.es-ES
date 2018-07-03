---
title: Ausente o no válido ASN.1 OID de datos comprimidos encontrado durante el proceso de descompresión | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0171daa8-289a-43f1-8cbf-d779ef9dc2ea
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2abc1c0f1331d95ebd331f8f60a947bcca86496
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993581"
---
# <a name="invalid-or-missing-asn1-compressed-data-oid-encountered-during-decompression-processing"></a>OID de datos comprimidos ASN.1 ausente o no válido detectado durante el proceso de descompresión
## <a name="details"></a>Detalles  
  
|                 |                                                                                          |
|-----------------|------------------------------------------------------------------------------------------|
|  Nombre del producto   |    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]    |
| Versión del producto |                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                |
|    Identificador del evento     |                                            -                                             |
|  Origen del evento   |  EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  |
|    Componente    |                                        Motor AS2                                        |
|  Nombre simbólico  |                                            -                                             |
|  Texto del mensaje   | OID de datos comprimidos ASN.1 ausente o no válido detectado durante el proceso de descompresión |
  
## <a name="explanation"></a>Explicación  
 Este error hace referencia a la estructura ASN.1 de los datos comprimidos. El error indica al remitente de los datos comprimidos que ha estructurado incorrectamente los datos comprimidos o que se ha producido una manipulación (cambio sin autorización) del mensaje.  
  
## <a name="user-action"></a>Acción del usuario  
 Revise la estructura de los datos comprimidos y compruebe si se ha producido una manipulación del mensaje.