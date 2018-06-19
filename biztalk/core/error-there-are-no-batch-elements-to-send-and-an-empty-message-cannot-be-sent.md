---
title: No hay ningún elemento de lote para enviar y no se puede enviar un mensaje vacío porque no está configurado para entidad | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0752079a-173e-4de3-96f4-e5de01b799b5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80dcf96feef006a2576afc5829e7927e003524a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241964"
---
# <a name="there-are-no-batch-elements-to-send-and-an-empty-message-cannot-be-sent-as-it-is-not-configured-for-party"></a><span data-ttu-id="d0b3c-102">No hay elementos por lotes que enviar, ni es posible enviar un mensaje vacío porque no está configurado para la entidad</span><span class="sxs-lookup"><span data-stu-id="d0b3c-102">There are no batch elements to send and an empty message cannot be sent as it is not configured for party</span></span>
## <a name="details"></a><span data-ttu-id="d0b3c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="d0b3c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d0b3c-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="d0b3c-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="d0b3c-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="d0b3c-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="d0b3c-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="d0b3c-106">Event ID</span></span>|-|  
|<span data-ttu-id="d0b3c-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="d0b3c-107">Event Source</span></span>|<span data-ttu-id="d0b3c-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0b3c-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="d0b3c-109">Componente</span><span class="sxs-lookup"><span data-stu-id="d0b3c-109">Component</span></span>|<span data-ttu-id="d0b3c-110">Motor de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="d0b3c-110">Batching Engine</span></span>|  
|<span data-ttu-id="d0b3c-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d0b3c-111">Symbolic Name</span></span>|<span data-ttu-id="d0b3c-112">EmptyMessageNotAllowed</span><span class="sxs-lookup"><span data-stu-id="d0b3c-112">EmptyMessageNotAllowed</span></span>|  
|<span data-ttu-id="d0b3c-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d0b3c-113">Message Text</span></span>|<span data-ttu-id="d0b3c-114">No hay elementos por lotes que enviar, ni es posible enviar un mensaje vacío porque no está configurado para la entidad {0}.</span><span class="sxs-lookup"><span data-stu-id="d0b3c-114">There are no batch elements to send and an empty message cannot be sent as it is not configured for party {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d0b3c-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="d0b3c-115">Explanation</span></span>  
 <span data-ttu-id="d0b3c-116">Esta advertencia indica que no se envió ningún mensaje de lote en un proceso de procesamiento por lotes basado en programa porque no se recibió ningún elemento de lote cuando estaba programada la liberación del lote, y no se ha habilitado la señal de lotes vacíos.</span><span class="sxs-lookup"><span data-stu-id="d0b3c-116">This Warning indicates that no batch message was sent in a schedule-based batching process because no batch elements had been received when the batch release was scheduled, and the empty batch signal has not been enabled.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d0b3c-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d0b3c-117">User Action</span></span>  
 <span data-ttu-id="d0b3c-118">Para impedir que se exponga esta advertencia, configure la señal de lotes vacíos mediante el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="d0b3c-118">To prevent this warning from being posted, configure the empty batch signal by doing the following:</span></span>  
  
1.  <span data-ttu-id="d0b3c-119">Abra la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="d0b3c-119">Open the BizTalk Server Administration Console.</span></span>  
  
2.  <span data-ttu-id="d0b3c-120">Vaya al nodo Entidades.</span><span class="sxs-lookup"><span data-stu-id="d0b3c-120">Move to the Parties node.</span></span>  
  
3.  <span data-ttu-id="d0b3c-121">Abra el cuadro de diálogo Propiedades de EDI para la entidad.</span><span class="sxs-lookup"><span data-stu-id="d0b3c-121">Open the EDI Properties dialog box for the party.</span></span>  
  
4.  <span data-ttu-id="d0b3c-122">Haga clic en el nodo Configuración de creación de lotes de intercambio (para la codificación correspondiente).</span><span class="sxs-lookup"><span data-stu-id="d0b3c-122">Click the Interchange Batch Creation Settings node (for the appropriate encoding).</span></span>  
  
5.  <span data-ttu-id="d0b3c-123">Haga clic en el Programador.</span><span class="sxs-lookup"><span data-stu-id="d0b3c-123">Click the Scheduler.</span></span>  
  
6.  <span data-ttu-id="d0b3c-124">Haga clic en la propiedad Enviar señal de lotes vacíos.</span><span class="sxs-lookup"><span data-stu-id="d0b3c-124">Click the Send empty batch signal property.</span></span>