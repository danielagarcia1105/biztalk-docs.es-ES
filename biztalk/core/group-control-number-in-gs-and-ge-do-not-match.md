---
title: Número de control de grupo de GS y GE no coinciden con | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2419f61-2717-4347-a4be-54362330c7e3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f162bdcfd76d25a37e196c37c25cbb970fb27155
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993637"
---
# <a name="group-control-number-in-gs-and-ge-do-not-match"></a><span data-ttu-id="fa90c-102">El número de control de grupo de GS y GE no coinciden.</span><span class="sxs-lookup"><span data-stu-id="fa90c-102">Group control number in GS and GE do not match</span></span>
## <a name="details"></a><span data-ttu-id="fa90c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="fa90c-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="fa90c-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="fa90c-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="fa90c-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="fa90c-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="fa90c-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="fa90c-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="fa90c-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="fa90c-107">Event Source</span></span>   | <span data-ttu-id="fa90c-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa90c-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="fa90c-109">Componente</span><span class="sxs-lookup"><span data-stu-id="fa90c-109">Component</span></span>    |                                       <span data-ttu-id="fa90c-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="fa90c-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="fa90c-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="fa90c-111">Symbolic Name</span></span>  |                         <span data-ttu-id="fa90c-112">X12FaControlNumberMismatchDescription</span><span class="sxs-lookup"><span data-stu-id="fa90c-112">X12FaControlNumberMismatchDescription</span></span>                          |
|  <span data-ttu-id="fa90c-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="fa90c-113">Message Text</span></span>   |                     <span data-ttu-id="fa90c-114">El número de control de grupo de GS y GE no coinciden.</span><span class="sxs-lookup"><span data-stu-id="fa90c-114">Group control number in GS and GE do not match</span></span>                     |
  
## <a name="explanation"></a><span data-ttu-id="fa90c-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="fa90c-115">Explanation</span></span>  
 <span data-ttu-id="fa90c-116">Este evento de error, advertencia o información indica que la canalización de recepción no pudo procesar el intercambio X12 entrante porque los números de control contenidos en los campos GS06 y GE02 del intercambio no tienen el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="fa90c-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because the control numbers contained in the GS06 and GE02 fields of the  interchange do not have the same value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fa90c-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="fa90c-117">User Action</span></span>  
 <span data-ttu-id="fa90c-118">Para resolver este error, asegúrese de que los números de control de grupo contenidos en los campos GS06 y GE02 del intercambio tienen el mismo valor y, a continuación, reenvíe el intercambio.</span><span class="sxs-lookup"><span data-stu-id="fa90c-118">To resolve this error, make sure that the group control numbers contained in the GS06 and GE02 fields of the interchange have the same value, and then have the interchange resent.</span></span>