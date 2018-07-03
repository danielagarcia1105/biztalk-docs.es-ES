---
title: Se ha producido una excepción durante el envío del lote en la orquestación por lotes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c58b2fa9-d036-4e09-a0f8-77a2f983881a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 838e9aff43dd260fd4af8e46ca88782c2389dfc7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971533"
---
# <a name="an-exception-has-occurred-during-the-batch-submission-in-the-batching-orchestration"></a>Se produjo una excepción durante el envío del lote de la orquestación de procesamiento por lotes
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                  |
| Versión del producto |                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                              |
|    Identificador del evento     |                                                          -                                                          |
|  Origen del evento   |               EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                |
|    Componente    |                                                   Motor de procesamiento por lotes                                                   |
|  Nombre simbólico  |                                                  ExceptionOccured                                                   |
|  Texto del mensaje   | Se produjo una excepción durante el envío del lote en la orquestación por lotes. Identificador de lote = {0}; Mensaje de error = {1} |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la orquestación de lote no pudo agregar un elemento de lote a un lote debido a la condición de error indicada en el campo Mensaje de error.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, determine cuál es la condición de error desde el campo Mensaje de error, resuelva el error y vuelva a enviar el mensaje.