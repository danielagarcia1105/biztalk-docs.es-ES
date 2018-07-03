---
title: Disposition-Notification-Option no es válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1b807a8-eec9-45a5-83cc-075c91b4bc9e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50831c03bc7dc0412cdb6fcd40ca981e87cf43f3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023194"
---
# <a name="disposition-notification-option-is-invalid"></a>Disposition-Notification-Option no es válido
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor AS2                                       |
|  Nombre simbólico  |                                           -                                            |
|  Texto del mensaje   |              Valor disposition-Notification-Option: "{0}" no es válido. {1}              |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción AS2 no pudo generar el MDN debido a que el encabezado Disposition-Notification-Option no era válido.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el encabezado Disposition-Notification-Option en el mensaje AS2 se ajusta a la sintaxis descrita en RFC 4130, "MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2"). Asegúrese de que el encabezado Signed-Receipt-Protocol se ha establecido en "optional" o "pcks7-signature" y que el encabezado Signed-Receipt-MICAlg se ha establecido en "optional", "MD5" o "SHA1". (Los dos encabezados se incluyen en el encabezado Disposition-Notification-Option).