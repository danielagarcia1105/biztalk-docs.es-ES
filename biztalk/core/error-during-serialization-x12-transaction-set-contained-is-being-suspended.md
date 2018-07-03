---
title: Error durante la serialización. El conjunto de transacciones contenido en el grupo funcional se está suspendiendo por los siguientes errores de X12 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49b13038-2637-4435-91e9-d6fe2b80ca7a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 745fee9f48d534b750b605268ce63b1c685e3231
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988941"
---
# <a name="error-encountered-during-serialization-the-x12-transaction-set-contained-in-functional-group-is-being-suspended-with-following-errors"></a>Error durante la serialización. El conjunto de transacciones X12 contenido en el grupo funcional se está suspendiendo por los errores siguientes
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                             |
| Versión del producto |                                                                                         [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                                         |
|    Identificador del evento     |                                                                                                                     -                                                                                                                      |
|  Origen del evento   |                                                                           EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                           |
|    Componente    |                                                                                                                 Motor EDI                                                                                                                 |
|  Nombre simbólico  |                                                                                                         X12TransactionSetSendError                                                                                                         |
|  Texto del mensaje   | Error durante la serialización. El X12 conjunto de transacciones con Id. '{0}'contenido en el grupo funcional con Id.'{1}', en el intercambio con Id. '{2}', Id. de remitente '{3}', Id. de destinatario '{4}' se está suspendiendo por los errores siguientes: |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de envío EDI encontró un error al serializar un intercambio X12 saliente debido a los errores indicados con el conjunto de transacciones identificado.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, use la información del mensaje de error para identificar el error en el conjunto de transacciones y, a continuación, determine la resolución del problema en la ayuda del producto.