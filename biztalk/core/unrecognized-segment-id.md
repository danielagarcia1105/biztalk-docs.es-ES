---
title: No se reconoce el Id. de segmento | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a00fe451-0a84-4dca-980c-682243fc9804
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2a3990ce9a1d913cdb9840605c6f0e34623db8b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007549"
---
# <a name="unrecognized-segment-id"></a><span data-ttu-id="a8082-102">Id. de segmento no reconocido.</span><span class="sxs-lookup"><span data-stu-id="a8082-102">Unrecognized segment ID</span></span>
## <a name="details"></a><span data-ttu-id="a8082-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a8082-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="a8082-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="a8082-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="a8082-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="a8082-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="a8082-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="a8082-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="a8082-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="a8082-107">Event Source</span></span>   | <span data-ttu-id="a8082-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8082-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="a8082-109">Componente</span><span class="sxs-lookup"><span data-stu-id="a8082-109">Component</span></span>    |                                       <span data-ttu-id="a8082-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="a8082-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="a8082-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a8082-111">Symbolic Name</span></span>  | <span data-ttu-id="a8082-112">EfactUnrecognizedSegmentIDDescription</span><span class="sxs-lookup"><span data-stu-id="a8082-112">EfactUnrecognizedSegmentIDDescription</span></span><br /><br /> <span data-ttu-id="a8082-113">X12UnrecognizedSegmentIDDescription</span><span class="sxs-lookup"><span data-stu-id="a8082-113">X12UnrecognizedSegmentIDDescription</span></span>  |
|  <span data-ttu-id="a8082-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a8082-114">Message Text</span></span>   |                                <span data-ttu-id="a8082-115">Id. de segmento no reconocido.</span><span class="sxs-lookup"><span data-stu-id="a8082-115">Unrecognized segment ID</span></span>                                 |
  
## <a name="explanation"></a><span data-ttu-id="a8082-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="a8082-116">Explanation</span></span>  
 <span data-ttu-id="a8082-117">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque un segmento de un conjunto de transacciones del intercambio no se ha definido mediante el esquema de documento correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a8082-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because a segment in a transaction set in the interchange was not defined by the corresponding document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a8082-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a8082-118">User Action</span></span>  
 <span data-ttu-id="a8082-119">Para resolver este error, pida al remitente del intercambio que quite el segmento no reconocido y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="a8082-119">To resolve this error, have the sender of the interchange remove the unrecognized segment and resend the interchange.</span></span>