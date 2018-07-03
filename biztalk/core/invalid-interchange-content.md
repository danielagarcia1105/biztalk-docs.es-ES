---
title: Contenido de intercambio no válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b2352c3-d233-4d79-be31-b32dde29c8ee
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc94b838a76b85c248322538328806520ad06723
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007629"
---
# <a name="invalid-interchange-content"></a><span data-ttu-id="e3822-102">Contenido de intercambio no válido.</span><span class="sxs-lookup"><span data-stu-id="e3822-102">Invalid Interchange Content</span></span>
## <a name="details"></a><span data-ttu-id="e3822-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="e3822-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="e3822-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="e3822-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="e3822-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="e3822-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="e3822-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="e3822-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="e3822-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="e3822-107">Event Source</span></span>   | <span data-ttu-id="e3822-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3822-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="e3822-109">Componente</span><span class="sxs-lookup"><span data-stu-id="e3822-109">Component</span></span>    |                                       <span data-ttu-id="e3822-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="e3822-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="e3822-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e3822-111">Symbolic Name</span></span>  |                       <span data-ttu-id="e3822-112">X12Ta1InvalidInterchangeContentDescription</span><span class="sxs-lookup"><span data-stu-id="e3822-112">X12Ta1InvalidInterchangeContentDescription</span></span>                       |
|  <span data-ttu-id="e3822-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e3822-113">Message Text</span></span>   |                              <span data-ttu-id="e3822-114">Contenido de intercambio no válido.</span><span class="sxs-lookup"><span data-stu-id="e3822-114">Invalid Interchange Content</span></span>                               |
  
## <a name="explanation"></a><span data-ttu-id="e3822-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="e3822-115">Explanation</span></span>  
 <span data-ttu-id="e3822-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante o que la canalización de envío no pudo procesar el intercambio saliente porque los datos del intercambio no superaron la validación de mensaje que realizó BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="e3822-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange or the send pipeline could not process the outgoing interchange because the data in the interchange did not pass message validation performed by BizTalk Server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e3822-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e3822-117">User Action</span></span>  
 <span data-ttu-id="e3822-118">Para resolver este error, identifique qué parte del intercambio tuvo un error de validación y qué validación tuvo el error.</span><span class="sxs-lookup"><span data-stu-id="e3822-118">To resolve this error, identify which part of the interchange failed validation, and which validation it failed.</span></span> <span data-ttu-id="e3822-119">Resuelva el problema que provocó el error de validación y reenvíe el intercambio.</span><span class="sxs-lookup"><span data-stu-id="e3822-119">Resolve the issue that caused validation to fail, and then have the interchange resent.</span></span>