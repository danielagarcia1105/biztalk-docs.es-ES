---
title: Error al analizar. El conjunto de transacciones contenido en el intercambio (sin grupo) se está suspendiendo por los errores siguientes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 901fef68-4649-480a-997c-b061d7d069d6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2e0d8e2b03decf2db806a08f082b7aace276a8e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006421"
---
# <a name="error-encountered-during-parsing-the-edifact-transaction-set-contained-in-interchange-without-group-is-being-suspended-with-following-errors"></a>Error al analizar. El conjunto de transacciones contenido en el intercambio (sin grupo) se está suspendiendo por los errores siguientes
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                   |
| Versión del producto |                                                                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                               |
|    Identificador del evento     |                                                                                                           -                                                                                                           |
|  Origen del evento   |                                                                EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                 |
|    Componente    |                                                                                                      Motor EDI                                                                                                       |
|  Nombre simbólico  |                                                                                      EfactTransactionSetReceiveErrorWithoutGroup                                                                                      |
|  Texto del mensaje   | Error al analizar. El conjunto de transacciones con Id. '{0}'contenido en el intercambio (sin grupo) con el Id.'{1}', Id. de remitente '{2}', Id. de destinatario '{3}' se está suspendiendo por los errores siguientes: |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción EDI ha encontrado un error al analizar un intercambio EDIFACT entrante sin un grupo debido a los errores indicados con el conjunto de transacciones identificado en el intercambio. Tenga en cuenta que el conjunto de transacciones no se encuentra en un grupo en el intercambio.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, use la información del mensaje de error para identificar el error en el conjunto de transacciones y, a continuación, determine la resolución del problema en la ayuda del producto.