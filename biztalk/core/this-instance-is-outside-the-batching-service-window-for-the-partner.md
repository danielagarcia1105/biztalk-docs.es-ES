---
title: Esta instancia está fuera del intervalo de servicio de procesamiento por lotes para el socio comercial | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e420d75-11fd-4221-9d97-814ca6e48c81
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e93e7e769a8f0e30b3753af690a69c5e6eaa9786
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278668"
---
# <a name="this-instance-is-outside-the-batching-service-window-for-the-partner"></a><span data-ttu-id="15f0d-102">Esta instancia está fuera de la ventana Servicio de procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="15f0d-102">This instance is outside the Batching Service window for the partner</span></span>
## <a name="details"></a><span data-ttu-id="15f0d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="15f0d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="15f0d-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="15f0d-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="15f0d-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="15f0d-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="15f0d-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="15f0d-106">Event ID</span></span>|-|  
|<span data-ttu-id="15f0d-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="15f0d-107">Event Source</span></span>|<span data-ttu-id="15f0d-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15f0d-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="15f0d-109">Componente</span><span class="sxs-lookup"><span data-stu-id="15f0d-109">Component</span></span>|<span data-ttu-id="15f0d-110">Motor de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="15f0d-110">Batching Engine</span></span>|  
|<span data-ttu-id="15f0d-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="15f0d-111">Symbolic Name</span></span>|<span data-ttu-id="15f0d-112">OutsideBatchingServiceWindow</span><span class="sxs-lookup"><span data-stu-id="15f0d-112">OutsideBatchingServiceWindow</span></span>|  
|<span data-ttu-id="15f0d-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="15f0d-113">Message Text</span></span>|<span data-ttu-id="15f0d-114">Esta instancia está fuera de la ventana Servicio de procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="15f0d-114">This instance is outside the Batching Service window for the partner</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="15f0d-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="15f0d-115">Explanation</span></span>  
 <span data-ttu-id="15f0d-116">Este evento de error,  indica que no se pudo iniciar una instancia de la orquestación de procesamiento por lotes porque la instancia quedó fuera del intervalo de activación para la entidad.</span><span class="sxs-lookup"><span data-stu-id="15f0d-116">This Error/Warning/Information event indicates that an instance of the batching orchestration could not be started because the instance fell outside the activation range for the party.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="15f0d-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="15f0d-117">User Action</span></span>  
 <span data-ttu-id="15f0d-118">Para resolver este error, abra la página Configuración de creación de lotes de intercambio de las Propiedades de EDI para la entidad y asegúrese de que la instancia de la orquestación se encuentra dentro del intervalo de activación.</span><span class="sxs-lookup"><span data-stu-id="15f0d-118">To resolve this error, open the Interchange Batch Creations Settings page of the EDI Properties for the party, and make sure that the orchestration instance is within the activation range.</span></span> <span data-ttu-id="15f0d-119">Si no es así, cambie la propiedad de tiempo de inicio y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="15f0d-119">If not, change the Start time property and then click **Start**.</span></span>