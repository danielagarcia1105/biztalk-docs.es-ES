---
title: Segmento inesperado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7169190c-8893-4076-8634-137fd43992f2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d493647a184a250120ee25e614deb82c2f062d2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998845"
---
# <a name="unexpected-segment"></a><span data-ttu-id="e1ce7-102">Segmento inesperado.</span><span class="sxs-lookup"><span data-stu-id="e1ce7-102">Unexpected segment</span></span>
## <a name="details"></a><span data-ttu-id="e1ce7-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="e1ce7-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="e1ce7-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="e1ce7-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="e1ce7-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="e1ce7-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="e1ce7-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="e1ce7-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="e1ce7-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="e1ce7-107">Event Source</span></span>   | <span data-ttu-id="e1ce7-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1ce7-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="e1ce7-109">Componente</span><span class="sxs-lookup"><span data-stu-id="e1ce7-109">Component</span></span>    |                                       <span data-ttu-id="e1ce7-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="e1ce7-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="e1ce7-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e1ce7-111">Symbolic Name</span></span>  |                            <span data-ttu-id="e1ce7-112">X12UnexpectedSegmentDescription</span><span class="sxs-lookup"><span data-stu-id="e1ce7-112">X12UnexpectedSegmentDescription</span></span>                             |
|  <span data-ttu-id="e1ce7-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e1ce7-113">Message Text</span></span>   |                                   <span data-ttu-id="e1ce7-114">Segmento inesperado.</span><span class="sxs-lookup"><span data-stu-id="e1ce7-114">Unexpected segment</span></span>                                   |
  
## <a name="explanation"></a><span data-ttu-id="e1ce7-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="e1ce7-115">Explanation</span></span>  
 <span data-ttu-id="e1ce7-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque un intercambio contiene un segmento no definido por el esquema de documento o el esquema de servicio.</span><span class="sxs-lookup"><span data-stu-id="e1ce7-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the interchange contains a segment that is not defined by either the document schema or the service schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e1ce7-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e1ce7-117">User Action</span></span>  
 <span data-ttu-id="e1ce7-118">Para resolver este error, pida al remitente del intercambio que quite el segmento inesperado del intercambio y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="e1ce7-118">To resolve this error, have the sender of the interchange remove the unexpected segment from the interchange, and then resend the interchange.</span></span>