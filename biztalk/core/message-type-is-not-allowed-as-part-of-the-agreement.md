---
title: No se permite el tipo de mensaje como parte del acuerdo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 829f8230-33b8-4b5f-a56a-d0c1d3a17271
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1ed9c1e4891a3365484b60e51848a998f2d152b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982373"
---
# <a name="message-type-is-not-allowed-as-part-of-the-agreement"></a>No se permite el tipo de mensaje como parte del acuerdo
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                          TransactionSetNotAllowedDescription                           |
|  Texto del mensaje   |               Tipo de mensaje {0} no se permite como parte del acuerdo.                |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que BizTalk Server no pudo procesar el documento porque el tipo de mensaje del documento no se permite como parte del acuerdo.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, mire los tipos de mensaje permitidos y no permitidos como parte del acuerdo.