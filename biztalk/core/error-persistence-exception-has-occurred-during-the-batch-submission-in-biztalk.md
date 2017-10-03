---
title: "Se produjo una excepción de persistencia durante el envío del lote en la orquestación por lotes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf6e832f-9d01-46e7-aaf5-2b402d509fac
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7eae4f48209dc4f5afefbc69c40706a31f2b00b7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="a-persistence-exception-has-occurred-during-the-batch-submission-in-the-batching-orchestration"></a>Se produjo una excepción de persistencia durante el envío del lote en la orquestación de procesamiento por lotes
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor de procesamiento por lotes|  
|Nombre simbólico|PersistenceExceptionOccured|  
|Texto del mensaje|Se produjo una excepción de persistencia durante el envío del lote en la orquestación de procesamiento por lotes. Identificador de lote = {0}, ErrorMessage = {1}. Compruebe las suscripciones de puerto de envío y corríjalas.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que BizTalk Server no pudo enviar un intercambio por lotes por no estar ningún puerto de envío suscrito al intercambio.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que un puerto de envío se suscribe al lote estableciendo las siguientes propiedades de filtro para el puerto de envío: EDI. DestinationPartyName = \<PartyName >, EDI. BatchEncodingType = EDIFACT o X12 y EDI. ToBeBatched = False.