---
title: Contenido de intercambio no válido | Documentos de Microsoft
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
ms.openlocfilehash: d03dc518406083cda1b070a3358cc4d8967f5f07
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257028"
---
# <a name="invalid-interchange-content"></a><span data-ttu-id="7ac24-102">Contenido de intercambio no válido.</span><span class="sxs-lookup"><span data-stu-id="7ac24-102">Invalid Interchange Content</span></span>
## <a name="details"></a><span data-ttu-id="7ac24-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="7ac24-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7ac24-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="7ac24-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="7ac24-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="7ac24-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="7ac24-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="7ac24-106">Event ID</span></span>|-|  
|<span data-ttu-id="7ac24-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="7ac24-107">Event Source</span></span>|<span data-ttu-id="7ac24-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ac24-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="7ac24-109">Componente</span><span class="sxs-lookup"><span data-stu-id="7ac24-109">Component</span></span>|<span data-ttu-id="7ac24-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="7ac24-110">EDI Engine</span></span>|  
|<span data-ttu-id="7ac24-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7ac24-111">Symbolic Name</span></span>|<span data-ttu-id="7ac24-112">X12Ta1InvalidInterchangeContentDescription</span><span class="sxs-lookup"><span data-stu-id="7ac24-112">X12Ta1InvalidInterchangeContentDescription</span></span>|  
|<span data-ttu-id="7ac24-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7ac24-113">Message Text</span></span>|<span data-ttu-id="7ac24-114">Contenido de intercambio no válido.</span><span class="sxs-lookup"><span data-stu-id="7ac24-114">Invalid Interchange Content</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7ac24-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="7ac24-115">Explanation</span></span>  
 <span data-ttu-id="7ac24-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante o que la canalización de envío no pudo procesar el intercambio saliente porque los datos del intercambio no superaron la validación de mensaje que realizó BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="7ac24-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange or the send pipeline could not process the outgoing interchange because the data in the interchange did not pass message validation performed by BizTalk Server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7ac24-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7ac24-117">User Action</span></span>  
 <span data-ttu-id="7ac24-118">Para resolver este error, identifique qué parte del intercambio tuvo un error de validación y qué validación tuvo el error.</span><span class="sxs-lookup"><span data-stu-id="7ac24-118">To resolve this error, identify which part of the interchange failed validation, and which validation it failed.</span></span> <span data-ttu-id="7ac24-119">Resuelva el problema que provocó el error de validación y reenvíe el intercambio.</span><span class="sxs-lookup"><span data-stu-id="7ac24-119">Resolve the issue that caused validation to fail, and then have the interchange resent.</span></span>