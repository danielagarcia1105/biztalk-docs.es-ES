---
title: Se ha producido una excepción durante la ejecución de la orquestación de enrutamiento | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 68ec8921-ba05-496e-8dcc-fd8994fcb8b7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 917349fe1157bc672ad3f3897f504625c59e7ba3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007325"
---
# <a name="an-exception-has-occurred-during-the-execution-of-the-routing-orchestration"></a>Se produjo una excepción al ejecutar la orquestación de enrutamiento
## <a name="details"></a>Detalles  
  
|                 |                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------|
|  Nombre del producto   |       [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]       |
| Versión del producto |                   [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                   |
|    Identificador del evento     |                                               -                                                |
|  Origen del evento   |     EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]     |
|    Componente    |                                        Motor de procesamiento por lotes                                         |
|  Nombre simbólico  |                                 ExceptionOccuredDuringRouting                                  |
|  Texto del mensaje   | Se produjo una excepción al ejecutar la orquestación de enrutamiento. ErrorMessage = {0} |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la orquestación de enrutamiento no pudo procesar correctamente cada copia del elemento de lote XML debido a la condición de error indicada en el campo Mensaje de error.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, determinar cuál es la condición de error desde el campo de mensaje de error, resuelva el error y vuelva a enviar el mensaje.