---
title: Terminador de segmento no válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 508dac21-4731-439d-bf4a-a50858f1ffa0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0249c16bf495f9103759ec4eba9a9c6776b87ca2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001829"
---
# <a name="invalid-segment-terminator"></a>Terminador de segmento no válido.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                       X12Ta1InvalidSegmentTerminatorDescription                        |
|  Texto del mensaje   |                               Terminador de segmento no válido.                               |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el valor del terminador de segmento del intercambio no estaba limitado a los caracteres del juego de caracteres ASCII. En X12, el terminador de segmento se define como el último carácter del segmento ISA. En EDIFACT, el terminador de segmento es el campo UNA6.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el terminador de segmento (el último carácter del segmento ISA de un intercambio X12 o el campo UNA6 en un intercambio EDIFACT) está limitado a los caracteres del juego de caracteres ASCII. Vuelva a enviar el intercambio.