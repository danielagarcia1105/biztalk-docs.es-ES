---
title: Datos almacenados para informes de estado de procesamiento por lotes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d55aa0e1-095f-434e-8530-f1a946ad4430
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db9831aafce56845fe7b75e91f5369a8860d8996
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238596"
---
# <a name="data-stored-for-batching-status-reports"></a>Datos almacenados para informes de estado de procesamiento por lotes
Cuando el **activar informes** propiedad está seleccionada para un acuerdo, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] almacenará el estado de cada instancia de procesamiento por lotes. Esta propiedad es en disponibles en la **propiedades generales** página de la **General** pestaña en el **propiedades del acuerdo de** cuadro de diálogo. El estado puede ser cualquiera de los siguientes valores:  
  
-   **Define**: la instancia de proceso por lotes está configurada. La fecha y hora de activación de lotes es posterior a las actuales. Todos los parámetros por lotes están definidos, pero el lote no se está ejecutando (no acepta documentos).  
  
-   **Active**: la instancia de lotes se ha activado y está agregando conjuntos de transacciones. Puede ver el número de conjuntos de transacciones aceptados y rechazados.  
  
-   **Libera**: el lote cumple los criterios de versión y se publicó en el cuadro de mensajes, pero no ha lanzado la canalización de envío, o que el lote se detuvo antes de procesar todos los mensajes.  
  
-   **Completado**: la canalización EdiSend ha enviado el lote.  
  
 Si la canalización EdiSend ha enviado el lote, puede correlacionar el registro del lote en la UI con un registro del intercambio EDI enviado y ver los detalles del conjunto de transacciones.  
  
> [!NOTE]
>  Puede haber varias instancias de lotes con el estado Completado para una configuración de lote.  
  
 **Correlacionar un intercambio con un lote**  
  
 La actividad de BAM BusinessMessageJournal permite que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] correlacione un intercambio EDI recibido que contenga un conjunto de transacciones con un intercambio por lotes saliente que contenga el mismo conjunto de transacciones. Para obtener información acerca de cómo implementar y utilizar esta información de correlación, vea [correlacionar un conjunto de transacciones entrante con un lote saliente](../core/correlating-an-incoming-transaction-set-with-an-outgoing-batch.md).  
  
## <a name="see-also"></a>Vea también  
 [Datos almacenados para informes de estado de AS2 y EDI](../core/data-stored-for-edi-and-as2-status-reports.md)   
 [Datos almacenados para informes de estado EDI](../core/data-stored-for-edi-status-reports.md)   
 [Datos almacenados para informes de estado de AS2](../core/data-stored-for-as2-status-reports.md)