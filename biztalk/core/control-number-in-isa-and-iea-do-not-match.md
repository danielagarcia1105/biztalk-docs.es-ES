---
title: Número de control de ISA e IEA no coinciden con | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f9091ea-460b-464b-acd5-8dc0488b61e5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1fa574e63444740e85cbdd9bf8ac411c495b24f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016232"
---
# <a name="control-number-in-isa-and-iea-do-not-match"></a><span data-ttu-id="7b60d-102">El número de control de ISA e IEA no coinciden.</span><span class="sxs-lookup"><span data-stu-id="7b60d-102">Control Number in ISA and IEA do not match</span></span>
## <a name="details"></a><span data-ttu-id="7b60d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="7b60d-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="7b60d-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="7b60d-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="7b60d-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="7b60d-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="7b60d-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="7b60d-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="7b60d-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="7b60d-107">Event Source</span></span>   | <span data-ttu-id="7b60d-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b60d-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="7b60d-109">Componente</span><span class="sxs-lookup"><span data-stu-id="7b60d-109">Component</span></span>    |                                       <span data-ttu-id="7b60d-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="7b60d-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="7b60d-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7b60d-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="7b60d-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7b60d-112">Message Text</span></span>   |                       <span data-ttu-id="7b60d-113">El número de control de ISA e IEA no coinciden.</span><span class="sxs-lookup"><span data-stu-id="7b60d-113">Control Number in ISA and IEA do not match</span></span>                       |
  
## <a name="explanation"></a><span data-ttu-id="7b60d-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="7b60d-114">Explanation</span></span>  
 <span data-ttu-id="7b60d-115">Este evento de error,  indica que la canalización de recepción AS2 no pudo procesar el intercambio entrante porque los números de control del intercambio contenidos en los campos ISA13 e IEA02 del intercambio no tienen el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="7b60d-115">This Error/Warning/Information event indicates that the AS2 receive pipeline could not process the incoming interchange because the interchange control numbers contained in the ISA13 and IEA02 fields of the interchange do not have the same value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7b60d-116">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7b60d-116">User Action</span></span>  
 <span data-ttu-id="7b60d-117">Para resolver este error, asegúrese de que los números de control de intercambio contenido en los campos ISA13 e IEA02 del intercambio tienen el mismo valor y, a continuación, reenvíe el intercambio.</span><span class="sxs-lookup"><span data-stu-id="7b60d-117">To resolve this error, make sure that the interchange control numbers contained in the ISA13 and IEA02 fields of the interchange have the same value, and then have the interchange resent.</span></span>