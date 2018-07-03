---
title: El acuerdo asociado con el identificador de lote no está habilitado o ha expirado. No puede continuar el procesamiento por lotes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d92cb07-7646-42b3-90a8-18acbcd145cd
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ace947d1c05774882b1e8f78f7b093f0795ba919
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018300"
---
# <a name="the-agreement-associated-with-batchid-is-not-enabled-or-has-expired-batching-cannot-continue"></a>El acuerdo asociado con el identificador de lote no está habilitado o ha expirado. El procesamiento por lotes no puede continuar
## <a name="details"></a>Detalles  
  
|                 |                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------|
|  Nombre del producto   |         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]         |
| Versión del producto |                     [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                     |
|    Identificador del evento     |                                                 -                                                  |
|  Origen del evento   |       EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]       |
|    Componente    |                                             Motor EDI                                             |
|  Nombre simbólico  |                                    ErrorBatchAgreementDisabled                                     |
|  Texto del mensaje   | El acuerdo asociado con el identificador de lote {0} no está habilitado o ha expirado. El procesamiento por lotes no puede continuar. |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que BizTalk Server no pudo iniciar un lote o procesar un mensaje por lotes porque el acuerdo ha expirado.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que esté presente un lote con el identificador dado en las propiedades del acuerdo contenedor y sus fechas de inicio y fin estén dentro de las fechas de inicio y fin del acuerdo. Asegúrese también de que el acuerdo esté habilitado.