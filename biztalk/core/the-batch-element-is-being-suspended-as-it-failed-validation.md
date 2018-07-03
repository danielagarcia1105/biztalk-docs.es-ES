---
title: El elemento de lote se ha suspendido debido a un error de validación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea5e19e8-4592-40f4-bffe-85ab27653fd5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90f82c88adc18899aac6d481b7a5d3e31e1a72c8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021970"
---
# <a name="the-batch-element-is-being-suspended-as-it-failed-validation"></a>El elemento de procesamiento por lotes se ha suspendido debido a un error de validación
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                    Motor de procesamiento por lotes                                     |
|  Nombre simbólico  |                                 BatchElementSuspended                                  |
|  Texto del mensaje   |    El elemento de procesamiento por lotes se ha suspendido debido a un error de validación. El error es: {0}    |
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que la orquestación por lotes no pudo agregar un conjunto de transacciones a un intercambio por lotes debido a que el conjunto de transacciones tuvo un error en la validación que ha realizado la orquestación por lotes. El intercambio se generará sin el conjunto de transacciones que tuvo un error en la validación. La orquestación por lotes configura la propiedad de contexto EDI.BatchElementValidationFailure en "True". La orquestación BatchSuspend recoge el mensaje que se basa en esa propiedad de contexto, registra la información de error y, a continuación, se suspende.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, indique al remitente del conjunto de transacciones qué error se produjo, según se indica en el mensaje de error. Pida al remitente que resuelva el problema que provocó el error de validación y reenvíe el conjunto de transacciones.