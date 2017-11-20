---
title: "El intercambio contenía un ISA formado Incorrectamente o el esquema de servicio no estaba disponible | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 78d285f6-26fb-4a3b-a959-a17623321b20
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84aec7600b71d48becfdeb30e34f837292c5ecfa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-interchange-contained-a-malformed-isa-or-the-service-schema-was-not-available"></a><span data-ttu-id="c0631-102">El intercambio contenía un ISA formado incorrectamente o el esquema Servicio no estaba disponible</span><span class="sxs-lookup"><span data-stu-id="c0631-102">The interchange contained a malformed ISA or the Service schema was not available</span></span>
## <a name="details"></a><span data-ttu-id="c0631-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="c0631-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c0631-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="c0631-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="c0631-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="c0631-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="c0631-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="c0631-106">Event ID</span></span>|-|  
|<span data-ttu-id="c0631-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="c0631-107">Event Source</span></span>|<span data-ttu-id="c0631-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0631-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="c0631-109">Componente</span><span class="sxs-lookup"><span data-stu-id="c0631-109">Component</span></span>|<span data-ttu-id="c0631-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="c0631-110">EDI Engine</span></span>|  
|<span data-ttu-id="c0631-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="c0631-111">Symbolic Name</span></span>|<span data-ttu-id="c0631-112">MalformedIsaError</span><span class="sxs-lookup"><span data-stu-id="c0631-112">MalformedIsaError</span></span>|  
|<span data-ttu-id="c0631-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="c0631-113">Message Text</span></span>|<span data-ttu-id="c0631-114">El intercambio contenía un ISA formado incorrectamente o el esquema Servicio no estaba disponible. Se ha rechazado completamente.</span><span class="sxs-lookup"><span data-stu-id="c0631-114">The interchange contained a malformed ISA or the Service schema was not available, it is being rejected completely</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c0631-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="c0631-115">Explanation</span></span>  
 <span data-ttu-id="c0631-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque los segmentos ISA o IEA del intercambio no se ajustaban a X12ServiceSchema, o bien X12ServiceSchema (en BaseArtifacts.dll) no estaba implementado.</span><span class="sxs-lookup"><span data-stu-id="c0631-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange, because the ISA or IEA segments in the interchange did not conform to the X12ServiceSchema, or the X12ServiceSchema (in BaseArtifacts.dll) was not deployed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c0631-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="c0631-117">User Action</span></span>  
 <span data-ttu-id="c0631-118">Para resolver este error, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="c0631-118">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="c0631-119">Pida al remitente del intercambio que cambie los segmentos ISA e IEA de modo que se ajusten a X12ServiceSchema.</span><span class="sxs-lookup"><span data-stu-id="c0631-119">Have the sender of the interchange change the ISA and IEA segments so that they conform to the X12ServiceSchema.</span></span>  
  
-   <span data-ttu-id="c0631-120">Asegúrese de que BaseArtifacts.dll incluye X12ServiceSchema y está implementado.</span><span class="sxs-lookup"><span data-stu-id="c0631-120">Ensure that BaseArtifacts.dll includes the X12ServiceSchema and is deployed.</span></span> <span data-ttu-id="c0631-121">Para ello, abra la consola de administración de BizTalk Server, el nodo Aplicación EDI de BizTalk y el nodo Esquemas. A continuación, compruebe que X12ServiceSchema aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="c0631-121">You can do so by opening the BizTalk Server Administration Console, opening the BizTalk EDI Application node and then the Schemas node, and verifying that X12ServiceSchema is listed.</span></span>