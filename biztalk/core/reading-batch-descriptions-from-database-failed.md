---
title: Lectura de Batchdescriptions desde la base de datos no se pudo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f959aa35-d957-45b0-bfac-1134b5087d0c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7e539cbc4a8a7227815c7d836b61b028bcee2f5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990629"
---
# <a name="reading-batch-descriptions-from-database-failed"></a><span data-ttu-id="24c7e-102">Error en la lectura de BatchDescriptions desde la base de datos</span><span class="sxs-lookup"><span data-stu-id="24c7e-102">Reading Batch Descriptions from database failed</span></span>
## <a name="details"></a><span data-ttu-id="24c7e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="24c7e-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="24c7e-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="24c7e-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="24c7e-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="24c7e-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="24c7e-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="24c7e-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="24c7e-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="24c7e-107">Event Source</span></span>   | <span data-ttu-id="24c7e-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24c7e-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="24c7e-109">Componente</span><span class="sxs-lookup"><span data-stu-id="24c7e-109">Component</span></span>    |                                       <span data-ttu-id="24c7e-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="24c7e-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="24c7e-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="24c7e-111">Symbolic Name</span></span>  |                                 <span data-ttu-id="24c7e-112">LoadBatchFiltersFailed</span><span class="sxs-lookup"><span data-stu-id="24c7e-112">LoadBatchFiltersFailed</span></span>                                 |
|  <span data-ttu-id="24c7e-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="24c7e-113">Message Text</span></span>   |     <span data-ttu-id="24c7e-114">Error en la lectura de BatchDescriptions desde la base de datos.</span><span class="sxs-lookup"><span data-stu-id="24c7e-114">Reading BatchDescriptions from database failed.</span></span> <span data-ttu-id="24c7e-115">Error: {0}.</span><span class="sxs-lookup"><span data-stu-id="24c7e-115">Error: {0}.</span></span> <span data-ttu-id="24c7e-116">Seguimiento de la pila: {1}.</span><span class="sxs-lookup"><span data-stu-id="24c7e-116">Stack Trace: {1}.</span></span>      |
  
## <a name="explanation"></a><span data-ttu-id="24c7e-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="24c7e-117">Explanation</span></span>  
 <span data-ttu-id="24c7e-118">Este evento de error, advertencia o información indica que BizTalk Server no pudo cargar los filtros especificados de los lotes configurados para comparar propiedades de contexto de mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="24c7e-118">This Error/Warning/Information event indicates BizTalk Server was unable to load the filters specified for the configured batches to compare context properties of incoming messages.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="24c7e-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="24c7e-119">User Action</span></span>  
 <span data-ttu-id="24c7e-120">Para resolver este error, asegúrese de que la base de datos de administración esté activa y sea posible conectarse a ella.</span><span class="sxs-lookup"><span data-stu-id="24c7e-120">To resolve this error, ensure that the Management database is up and can be connected.</span></span>