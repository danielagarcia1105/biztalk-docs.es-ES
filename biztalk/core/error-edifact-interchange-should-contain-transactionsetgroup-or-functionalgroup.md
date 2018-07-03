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
# <a name="edifact-interchange-should-have-contained-transactionsetgroup-or-functionalgroup-xml-tags"></a><span data-ttu-id="316a6-102">El intercambio Edifact debía contener las etiquetas Xml TransactionSetGroup o FunctionalGroup.</span><span class="sxs-lookup"><span data-stu-id="316a6-102">Edifact interchange should have contained TransactionSetGroup or FunctionalGroup Xml tags</span></span>
## <a name="details"></a><span data-ttu-id="316a6-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="316a6-103">Details</span></span>  
  
|                 |                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------|
|  <span data-ttu-id="316a6-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="316a6-104">Product Name</span></span>   |    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]     |
| <span data-ttu-id="316a6-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="316a6-105">Product Version</span></span> |                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                 |
|    <span data-ttu-id="316a6-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="316a6-106">Event ID</span></span>     |                                             -                                             |
|  <span data-ttu-id="316a6-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="316a6-107">Event Source</span></span>   |  <span data-ttu-id="316a6-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="316a6-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>   |
|    <span data-ttu-id="316a6-109">Componente</span><span class="sxs-lookup"><span data-stu-id="316a6-109">Component</span></span>    |                                        <span data-ttu-id="316a6-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="316a6-110">EDI Engine</span></span>                                         |
|  <span data-ttu-id="316a6-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="316a6-111">Symbolic Name</span></span>  |                                             -                                             |
|  <span data-ttu-id="316a6-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="316a6-112">Message Text</span></span>   | <span data-ttu-id="316a6-113">El intercambio Edifact debía contener las etiquetas Xml TransactionSetGroup o FunctionalGroup.</span><span class="sxs-lookup"><span data-stu-id="316a6-113">Edifact interchange should have contained TransactionSetGroup or FunctionalGroup Xml tags</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="316a6-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="316a6-114">Explanation</span></span>  
 <span data-ttu-id="316a6-115">Este evento de error,  indica que la canalización de envío no pudo procesar un intercambio EDIFACT procesado por lotes y conservado porque las etiquetas TransactionSetGroup o FunctionalGroup no se incluyeron en el archivo XML de intercambio.</span><span class="sxs-lookup"><span data-stu-id="316a6-115">This Error/Warning/Information event indicates that the send pipeline could not process an EDIFACT batched interchange that was preserved because the TransactionSetGroup or FunctionalGroup tags were not included in the interchange XML file.</span></span>  
  
 <span data-ttu-id="316a6-116">Cuando BizTalk procesa un intercambio por lotes conservado, se asigna una etiqueta XML a un grupo de conjuntos de transacciones o a un grupo de los grupos del archivo XML del intercambio.</span><span class="sxs-lookup"><span data-stu-id="316a6-116">When BizTalk processes a batched interchange that is preserved, a group of transaction sets or a group of groups in the interchange's XML file are given an XML tag.</span></span> <span data-ttu-id="316a6-117">A un grupo de conjuntos de transacciones se le asigna la etiqueta TransactionSetGroup.</span><span class="sxs-lookup"><span data-stu-id="316a6-117">A group of transaction sets is given the TransactionSetGroup tag.</span></span> <span data-ttu-id="316a6-118">A un grupo de grupos se le asigna la etiqueta FunctionalGroup.</span><span class="sxs-lookup"><span data-stu-id="316a6-118">A group of groups is given the FunctionalGroup tag.</span></span> <span data-ttu-id="316a6-119">Esta condición de error tiene lugar si configura un lote conservado mediante una canalización de recepción y una canalización de envío de transmisión de atravesar.</span><span class="sxs-lookup"><span data-stu-id="316a6-119">This error condition occurs if you set up a preserved batch using a receive pipeline and a passthrough transmit send pipeline.</span></span> <span data-ttu-id="316a6-120">La canalización de recepción configura las etiquetas y la de envío las elimina.</span><span class="sxs-lookup"><span data-stu-id="316a6-120">The tags are set by the receive pipeline and stripped out by the send pipeline.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="316a6-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="316a6-121">User Action</span></span>  
 <span data-ttu-id="316a6-122">Para resolver este error, asegúrese de que el archivo XML generado para el lote conservado tiene una estructura XML bien formada con la etiqueta TransactionSetGroup (para un grupo con varios conjuntos de transacciones) o la etiqueta FunctionalGroup (para varios grupos).</span><span class="sxs-lookup"><span data-stu-id="316a6-122">To resolve this error, ensure that the XML file generated for the preserved batch has a well-formed XML structure with the TransactionSetGroup tag (for a group with multiple transaction sets) and/or the FunctionalGroup tag (for multiple groups).</span></span>