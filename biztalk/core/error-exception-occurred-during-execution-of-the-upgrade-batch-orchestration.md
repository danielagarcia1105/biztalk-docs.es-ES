---
title: Se ha producido una excepción durante la ejecución de la orquestación de lote de actualización | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2221a498-98aa-43ab-bc4e-34dcbd92dcf0
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a12c1a116a0f7d35f6fbc7d2250c48f224081fae
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981349"
---
# <a name="an-exception-has-occurred-during-the-execution-of-the-upgrade-batch-orchestration"></a>Se produjo una excepción durante la ejecución de la orquestación del lote de actualización
## <a name="details"></a>Detalles  
  
|                 |                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]           |
| Versión del producto |                      [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                       |
|    Identificador del evento     |                                                   -                                                   |
|  Origen del evento   |                                          EDI de BizTalk Server                                           |
|    Componente    |                                            Motor de procesamiento por lotes                                            |
|  Nombre simbólico  |                                     ExceptionOccuredDuringUpgrade                                     |
|  Texto del mensaje   | Se produjo una excepción durante la ejecución de la orquestación del lote de actualización. ErrorMessage = {0} |
  
## <a name="explanation"></a>Explicación  
 El evento de error,  indica que la orquestación del lote de actualización no pudo procesar correctamente el mensaje debido a la condición de error indicada en el campo Mensaje de error.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, determine cuál es la condición de error desde el campo Mensaje de error, resuelva el error y vuelva a enviar el mensaje.