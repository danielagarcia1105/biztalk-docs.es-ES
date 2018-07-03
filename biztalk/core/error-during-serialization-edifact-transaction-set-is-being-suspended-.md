---
title: Conjunto de transacciones contenido en el error de intercambio | Microsoft Docs
description: Error durante la serialización. El conjunto de transacciones contenido en el intercambio (sin grupo) se está suspendiendo por los errores siguientes
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a0a33ac-d83e-495c-ba75-88c15ad7cfcd
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5fcd7702ce791037d8a7320f647955fca1c9489
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981933"
---
# <a name="edifact-transaction-set-is-suspended-error-and-details"></a>Conjunto de transacciones EDIFACT es error suspendido y detalles

`Error encountered during serialization. The Edifact transaction set contained in interchange (without group) is being suspended with following errors`

## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                              |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                      |
| Versión del producto |                                                                                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                                  |
|    Identificador del evento     |                                                                                                              -                                                                                                               |
|  Origen del evento   |                                                                    EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                    |
|    Componente    |                                                                                                          Motor EDI                                                                                                          |
|  Nombre simbólico  |                                                                                           EfactTransactionSetSendErrorWithoutGroup                                                                                           |
|  Texto del mensaje   | Error durante la serialización. El conjunto de transacciones con Id. '{0}'contenido en el intercambio (sin grupo) con el Id.'{1}', Id. de remitente '{2}', Id. de destinatario '{3}' se está suspendiendo por los errores siguientes: |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de envío EDI encontró un error al serializar un intercambio EDIFACT saliente debido a los errores indicados con el conjunto de transacciones identificado. Tenga en cuenta que el conjunto de transacciones no se encuentra en un grupo en el intercambio.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, use la información del mensaje de error para identificar el error en el conjunto de transacciones y, a continuación, determine la resolución del problema.