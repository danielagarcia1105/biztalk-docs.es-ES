---
title: AS2 no válido-al encabezado recibido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 56cd16b3-511b-4716-8806-817f174f0b0e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0bc9fd8043205920f69aec2ca7efbfcc9478724
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010357"
---
# <a name="invalid-as2-to-header-received"></a>Encabezado AS2-To recibido
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor AS2                                       |
|  Nombre simbólico  |                          InvalidAS2ToNameHeaderReceivedError                           |
|  Texto del mensaje   |                      Encabezado AS2-To recibido.  Valor: {0}                       |
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que la canalización de recepción no pudo procesar el intercambio entrante porque el valor del encabezado AS2-To en el mensaje no se ajustaba a las especificaciones de AS2 RFC 4130.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el valor del encabezado AS2-To del mensaje se ajusta a las especificaciones de la sección 6.2 de AS2 RFC 4130.