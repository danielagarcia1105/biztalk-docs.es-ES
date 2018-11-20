---
title: Conjunto de delimitadores no válido porque al menos uno de los delimitadores está fuera del intervalo permitido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1286559-765b-4728-945d-cf3386e1ba06
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebda7e3ebfe2adc0084b672a2f66ed1ad639c943
ms.sourcegitcommit: c3070a7a3f332857357f056dc632829b43869c17
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2018
ms.locfileid: "51630369"
---
# <a name="invalid-delimiter-set-because-at-least-one-of-the-delimiters-is-outside-the-allowed-range"></a>Grupo de delimitadores no válido porque al menos uno de los delimitadores está fuera del intervalo permitido
## <a name="details"></a>Detalles  
  
|                 |                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]           |
| Versión del producto |                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                       |
|    Identificador del evento     |                                                   -                                                    |
|  Origen del evento   |         EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]         |
|    Componente    |                                               Motor EDI                                               |
|  Nombre simbólico  |                                          DelimiterOutOfRange                                           |
|  Texto del mensaje   | Conjunto de delimitadores no válido {0}, al menos uno de los delimitadores está fuera del intervalo permitido de 0 a 127 |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante, pues uno o varios separadores del intercambio estaban fuera del intervalo de valores del conjunto de caracteres ASCII.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que cada separador del intercambio se encuentra en el conjunto de caracteres ASCII y vuelva a enviar el mensaje.
