---
title: Los delimitadores no son únicos, separadores de campo y de segmento son los mismos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1441434a-e969-4803-8e44-c7738d9b23ed
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff43a9b86fc39589cd513c82c5d9bed9055f5902
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969533"
---
# <a name="delimiters-are-not-unique-field-and-segment-separator-are-the-same"></a>Los delimitadores no son únicos. Los separadores de campo y de segmento coinciden.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                                           -                                            |
|  Texto del mensaje   |          Los delimitadores no son únicos. Los separadores de campo y de segmento coinciden.           |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de envío EDI no pudo procesar un intercambio saliente porque el elemento de datos y los separadores de segmentos tenían el mismo valor. En un intercambio X12, el separador de elemento de datos es el carácter situado en la cuarta posición de carácter del segmento ISA y el terminador de segmento es el carácter de la última posición de carácter del segmento ISA. En un intercambio EDIFACT, el separador del elemento de datos es el carácter del campo UNA2 y el terminador de segmento es el carácter del campo UNA6. Dos separadores con el mismo valor pueden tener lugar (pero provocarán una condición de error) en un escenario de lote conservado o si se recibe un intercambio mediante una transmisión de atravesar y posteriormente el puerto de envío lo recoge como archivo XML en el cuadro de mensajes.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, cambie el valor del elemento de datos o del separador de segmento en el intercambio y, a continuación, vuelva a enviar el intercambio.