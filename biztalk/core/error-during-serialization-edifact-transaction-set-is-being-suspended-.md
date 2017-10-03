---
title: Conjunto de contenido en el error de intercambio de transacciones de EDIFACT | Documentos de Microsoft
description: "Error durante la serialización. El conjunto de transacciones contenido en el intercambio (sin grupo) se está suspendiendo por los errores siguientes"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a0a33ac-d83e-495c-ba75-88c15ad7cfcd
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67f089e49941ffec7d3392b3bc35edcbc4eefec5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="edifact-transaction-set-is-suspended-error-and-details"></a>Conjunto de transacciones de EDIFACT es detalles y error suspendido

`Error encountered during serialization. The Edifact transaction set contained in interchange (without group) is being suspended with following errors`

## <a name="details"></a>Detalles  
  
|||  
|---|---|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|EfactTransactionSetSendErrorWithoutGroup|  
|Texto del mensaje|Error durante la serialización. El conjunto de transacciones con identificador '{0}' contenido en el intercambio (sin grupo) con Id. '{1}', Id. de remitente '{2}', Id. de destinatario '{3}' se está suspendiendo por los siguientes errores:|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de envío EDI encontró un error al serializar un intercambio EDIFACT saliente debido a los errores indicados con el conjunto de transacciones identificado. Tenga en cuenta que el conjunto de transacciones no se encuentra en un grupo en el intercambio.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, use la información en el mensaje de error para identificar el error en el conjunto de transacciones y, a continuación, determine la resolución del problema.