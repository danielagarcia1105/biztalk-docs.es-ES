---
title: El descodificador AS2 no pudo procesar la firma MDN no cumplía nuestra solicitud | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a42d344-fc28-4bc4-9328-46158f15a008
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a4d5cb5cd1825f5620ab39e4c770eb9818a5ade
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978879"
---
# <a name="the-as2-decoder-failed-processing-because-the-mdn-signing-did-not-match-our-request"></a>Error de procesamiento de descodificador AS2. La firma MDN no cumplía nuestra solicitud
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                           |
| Versión del producto |                                                                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                       |
|    Identificador del evento     |                                                                                                   -                                                                                                    |
|  Origen del evento   |                                                         EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                         |
|    Componente    |                                                                                               Motor AS2                                                                                               |
|  Nombre simbólico  |                                                                          AS2DecoderMdnSigningMismatchFailureDuringProcessing                                                                           |
|  Texto del mensaje   | Error de procesamiento de descodificador AS2. La firma MDN no cumplía nuestra solicitud.  Detalles del mensaje MDN son los siguientes: AS2-de: "{0}" AS2-para: "{1}" MessageID: "{2}" OriginalMessageID: "{3}" |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el MDN entrante porque el MDN estaba firmado y no se solicitaba la firma para él o que el MDN estaba sin firmar y se solicitaba la firma para él.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una de las siguientes acciones:  
  
1.  Cambie la solicitud de firma para que el MDN coincida con la solicitud. Para ello, abra la página Entidad como receptora del mensaje AS2 del cuadro de diálogo Propiedades de AS2 y, con la propiedad "Solicitar MDN" seleccionada, seleccione o desactive la propiedad "Solicitar MDN firmado".  
  
2.  Póngase en contacto con el receptor del mensaje AS2 original para resolver si los MDN deben firmarse o no.