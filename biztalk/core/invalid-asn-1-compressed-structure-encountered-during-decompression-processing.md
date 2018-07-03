---
title: ASN.1 comprimido no válido detectado durante el procesamiento de descompresión | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4e5ebbd6-249a-4746-8ee6-cfb1f52ecc94
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07d1e44e38665a6a643131545afb660945a9f07e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969077"
---
# <a name="invalid-asn1-compressed-structure-encountered-during-decompression-processing"></a>ASN.1 comprimido no válido detectado durante el proceso de descompresión
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor AS2                                       |
|  Nombre simbólico  |                       InvalidASN1CompressedStructureEncountered                        |
|  Texto del mensaje   | Encabezado comprimido ASN.1 ausente o no válido detectado durante el proceso de descompresión |
  
## <a name="explanation"></a>Explicación  
 Este error hace referencia a la estructura ASN.1 de los datos comprimidos. El error indica al remitente de los datos comprimidos que ha estructurado incorrectamente los datos comprimidos o que se ha producido una manipulación (cambio sin autorización) del mensaje.  
  
## <a name="user-action"></a>Acción del usuario  
 Revise la estructura de los datos comprimidos y compruebe si se ha producido una manipulación del mensaje.