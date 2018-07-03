---
title: Error durante la serialización. El conjunto de transacciones contenido en el grupo funcional se está suspendiendo por los errores siguientes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24b76086-334b-45fb-85f8-82e3335daac4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c89d4300d54bc7e524f9f33aea4689a6cdc4bc27
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007661"
---
# <a name="error-encountered-during-serialization-the-edifact-transaction-set-contained-in-functional-group-is-being-suspended-with-following-errors"></a>Error durante la serialización. El conjunto de transacciones Edifact contenido en el grupo funcional se está suspendiendo por los errores siguientes
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                               |
| Versión del producto |                                                                                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                                           |
|    Identificador del evento     |                                                                                                                       -                                                                                                                        |
|  Origen del evento   |                                                                             EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                             |
|    Componente    |                                                                                                                   Motor EDI                                                                                                                   |
|  Nombre simbólico  |                                                                                                          EfactTransactionSetSendError                                                                                                          |
|  Texto del mensaje   | Error durante la serialización. El conjunto de transacciones con Id. '{0}'contenido en el grupo funcional con Id.'{1}', en el intercambio con Id. '{2}', Id. de remitente '{3}', Id. de destinatario '{4}' se está suspendiendo por los errores siguientes: |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de envío EDI encontró un error al serializar un intercambio EDIFACT saliente debido a los errores indicados con el conjunto de transacciones identificado.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, use la información del mensaje de error para identificar el error en el conjunto de transacciones y, a continuación, determine la resolución del problema en la ayuda del producto.