---
title: Se ha producido una excepción durante la ejecución de la orquestación de lote de actualización | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2221a498-98aa-43ab-bc4e-34dcbd92dcf0
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a12c1a116a0f7d35f6fbc7d2250c48f224081fae
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981349"
---
# <a name="an-exception-has-occurred-during-the-execution-of-the-upgrade-batch-orchestration"></a><span data-ttu-id="cb52f-102">Se produjo una excepción durante la ejecución de la orquestación del lote de actualización</span><span class="sxs-lookup"><span data-stu-id="cb52f-102">An exception has occurred during the execution of the upgrade batch orchestration</span></span>
## <a name="details"></a><span data-ttu-id="cb52f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="cb52f-103">Details</span></span>  
  
|                 |                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="cb52f-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="cb52f-104">Product Name</span></span>   |          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]           |
| <span data-ttu-id="cb52f-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="cb52f-105">Product Version</span></span> |                      [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                       |
|    <span data-ttu-id="cb52f-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="cb52f-106">Event ID</span></span>     |                                                   -                                                   |
|  <span data-ttu-id="cb52f-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="cb52f-107">Event Source</span></span>   |                                          <span data-ttu-id="cb52f-108">EDI de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="cb52f-108">BizTalk Server EDI</span></span>                                           |
|    <span data-ttu-id="cb52f-109">Componente</span><span class="sxs-lookup"><span data-stu-id="cb52f-109">Component</span></span>    |                                            <span data-ttu-id="cb52f-110">Motor de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="cb52f-110">Batching Engine</span></span>                                            |
|  <span data-ttu-id="cb52f-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="cb52f-111">Symbolic Name</span></span>  |                                     <span data-ttu-id="cb52f-112">ExceptionOccuredDuringUpgrade</span><span class="sxs-lookup"><span data-stu-id="cb52f-112">ExceptionOccuredDuringUpgrade</span></span>                                     |
|  <span data-ttu-id="cb52f-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="cb52f-113">Message Text</span></span>   | <span data-ttu-id="cb52f-114">Se produjo una excepción durante la ejecución de la orquestación del lote de actualización.</span><span class="sxs-lookup"><span data-stu-id="cb52f-114">An exception has occurred during the execution of the upgrade batch Orchestration.</span></span> <span data-ttu-id="cb52f-115">ErrorMessage = {0}</span><span class="sxs-lookup"><span data-stu-id="cb52f-115">ErrorMessage = {0}</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="cb52f-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="cb52f-116">Explanation</span></span>  
 <span data-ttu-id="cb52f-117">El evento de error,  indica que la orquestación del lote de actualización no pudo procesar correctamente el mensaje debido a la condición de error indicada en el campo Mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="cb52f-117">The Error/Warning/Information event indicates that the upgrade batch orchestration could not process the message correctly because of the error condition indicated in ErrorMessage field.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cb52f-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="cb52f-118">User Action</span></span>  
 <span data-ttu-id="cb52f-119">Para resolver este error, determine cuál es la condición de error desde el campo Mensaje de error, resuelva el error y vuelva a enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="cb52f-119">To resolve this error, determine what the error condition is from the ErrorMessage field, resolve the error, and then resubmit the message.</span></span>