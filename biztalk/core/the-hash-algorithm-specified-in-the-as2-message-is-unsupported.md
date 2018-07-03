---
title: No se admite el algoritmo hash especificado en el mensaje AS2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1b292238-f964-4275-bbfa-e21c9150abf7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c3c46f65fb71ef810fc4e657df01e0065757cae
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008597"
---
# <a name="the-hash-algorithm-specified-in-the-as2-message-is-unsupported"></a>El algoritmo de hash especificado en el mensaje AS2 no es compatible
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor AS2                                       |
|  Nombre simbólico  |                            UnsupportedAS2HashAlgorithmError                            |
|  Texto del mensaje   |            El algoritmo de hash especificado en el mensaje AS2 no es compatible.             |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo generar el MDN según se ha especificado porque el algoritmo hash MIC especificado en el encabezado signed-receipt-micalg del mensaje AS2 recibido no es un valor válido.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, haga que el remitente del mensaje cambie el algoritmo a MD5 o SHA1 y reenvíe el mensaje.