---
title: El intercambio EDIFACT debía contener TransactionSetGroup o FunctionalGroup Xml etiquetas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 34318133-211f-422d-acdf-b841ece5d2b0
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5736a9146a88dd9c9dac6747e381fccc88f18d9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979333"
---
# <a name="edifact-interchange-should-have-contained-transactionsetgroup-or-functionalgroup-xml-tags"></a>El intercambio Edifact debía contener las etiquetas Xml TransactionSetGroup o FunctionalGroup.
## <a name="details"></a>Detalles  
  
|                 |                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------|
|  Nombre del producto   |    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]     |
| Versión del producto |                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                 |
|    Identificador del evento     |                                             -                                             |
|  Origen del evento   |  EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
|    Componente    |                                        Motor EDI                                         |
|  Nombre simbólico  |                                             -                                             |
|  Texto del mensaje   | El intercambio Edifact debía contener las etiquetas Xml TransactionSetGroup o FunctionalGroup. |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de envío no pudo procesar un intercambio EDIFACT procesado por lotes y conservado porque las etiquetas TransactionSetGroup o FunctionalGroup no se incluyeron en el archivo XML de intercambio.  
  
 Cuando BizTalk procesa un intercambio por lotes conservado, se asigna una etiqueta XML a un grupo de conjuntos de transacciones o a un grupo de los grupos del archivo XML del intercambio. A un grupo de conjuntos de transacciones se le asigna la etiqueta TransactionSetGroup. A un grupo de grupos se le asigna la etiqueta FunctionalGroup. Esta condición de error tiene lugar si configura un lote conservado mediante una canalización de recepción y una canalización de envío de transmisión de atravesar. La canalización de recepción configura las etiquetas y la de envío las elimina.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el archivo XML generado para el lote conservado tiene una estructura XML bien formada con la etiqueta TransactionSetGroup (para un grupo con varios conjuntos de transacciones) o la etiqueta FunctionalGroup (para varios grupos).