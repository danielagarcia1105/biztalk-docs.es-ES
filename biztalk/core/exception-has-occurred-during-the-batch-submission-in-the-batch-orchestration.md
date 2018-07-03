---
title: Se ha producido una excepción durante el envío del lote en la orquestación por lotes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c58b2fa9-d036-4e09-a0f8-77a2f983881a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 838e9aff43dd260fd4af8e46ca88782c2389dfc7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971533"
---
# <a name="an-exception-has-occurred-during-the-batch-submission-in-the-batching-orchestration"></a><span data-ttu-id="ef70c-102">Se produjo una excepción durante el envío del lote de la orquestación de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="ef70c-102">An exception has occurred during the batch submission in the batching orchestration</span></span>
## <a name="details"></a><span data-ttu-id="ef70c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ef70c-103">Details</span></span>  
  
|                 |                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ef70c-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ef70c-104">Product Name</span></span>   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                  |
| <span data-ttu-id="ef70c-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ef70c-105">Product Version</span></span> |                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                              |
|    <span data-ttu-id="ef70c-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ef70c-106">Event ID</span></span>     |                                                          -                                                          |
|  <span data-ttu-id="ef70c-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ef70c-107">Event Source</span></span>   |               <span data-ttu-id="ef70c-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef70c-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                |
|    <span data-ttu-id="ef70c-109">Componente</span><span class="sxs-lookup"><span data-stu-id="ef70c-109">Component</span></span>    |                                                   <span data-ttu-id="ef70c-110">Motor de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="ef70c-110">Batching Engine</span></span>                                                   |
|  <span data-ttu-id="ef70c-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ef70c-111">Symbolic Name</span></span>  |                                                  <span data-ttu-id="ef70c-112">ExceptionOccured</span><span class="sxs-lookup"><span data-stu-id="ef70c-112">ExceptionOccured</span></span>                                                   |
|  <span data-ttu-id="ef70c-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ef70c-113">Message Text</span></span>   | <span data-ttu-id="ef70c-114">Se produjo una excepción durante el envío del lote en la orquestación por lotes.</span><span class="sxs-lookup"><span data-stu-id="ef70c-114">An exception has occured during the batch submission in the batching Orchestration.</span></span> <span data-ttu-id="ef70c-115">Identificador de lote = {0}; Mensaje de error = {1}</span><span class="sxs-lookup"><span data-stu-id="ef70c-115">Batch Id= {0}, ErrorMessage {1}</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="ef70c-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="ef70c-116">Explanation</span></span>  
 <span data-ttu-id="ef70c-117">Este evento de error,  indica que la orquestación de lote no pudo agregar un elemento de lote a un lote debido a la condición de error indicada en el campo Mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="ef70c-117">This Error/Warning/Information event indicates that the batching orchestration could not add a batch element to a batch because of the error condition indicated in the ErrorMessage field.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ef70c-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ef70c-118">User Action</span></span>  
 <span data-ttu-id="ef70c-119">Para resolver este error, determine cuál es la condición de error desde el campo Mensaje de error, resuelva el error y vuelva a enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="ef70c-119">To resolve this error, determine what the error condition is from the ErrorMessage field, resolve the error, and then resubmit the message.</span></span>