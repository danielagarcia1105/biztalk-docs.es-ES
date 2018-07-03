---
title: Id. de remitente no válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be8055ab-8aba-49ac-ad33-fb33d4ff3e8b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7517adcd214f789c8af37d4abce2478e6da20507
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976541"
---
# <a name="invalid-senderid"></a>Id. de remitente no válido.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                            X12Ta1InvalidSenderIdDescription                            |
|  Texto del mensaje   |                                    Id. de remitente no válido.                                    |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el identificador de remitente en el campo ISA06 o la identificación de remitente en el campo UNB2.1 no se ajustaba al tipo de datos y al número de dígitos que establece el esquema de servicio (X12ServiceSchema o EdifactServiceSchema en BaseArtifacts.dll).  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el campo ISA06 sea del tipo de datos X12_AN y tenga una longitud de 15 caracteres (con o sin espacios finales) o de que el campo UNB2.1 sea del tipo de datos EDIFACT_AN y tenga entre 1 y 35 caracteres. Vuelva a enviar el intercambio.