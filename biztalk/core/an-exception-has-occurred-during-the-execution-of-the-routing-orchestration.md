---
title: "Se ha producido una excepción durante la ejecución de la orquestación de enrutamiento | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68ec8921-ba05-496e-8dcc-fd8994fcb8b7
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e865ec091330a863cb2bab90bbafd9b891edb05
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="an-exception-has-occurred-during-the-execution-of-the-routing-orchestration"></a><span data-ttu-id="67a6c-102">Se produjo una excepción al ejecutar la orquestación de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="67a6c-102">An exception has occurred during the execution of the routing orchestration</span></span>
## <a name="details"></a><span data-ttu-id="67a6c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="67a6c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="67a6c-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="67a6c-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="67a6c-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="67a6c-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="67a6c-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="67a6c-106">Event ID</span></span>|-|  
|<span data-ttu-id="67a6c-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="67a6c-107">Event Source</span></span>|<span data-ttu-id="67a6c-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67a6c-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="67a6c-109">Componente</span><span class="sxs-lookup"><span data-stu-id="67a6c-109">Component</span></span>|<span data-ttu-id="67a6c-110">Motor de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="67a6c-110">Batching Engine</span></span>|  
|<span data-ttu-id="67a6c-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="67a6c-111">Symbolic Name</span></span>|<span data-ttu-id="67a6c-112">ExceptionOccuredDuringRouting</span><span class="sxs-lookup"><span data-stu-id="67a6c-112">ExceptionOccuredDuringRouting</span></span>|  
|<span data-ttu-id="67a6c-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="67a6c-113">Message Text</span></span>|<span data-ttu-id="67a6c-114">Se produjo una excepción al ejecutar la orquestación de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="67a6c-114">An exception has occured during the execution of the routing Orchestration.</span></span> <span data-ttu-id="67a6c-115">Mensaje de error: {0}</span><span class="sxs-lookup"><span data-stu-id="67a6c-115">ErrorMessage = {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="67a6c-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="67a6c-116">Explanation</span></span>  
 <span data-ttu-id="67a6c-117">Este evento de error,  indica que la orquestación de enrutamiento no pudo procesar correctamente cada copia del elemento de lote XML debido a la condición de error indicada en el campo Mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="67a6c-117">This Error/Warning/Information event indicates that the routing orchestration could not process each copy of the XML batch element correctly because of the error condition indicated in ErrorMessage field.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="67a6c-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="67a6c-118">User Action</span></span>  
 <span data-ttu-id="67a6c-119">Para resolver este error, determinar cuál es la condición de error desde el campo mensaje, resolver el error y vuelva a enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="67a6c-119">To resolve this error, determine what the error condition is from the ErrorMessage field, resolve the error, and resubmit the message.</span></span>