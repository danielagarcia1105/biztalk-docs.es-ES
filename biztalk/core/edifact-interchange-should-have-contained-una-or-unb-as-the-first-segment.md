---
title: El intercambio EDIFACT debía contener UNA o UNB como primer segmento | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc43fd17-31d0-48df-93cd-524b40034764
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ee9d5100c8378b5ee411673c4c185dcf5def365
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017838"
---
# <a name="edifact-interchange-should-have-contained-una-or-unb-as-the-first-segment"></a><span data-ttu-id="22b47-102">El intercambio Edifact debía contener UNA o UNB como primer segmento</span><span class="sxs-lookup"><span data-stu-id="22b47-102">Edifact interchange should have contained UNA or UNB as the first segment</span></span>
## <a name="details"></a><span data-ttu-id="22b47-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="22b47-103">Details</span></span>  
  
|                 |                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="22b47-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="22b47-104">Product Name</span></span>   |        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]        |
| <span data-ttu-id="22b47-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="22b47-105">Product Version</span></span> |                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                    |
|    <span data-ttu-id="22b47-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="22b47-106">Event ID</span></span>     |                                                -                                                 |
|  <span data-ttu-id="22b47-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="22b47-107">Event Source</span></span>   |      <span data-ttu-id="22b47-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22b47-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>      |
|    <span data-ttu-id="22b47-109">Componente</span><span class="sxs-lookup"><span data-stu-id="22b47-109">Component</span></span>    |                                            <span data-ttu-id="22b47-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="22b47-110">EDI Engine</span></span>                                            |
|  <span data-ttu-id="22b47-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="22b47-111">Symbolic Name</span></span>  |                                                -                                                 |
|  <span data-ttu-id="22b47-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="22b47-112">Message Text</span></span>   | <span data-ttu-id="22b47-113">El intercambio Edifact debía contener UNA o UNB como primer segmento.</span><span class="sxs-lookup"><span data-stu-id="22b47-113">Edifact interchange should have contained UNA or UNB as the first segment.</span></span> <span data-ttu-id="22b47-114">En su lugar {0} encontró</span><span class="sxs-lookup"><span data-stu-id="22b47-114">Instead {0} was found</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="22b47-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="22b47-115">Explanation</span></span>  
 <span data-ttu-id="22b47-116">Este evento de Error, advertencia o información indica que la recepción de EDI canalización no pudo procesar el intercambio EDIFACT entrante debido a que el primer segmento era ni UNA ni un segmento UNB.</span><span class="sxs-lookup"><span data-stu-id="22b47-116">This Error/Warning/Information event indicates that the EDI receive pipeline could not process the incoming EDIFACT interchange because the first segment was neither a UNA nor a UNB segment.</span></span> <span data-ttu-id="22b47-117">El segmento UNA es opcional; el segmento UNB, obligatorio.</span><span class="sxs-lookup"><span data-stu-id="22b47-117">The UNA segment is optional; the UNB segment is mandatory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="22b47-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="22b47-118">User Action</span></span>  
 <span data-ttu-id="22b47-119">Para resolver este error, asegúrese de que el remitente del intercambio incluye un segmento UNA o UNB como primer segmento del intercambio y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="22b47-119">To resolve this error, ensure that the sender of the interchange includes the UNA or UNB segment as the first segment of the interchange, and then resends the interchange.</span></span>