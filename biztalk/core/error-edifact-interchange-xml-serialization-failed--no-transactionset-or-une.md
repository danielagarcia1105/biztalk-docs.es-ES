---
title: "Error de serialización Xml de intercambio EDIFACT debido a la estructura no válida, sin transactionSet o UNE | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3ce1c219-f2ed-46c1-ae4b-8a4206f7cd01
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5c6aae4bc3ed16afffadec774eaeac9ed64808d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="edifact-interchange-xml-serialization-failed-due-to-invalid-structure-no-transactionset-or-une"></a>Error de serialización Xml de intercambio Edifact debido a una estructura no válida, sin TransactionSet o UNE
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|EfactTransactionSetOrUneNotFound|  
|Texto del mensaje|Error de serialización Xml de intercambio Edifact debido a una estructura no válida. Se busca TransactionSet o UNE, pero no se encuentra.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción EDI no pudo procesar el intercambio EDIFACT entrante debido a que el primer segmento no era ni UNA ni UNB. El segmento UNA es opcional; el segmento UNB, obligatorio.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el remitente del intercambio estructura el mensaje de modo que un conjunto de transacciones de un grupo sea seguido por otro conjunto de transacciones o bien por un segmento UNE. Pida al remitente que vuelva a enviar el intercambio.