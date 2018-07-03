---
title: 'Error al procesar el mensaje Edifact en el puerto de envío: no existen acuerdos de pares de calificador de identificador de receptor y no existe ninguna entidad con nombre | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11880c7c-6032-449b-b251-27fc2b2f0d72
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0b4e66ce918f59502125e77b7c19615cb281660
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009917"
---
# <a name="a-failure-occurred-in-processing-edifact-message-on-send-port-no-agreement-for-receiver-and-sender-identifier-qualifier-pairs-and-no-party-with-name"></a>Error al procesar el mensaje Edifact en el puerto de envío: no existen acuerdos de pares de calificador de identificador de receptor y no existe ninguna entidad con nombre
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                        |
| Versión del producto |                                                                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                    |
|    Identificador del evento     |                                                                                                -                                                                                                 |
|  Origen del evento   |                                                      EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                      |
|    Componente    |                                                                                            Motor EDI                                                                                            |
|  Nombre simbólico  |                                                                                                -                                                                                                 |
|  Texto del mensaje   | Error al procesar el mensaje Edifact en el puerto de envío {0}. No existen acuerdos de pares de calificador/identificador de receptor y remitente para {1}, {2}, {3} y {4}. No existe ninguna entidad con el nombre {5}. |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que BizTalk Server no pudo resolver la entidad para el intercambio EDIFACT porque no pudo hacer coincidir las propiedades del calificador e identificador del servidor promocionado y las propiedades del calificador e identificador del receptor promocionado con los valores correspondientes para una entidad.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el calificador e identificador del remitente (UNB2.1 y UNB2.2) y el calificador e identificador del receptor (UNB3.1 y UNB3.2) definidos en la página Definición de segmento UNB del cuadro de diálogo Propiedades de EDI coinciden con las propiedades promocionadas correspondientes en el contexto del intercambio.