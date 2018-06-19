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
# <a name="data-stored-for-batching-status-reports"></a><span data-ttu-id="31cd3-102">Datos almacenados para informes de estado de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="31cd3-102">Data Stored for Batching Status Reports</span></span>
<span data-ttu-id="31cd3-103">Cuando el **activar informes** propiedad está seleccionada para un acuerdo, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] almacenará el estado de cada instancia de procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="31cd3-103">When the **Turn ON Reporting** property is selected for an agreement, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will store the status of each batching instance.</span></span> <span data-ttu-id="31cd3-104">Esta propiedad es en disponibles en la **propiedades generales** página de la **General** pestaña en el **propiedades del acuerdo de** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="31cd3-104">This property is in available in the **General Properties** page of the **General** tab in the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="31cd3-105">El estado puede ser cualquiera de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="31cd3-105">The status can be any of the following:</span></span>  
  
-   <span data-ttu-id="31cd3-106">**Define**: la instancia de proceso por lotes está configurada.</span><span class="sxs-lookup"><span data-stu-id="31cd3-106">**Defined**: The batch instance is configured.</span></span> <span data-ttu-id="31cd3-107">La fecha y hora de activación de lotes es posterior a las actuales.</span><span class="sxs-lookup"><span data-stu-id="31cd3-107">The batch activation start date time is greater than the current date time.</span></span> <span data-ttu-id="31cd3-108">Todos los parámetros por lotes están definidos, pero el lote no se está ejecutando (no acepta documentos).</span><span class="sxs-lookup"><span data-stu-id="31cd3-108">All batch parameters are defined, but the batch is not running (not accepting documents).</span></span>  
  
-   <span data-ttu-id="31cd3-109">**Active**: la instancia de lotes se ha activado y está agregando conjuntos de transacciones.</span><span class="sxs-lookup"><span data-stu-id="31cd3-109">**Active**: The batch instance has been activated and is aggregating transaction sets.</span></span> <span data-ttu-id="31cd3-110">Puede ver el número de conjuntos de transacciones aceptados y rechazados.</span><span class="sxs-lookup"><span data-stu-id="31cd3-110">You can view the number of accepted/rejected transaction sets.</span></span>  
  
-   <span data-ttu-id="31cd3-111">**Libera**: el lote cumple los criterios de versión y se publicó en el cuadro de mensajes, pero no ha lanzado la canalización de envío, o que el lote se detuvo antes de procesar todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="31cd3-111">**Released**: The batch met the release criteria and was released into the MessageBox, but has not been released by the send pipeline, or that the batch was stopped before processing any messages.</span></span>  
  
-   <span data-ttu-id="31cd3-112">**Completado**: la canalización EdiSend ha enviado el lote.</span><span class="sxs-lookup"><span data-stu-id="31cd3-112">**Completed**: The batch was sent by the EdiSend pipeline.</span></span>  
  
 <span data-ttu-id="31cd3-113">Si la canalización EdiSend ha enviado el lote, puede correlacionar el registro del lote en la UI con un registro del intercambio EDI enviado y ver los detalles del conjunto de transacciones.</span><span class="sxs-lookup"><span data-stu-id="31cd3-113">If the batch was sent by the EdiSend pipeline, you can correlate the batch record in the UI with a record of the sent Edi interchange, and view transaction set details.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31cd3-114">Puede haber varias instancias de lotes con el estado Completado para una configuración de lote.</span><span class="sxs-lookup"><span data-stu-id="31cd3-114">There may be multiple batch instances with a status of Completed for a batch configuration.</span></span>  
  
 <span data-ttu-id="31cd3-115">**Correlacionar un intercambio con un lote**</span><span class="sxs-lookup"><span data-stu-id="31cd3-115">**Correlating an Interchange with a Batch**</span></span>  
  
 <span data-ttu-id="31cd3-116">La actividad de BAM BusinessMessageJournal permite que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] correlacione un intercambio EDI recibido que contenga un conjunto de transacciones con un intercambio por lotes saliente que contenga el mismo conjunto de transacciones.</span><span class="sxs-lookup"><span data-stu-id="31cd3-116">The BusinessMessageJournal BAM activity enables [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to correlate a received EDI interchange containing a transaction set with an outgoing batched interchange that contains the same transaction set.</span></span> <span data-ttu-id="31cd3-117">Para obtener información acerca de cómo implementar y utilizar esta información de correlación, vea [correlacionar un conjunto de transacciones entrante con un lote saliente](../core/correlating-an-incoming-transaction-set-with-an-outgoing-batch.md).</span><span class="sxs-lookup"><span data-stu-id="31cd3-117">For information about how to implement and use this correlation information, see [Correlating an Incoming Transaction Set with an Outgoing Batch](../core/correlating-an-incoming-transaction-set-with-an-outgoing-batch.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31cd3-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="31cd3-118">See Also</span></span>  
 <span data-ttu-id="31cd3-119">[Datos almacenados para informes de estado de AS2 y EDI](../core/data-stored-for-edi-and-as2-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="31cd3-119">[Data Stored for EDI and AS2 Status Reports](../core/data-stored-for-edi-and-as2-status-reports.md) </span></span>  
 <span data-ttu-id="31cd3-120">[Datos almacenados para informes de estado EDI](../core/data-stored-for-edi-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="31cd3-120">[Data Stored for EDI Status Reports](../core/data-stored-for-edi-status-reports.md) </span></span>  
 [<span data-ttu-id="31cd3-121">Datos almacenados para informes de estado de AS2</span><span class="sxs-lookup"><span data-stu-id="31cd3-121">Data Stored for AS2 Status Reports</span></span>](../core/data-stored-for-as2-status-reports.md)