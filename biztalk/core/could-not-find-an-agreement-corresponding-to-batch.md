---
title: No se pudo encontrar ningún acuerdo correspondiente al lote | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d1c0480-9a6f-481a-9143-e5a55707c3b5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b51fabd7aaf01d751f1a5ecff3c3a4e773e0b7b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978381"
---
# <a name="could-not-find-an-agreement-corresponding-to-batch"></a>No se encuentra ningún acuerdo correspondiente al lote
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                               AgreementNotFoundForBatch                                |
|  Texto del mensaje   |                No se pudo encontrar ningún acuerdo correspondiente al lote {0}.                 |
  
## <a name="explanation"></a>Explicación  
 Este evento de error indica que BizTalk Server no pudo encontrar un lote correspondiente a este identificador al tratar de iniciar o detener un lote o procesar un mensaje por lotes.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que esté presente un lote con el identificador dado en las propiedades del acuerdo contenedor.