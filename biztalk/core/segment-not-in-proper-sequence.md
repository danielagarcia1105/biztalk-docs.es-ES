---
title: Segmento no tiene el orden adecuado | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6f0c0fdc-10d9-4b77-a80d-b2b8571e7665
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70b6147ea32bed7adf10640a3291ea9c75f71b1e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="segment-not-in-proper-sequence"></a><span data-ttu-id="1d428-102">El segmento no tiene el orden adecuado.</span><span class="sxs-lookup"><span data-stu-id="1d428-102">Segment Not In Proper Sequence</span></span>
## <a name="details"></a><span data-ttu-id="1d428-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="1d428-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1d428-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="1d428-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="1d428-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="1d428-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="1d428-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="1d428-106">Event ID</span></span>|-|  
|<span data-ttu-id="1d428-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="1d428-107">Event Source</span></span>|<span data-ttu-id="1d428-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d428-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="1d428-109">Componente</span><span class="sxs-lookup"><span data-stu-id="1d428-109">Component</span></span>|<span data-ttu-id="1d428-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="1d428-110">EDI Engine</span></span>|  
|<span data-ttu-id="1d428-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="1d428-111">Symbolic Name</span></span>|<span data-ttu-id="1d428-112">X12SegmentNotInProperSequenceDescription</span><span class="sxs-lookup"><span data-stu-id="1d428-112">X12SegmentNotInProperSequenceDescription</span></span>|  
|<span data-ttu-id="1d428-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="1d428-113">Message Text</span></span>|<span data-ttu-id="1d428-114">El segmento no tiene el orden adecuado.</span><span class="sxs-lookup"><span data-stu-id="1d428-114">Segment Not In Proper Sequence</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1d428-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="1d428-115">Explanation</span></span>  
 <span data-ttu-id="1d428-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio X12 entrante, pues un segmento del intercambio no guarda el orden que especifica el esquema del documento.</span><span class="sxs-lookup"><span data-stu-id="1d428-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because a segment in the interchange is out of the sequence specified by the document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1d428-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="1d428-117">User Action</span></span>  
 <span data-ttu-id="1d428-118">Para resolver este error, pida al remitente del intercambio que cambie el orden de los segmentos del intercambio para que tengan el que especifica el esquema del documento y que vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="1d428-118">To resolve this error, have the sender of the interchange rearrange the segments in the interchange so they are in the order specified by the document schema, and then resend the interchange.</span></span>