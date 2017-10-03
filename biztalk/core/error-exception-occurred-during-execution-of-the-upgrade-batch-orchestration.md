---
title: "Se ha producido una excepción durante la ejecución de la orquestación de lote de actualización | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2221a498-98aa-43ab-bc4e-34dcbd92dcf0
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54cd439e180365010ec8881ce7165022dd7826d6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="an-exception-has-occurred-during-the-execution-of-the-upgrade-batch-orchestration"></a><span data-ttu-id="b5e13-102">Se produjo una excepción durante la ejecución de la orquestación del lote de actualización</span><span class="sxs-lookup"><span data-stu-id="b5e13-102">An exception has occurred during the execution of the upgrade batch orchestration</span></span>
## <a name="details"></a><span data-ttu-id="b5e13-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="b5e13-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b5e13-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="b5e13-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="b5e13-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="b5e13-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="b5e13-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="b5e13-106">Event ID</span></span>|-|  
|<span data-ttu-id="b5e13-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="b5e13-107">Event Source</span></span>|<span data-ttu-id="b5e13-108">EDI de [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5e13-108">[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] EDI</span></span>|  
|<span data-ttu-id="b5e13-109">Componente</span><span class="sxs-lookup"><span data-stu-id="b5e13-109">Component</span></span>|<span data-ttu-id="b5e13-110">Motor de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="b5e13-110">Batching Engine</span></span>|  
|<span data-ttu-id="b5e13-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b5e13-111">Symbolic Name</span></span>|<span data-ttu-id="b5e13-112">ExceptionOccuredDuringUpgrade</span><span class="sxs-lookup"><span data-stu-id="b5e13-112">ExceptionOccuredDuringUpgrade</span></span>|  
|<span data-ttu-id="b5e13-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b5e13-113">Message Text</span></span>|<span data-ttu-id="b5e13-114">Se produjo una excepción durante la ejecución de la orquestación del lote de actualización.</span><span class="sxs-lookup"><span data-stu-id="b5e13-114">An exception has occurred during the execution of the upgrade batch Orchestration.</span></span> <span data-ttu-id="b5e13-115">Mensaje de error: {0}</span><span class="sxs-lookup"><span data-stu-id="b5e13-115">ErrorMessage = {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b5e13-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="b5e13-116">Explanation</span></span>  
 <span data-ttu-id="b5e13-117">El evento de error,  indica que la orquestación del lote de actualización no pudo procesar correctamente el mensaje debido a la condición de error indicada en el campo Mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="b5e13-117">The Error/Warning/Information event indicates that the upgrade batch orchestration could not process the message correctly because of the error condition indicated in ErrorMessage field.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b5e13-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b5e13-118">User Action</span></span>  
 <span data-ttu-id="b5e13-119">Para resolver este error, determine cuál es la condición de error desde el campo Mensaje de error, resuelva el error y vuelva a enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="b5e13-119">To resolve this error, determine what the error condition is from the ErrorMessage field, resolve the error, and then resubmit the message.</span></span>