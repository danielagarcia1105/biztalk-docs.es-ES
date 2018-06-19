---
title: Error de creación del mensaje de Control para el identificador de lote | Documentos de Microsoft
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
ms.openlocfilehash: 6a5650ab649e9b0957e64f3cdecc13c725d64536
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238196"
---
# <a name="creation-of-control-message-failed-for-batch-id"></a><span data-ttu-id="f0ca6-102">Error en la creación del mensaje de control para el identificador del lote</span><span class="sxs-lookup"><span data-stu-id="f0ca6-102">Creation of Control Message failed for Batch id</span></span>
## <a name="details"></a><span data-ttu-id="f0ca6-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="f0ca6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f0ca6-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="f0ca6-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="f0ca6-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="f0ca6-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="f0ca6-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="f0ca6-106">Event ID</span></span>|-|  
|<span data-ttu-id="f0ca6-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="f0ca6-107">Event Source</span></span>|<span data-ttu-id="f0ca6-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0ca6-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="f0ca6-109">Componente</span><span class="sxs-lookup"><span data-stu-id="f0ca6-109">Component</span></span>|<span data-ttu-id="f0ca6-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="f0ca6-110">EDI Engine</span></span>|  
|<span data-ttu-id="f0ca6-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="f0ca6-111">Symbolic Name</span></span>|<span data-ttu-id="f0ca6-112">CreateControlMessageFailed</span><span class="sxs-lookup"><span data-stu-id="f0ca6-112">CreateControlMessageFailed</span></span>|  
|<span data-ttu-id="f0ca6-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="f0ca6-113">Message Text</span></span>|<span data-ttu-id="f0ca6-114">Error en la creación del mensaje de control para el identificador {0} del lote.</span><span class="sxs-lookup"><span data-stu-id="f0ca6-114">Creation of Control Message failed for Batch id {0}.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f0ca6-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="f0ca6-115">Explanation</span></span>  
 <span data-ttu-id="f0ca6-116">Este evento de error, advertencia o información indica que BizTalk Server no pudo iniciar o detener un lote.</span><span class="sxs-lookup"><span data-stu-id="f0ca6-116">This Error/Warning/Information event indicates BizTalk Server was start/stop a batch.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f0ca6-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="f0ca6-117">User Action</span></span>  
 <span data-ttu-id="f0ca6-118">Para resolver este error, asegúrese de que esté presente un lote con el identificador dado en las propiedades del acuerdo contenedor y que la base de datos esté activa.</span><span class="sxs-lookup"><span data-stu-id="f0ca6-118">To resolve this error, ensure that a batch with the given Id is present in the Agreement properties of the containing Agreement and the database is up.</span></span>