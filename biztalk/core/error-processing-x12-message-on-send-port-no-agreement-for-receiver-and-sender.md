---
title: 'Se ha producido un error en el procesamiento de X12 mensaje en el puerto de envío: no existen acuerdos de pares de calificador de identificador de receptor y no existe ninguna entidad con nombre | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fdf445e8-51a3-44fb-aa71-e0b0ab9c428f
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30d75c1db7b55d1955eec398d6c8d792b11ca648
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005709"
---
# <a name="a-failure-occurred-in-processing-x12-message-on-send-port-no-agreement-for-receiver-and-sender-identifier-qualifier-pairs-and-no-party-with-name"></a>Se ha producido un error en el procesamiento de X12 mensaje en el puerto de envío: no existen acuerdos de pares de calificador de identificador de receptor y no existe ninguna entidad con nombre
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                      |
| Versión del producto |                                                                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                  |
|    Identificador del evento     |                                                                                              -                                                                                               |
|  Origen del evento   |                                                    EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                    |
|    Componente    |                                                                                          Motor EDI                                                                                          |
|  Nombre simbólico  |                                                                                              -                                                                                               |
|  Texto del mensaje   | Se ha producido un error en el procesamiento de X12 mensaje en el puerto de envío {0}. No existen acuerdos de pares de calificador/identificador de receptor y remitente para {1}, {2}, {3} y {4}. No existe ninguna entidad con el nombre {5}. |
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que BizTalk Server no pudo resolver la entidad para el intercambio EDIFACT porque no pudo hacer coincidir las propiedades del calificador e identificador del servidor promocionado y las propiedades del calificador e identificador del receptor promocionado con los valores correspondientes para una entidad.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el calificador e identificador del remitente (ISA5 e ISA6) y el calificador e identificador del receptor (ISA7 e ISA8) definidos en la página Definición de segmento ISA del cuadro de diálogo Propiedades de EDI coinciden con las propiedades promocionadas correspondientes en el contexto del intercambio.