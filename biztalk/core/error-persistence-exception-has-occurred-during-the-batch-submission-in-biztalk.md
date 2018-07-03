---
title: Se ha producido una excepción de persistencia durante el envío del lote en la orquestación por lotes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf6e832f-9d01-46e7-aaf5-2b402d509fac
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8a1277dd26fcb2036e3378f7fa6d22067a1f7e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020922"
---
# <a name="a-persistence-exception-has-occurred-during-the-batch-submission-in-the-batching-orchestration"></a>Se produjo una excepción de persistencia durante el envío del lote en la orquestación de procesamiento por lotes
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                     |
| Versión del producto |                                                                 [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                 |
|    Identificador del evento     |                                                                                             -                                                                                              |
|  Origen del evento   |                                                   EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                   |
|    Componente    |                                                                                      Motor de procesamiento por lotes                                                                                       |
|  Nombre simbólico  |                                                                                PersistenceExceptionOccured                                                                                 |
|  Texto del mensaje   | Se produjo una excepción de persistencia durante el envío del lote en la orquestación de procesamiento por lotes. Identificador de lote = {0}; Mensaje de error = {1}. Compruebe las suscripciones de puerto de envío y corríjalas. |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que BizTalk Server no pudo enviar un intercambio por lotes por no estar ningún puerto de envío suscrito al intercambio.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que un puerto de envío se suscribe al lote estableciendo las siguientes propiedades de filtro para el puerto de envío: EDI. DestinationPartyName = \<PartyName\>, EDI. BatchEncodingType = EDIFACT o X12 y EDI. ToBeBatched = False.