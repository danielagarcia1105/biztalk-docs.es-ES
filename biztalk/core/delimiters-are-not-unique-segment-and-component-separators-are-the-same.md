---
title: Los delimitadores no son únicos, los separadores de segmento y de componente son los mismos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 13c41899-02af-4678-a4ad-f3dc48c1fdfb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6068b13502b8893fd5065957b6dd73072236126
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983781"
---
# <a name="delimiters-are-not-unique-segment-and-component-separators-are-the-same"></a>Los delimitadores no son únicos. Los separadores de segmento y de componente coinciden.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                                           -                                            |
|  Texto del mensaje   |        Los delimitadores no son únicos. Los separadores de segmento y de componente coinciden.        |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de envío EDI no pudo procesar un intercambio saliente porque el terminador de segmento o el separador de componentes eran el mismo valor. En un intercambio X12, el terminador de segmento es el carácter de la última posición de carácter del segmento ISA y el separador de componente es el carácter del campo ISA16. En un intercambio EDIFACT, el terminador de segmento es el carácter del campo UNA6 y el separador de componente es el carácter del campo UNA1. Dos separadores con el mismo valor pueden tener lugar (pero provocarán una condición de error) en un escenario de lote conservado o si se recibe un intercambio mediante una transmisión de atravesar y posteriormente el puerto de envío lo recoge como archivo XML en el cuadro de mensajes.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, cambie el valor del terminador de segmento o del separador de componentes en el intercambio y, a continuación, vuelva a enviar el intercambio.