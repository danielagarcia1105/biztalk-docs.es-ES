---
title: Error de creación del mensaje de Control para el identificador de lote | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f03078e7-46b0-4082-9d66-6b892152a12d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ba63bc570ac29f95c70b5bc6e09050e26c435b2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979805"
---
# <a name="creation-of-control-message-failed-for-batch-id"></a><span data-ttu-id="22aaf-102">Error en la creación del mensaje de control para el identificador del lote</span><span class="sxs-lookup"><span data-stu-id="22aaf-102">Creation of Control Message failed for Batch id</span></span>
## <a name="details"></a><span data-ttu-id="22aaf-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="22aaf-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="22aaf-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="22aaf-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="22aaf-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="22aaf-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="22aaf-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="22aaf-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="22aaf-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="22aaf-107">Event Source</span></span>   | <span data-ttu-id="22aaf-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22aaf-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="22aaf-109">Componente</span><span class="sxs-lookup"><span data-stu-id="22aaf-109">Component</span></span>    |                                       <span data-ttu-id="22aaf-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="22aaf-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="22aaf-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="22aaf-111">Symbolic Name</span></span>  |                               <span data-ttu-id="22aaf-112">CreateControlMessageFailed</span><span class="sxs-lookup"><span data-stu-id="22aaf-112">CreateControlMessageFailed</span></span>                               |
|  <span data-ttu-id="22aaf-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="22aaf-113">Message Text</span></span>   |                  <span data-ttu-id="22aaf-114">Error en la creación del mensaje de control para el identificador {0} del lote.</span><span class="sxs-lookup"><span data-stu-id="22aaf-114">Creation of Control Message failed for Batch id {0}.</span></span>                  |
  
## <a name="explanation"></a><span data-ttu-id="22aaf-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="22aaf-115">Explanation</span></span>  
 <span data-ttu-id="22aaf-116">Este evento de error, advertencia o información indica que BizTalk Server no pudo iniciar o detener un lote.</span><span class="sxs-lookup"><span data-stu-id="22aaf-116">This Error/Warning/Information event indicates BizTalk Server was start/stop a batch.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="22aaf-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="22aaf-117">User Action</span></span>  
 <span data-ttu-id="22aaf-118">Para resolver este error, asegúrese de que esté presente un lote con el identificador dado en las propiedades del acuerdo contenedor y que la base de datos esté activa.</span><span class="sxs-lookup"><span data-stu-id="22aaf-118">To resolve this error, ensure that a batch with the given Id is present in the Agreement properties of the containing Agreement and the database is up.</span></span>