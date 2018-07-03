---
title: Acuerdo encontrado para el protocolo está deshabilitado o expirado estado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b524f423-1325-495c-9499-33101f6388fc
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d7e4092b057b83caef252d63853ecf6791edbde
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014725"
---
# <a name="agreement-found-for-the-protocol-is-in-disabled-or-expired-state"></a>El acuerdo encontrado para el protocolo tiene el estado Deshabilitado o Expirado
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                     AgreementResolutionAgreementDiasbledOrExpired                      |
|  Texto del mensaje   |      Se encontró el contrato para el {0} protocolo está deshabilitado o expirado estado.      |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que BizTalk Server pudo resolver en un acuerdo, pero este último se encuentra en estado deshabilitado o expirado.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, habilite el acuerdo.