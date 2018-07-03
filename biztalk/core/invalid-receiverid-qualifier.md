---
title: Calificador de Id. de destinatario no válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52d60f7e-6f16-424d-91b8-dc8181206249
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f4cf13bb338959ca4cd7d2d25a85749f0ff0171
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981821"
---
# <a name="invalid-receiverid-qualifier"></a>Calificador de Id. de destinatario no válido.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                      X12Ta1InvalidReceiverIdQualifierDescription                       |
|  Texto del mensaje   |                              Calificador de Id. de destinatario no válido.                              |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el calificador de destinatario en el campo ISA07 (para un intercambio X12) o el calificador de código de destinatario en el campo UNB3.2 (para un intercambio EDIFACT) no coincidía con un valor en la enumeración que establece el esquema de servicio (X12ServiceSchema o EdifactServiceSchema en BaseArtifacts.dll).  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el campo ISA07 o el campo UNB3.2 coincide con uno de los valores de la enumeración que establece el esquema de servicio. Vuelva a enviar el intercambio.