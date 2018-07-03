---
title: 'El intercambio contenía un error estructural. Último grupo funcional con estructura válida fue el Id.: | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd62855b-ecc6-4cfd-be9c-0025348eb841
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3da8a701e543fe5bfb9453af3cfa2514414f5c2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988101"
---
# <a name="the-interchange-had-structural-error-last-structurally-valid-functional-group-id-was"></a><span data-ttu-id="e4155-103">El intercambio contenía un error estructural.</span><span class="sxs-lookup"><span data-stu-id="e4155-103">The interchange had structural error.</span></span> <span data-ttu-id="e4155-104">El Id. del último grupo funcional con estructura válida fue:</span><span class="sxs-lookup"><span data-stu-id="e4155-104">Last structurally valid functional group ID was:</span></span>
## <a name="details"></a><span data-ttu-id="e4155-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="e4155-105">Details</span></span>  
  
|                 |                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e4155-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="e4155-106">Product Name</span></span>   |                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                 |
| <span data-ttu-id="e4155-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="e4155-107">Product Version</span></span> |                                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                             |
|    <span data-ttu-id="e4155-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="e4155-108">Event ID</span></span>     |                                                                         -                                                                          |
|  <span data-ttu-id="e4155-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="e4155-109">Event Source</span></span>   |                               <span data-ttu-id="e4155-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4155-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                               |
|    <span data-ttu-id="e4155-111">Componente</span><span class="sxs-lookup"><span data-stu-id="e4155-111">Component</span></span>    |                                                                     <span data-ttu-id="e4155-112">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="e4155-112">EDI Engine</span></span>                                                                     |
|  <span data-ttu-id="e4155-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e4155-113">Symbolic Name</span></span>  |                                                     <span data-ttu-id="e4155-114">X12InterchangeStructuralErrorAfter1stGroup</span><span class="sxs-lookup"><span data-stu-id="e4155-114">X12InterchangeStructuralErrorAfter1stGroup</span></span>                                                     |
|  <span data-ttu-id="e4155-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e4155-115">Message Text</span></span>   | <span data-ttu-id="e4155-116">El intercambio con Id. '{0}', Id. de remitente '{1}', Id. de destinatario '{2}' contenía un error estructural.</span><span class="sxs-lookup"><span data-stu-id="e4155-116">The interchange with id '{0}', with sender id '{1}', receiver id '{2}' had structural error.</span></span> <span data-ttu-id="e4155-117">El Id. del último grupo funcional con estructura válida fue '{3}'.</span><span class="sxs-lookup"><span data-stu-id="e4155-117">Last structurally valid functional group ID was '{3}'</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="e4155-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="e4155-118">Explanation</span></span>  
 <span data-ttu-id="e4155-119">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio X12 entrante porque ha tenido lugar un error estructural en el intercambio después del grupo funcional indicado.</span><span class="sxs-lookup"><span data-stu-id="e4155-119">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange, because a structural error occurred in the interchange after the indicated functional group.</span></span> <span data-ttu-id="e4155-120">Esto puede haberse producido con un intercambio que se estaba conservando, con conjuntos de transacciones suspendidos debido al error.</span><span class="sxs-lookup"><span data-stu-id="e4155-120">This may have occurred with an interchange that was being preserved, with transaction sets suspended on the error.</span></span> <span data-ttu-id="e4155-121">Como resultado de este error, el o los conjuntos de transacciones que incluían el error se han suspendido, pero el resto de los conjuntos de transacciones se han procesado como parte del lote conservado.</span><span class="sxs-lookup"><span data-stu-id="e4155-121">As a result of this error, the transaction set (or sets) that included the error was suspended, but the rest of the transaction sets were processed as part of the preserved batch.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e4155-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e4155-122">User Action</span></span>  
 <span data-ttu-id="e4155-123">Para resolver este error, pida al remitente del intercambio que corrija el error estructural y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="e4155-123">To resolve this error, have the sender of the interchange fix the structural error, and then resend the interchange.</span></span>