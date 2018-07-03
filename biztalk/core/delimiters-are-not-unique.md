---
title: Los delimitadores no son únicos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c37cc55-8923-4124-9004-91ee5093df9c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d724533fb89d3f4d43654aadaf43094adb80e06
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966747"
---
# <a name="delimiters-are-not-unique"></a>Los delimitadores no son únicos
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                                           -                                            |
|  Texto del mensaje   |                               Los delimitadores no son únicos                                |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de envío EDI no pudo procesar un intercambio saliente porque coincidían dos o más de los separadores identificados en el intercambio y usados para separar facetas del intercambio. Los separadores se identifican en el segmento ISA de un intercambio X12 y en el segmento UNA de un intercambio EDIFACT. Dos o más separadores con el mismo valor pueden tener lugar en un escenario de lote conservado o si se recibe un intercambio mediante una transmisión de atravesar y posteriormente el puerto de envío lo recoge como archivo XML en el cuadro de mensajes. Esta condición de error provocará un error en el procesamiento del intercambio.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, identifique los separadores del intercambio que tengan el mismo valor y cambie el valor de uno de los separadores.