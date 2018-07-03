---
title: Muy pocos elementos de datos encontrados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d6eca6c1-73ee-4b9a-be84-461051eda963
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89d82a5015d2285437363f178f88c165e3ba6333
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984781"
---
# <a name="too-few-data-elements-found"></a><span data-ttu-id="6adb4-102">No se encontraron suficientes datos de elementos.</span><span class="sxs-lookup"><span data-stu-id="6adb4-102">Too few data elements found</span></span>
## <a name="details"></a><span data-ttu-id="6adb4-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="6adb4-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="6adb4-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="6adb4-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="6adb4-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="6adb4-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="6adb4-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="6adb4-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="6adb4-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="6adb4-107">Event Source</span></span>   | <span data-ttu-id="6adb4-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6adb4-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="6adb4-109">Componente</span><span class="sxs-lookup"><span data-stu-id="6adb4-109">Component</span></span>    |                                       <span data-ttu-id="6adb4-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="6adb4-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="6adb4-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="6adb4-111">Symbolic Name</span></span>  |                        <span data-ttu-id="6adb4-112">X12FeTooFewDataElementsFoundDescription</span><span class="sxs-lookup"><span data-stu-id="6adb4-112">X12FeTooFewDataElementsFoundDescription</span></span>                         |
|  <span data-ttu-id="6adb4-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="6adb4-113">Message Text</span></span>   |                              <span data-ttu-id="6adb4-114">No se encontraron suficientes datos de elementos.</span><span class="sxs-lookup"><span data-stu-id="6adb4-114">Too few data elements found</span></span>                               |
  
## <a name="explanation"></a><span data-ttu-id="6adb4-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="6adb4-115">Explanation</span></span>  
 <span data-ttu-id="6adb4-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante o que la canalización de envío no pudo procesar el intercambio saliente porque un segmento del intercambio contenía menos elementos de datos de los que requería el esquema de documento o el esquema de servicio.</span><span class="sxs-lookup"><span data-stu-id="6adb4-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange or the send pipeline could not process the outgoing interchange because a segment in the interchange contained fewer data elements than required by the document schema or the service schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6adb4-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="6adb4-117">User Action</span></span>  
 <span data-ttu-id="6adb4-118">Para resolver este error, pida al remitente del intercambio que se asegure de que los segmentos incluyan el número requerido de elementos de datos y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="6adb4-118">To resolve this error, have the sender of the interchange ensure that segments include the required number of data elements, and then resend the interchange.</span></span>