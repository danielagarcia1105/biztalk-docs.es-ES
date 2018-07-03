---
title: Separador de elementos de componente no válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 738a1107-86e6-4475-a61d-ed1d9ab7e5d2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 927a33124fdb624df79d3b2f99b07f61345289e9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997557"
---
# <a name="invalid-component-element-separator"></a><span data-ttu-id="66088-102">Separador de elemento de componente no válido.</span><span class="sxs-lookup"><span data-stu-id="66088-102">Invalid Component Element Separator</span></span>
## <a name="details"></a><span data-ttu-id="66088-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="66088-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="66088-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="66088-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="66088-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="66088-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="66088-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="66088-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="66088-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="66088-107">Event Source</span></span>   | <span data-ttu-id="66088-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66088-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="66088-109">Componente</span><span class="sxs-lookup"><span data-stu-id="66088-109">Component</span></span>    |                                       <span data-ttu-id="66088-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="66088-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="66088-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="66088-111">Symbolic Name</span></span>  |                   <span data-ttu-id="66088-112">X12Ta1InvalidComponentElementSeparatorDescription\\</span><span class="sxs-lookup"><span data-stu-id="66088-112">X12Ta1InvalidComponentElementSeparatorDescription\\</span></span>                   |
|  <span data-ttu-id="66088-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="66088-113">Message Text</span></span>   |                          <span data-ttu-id="66088-114">Separador de elemento de componente no válido.</span><span class="sxs-lookup"><span data-stu-id="66088-114">Invalid Component Element Separator</span></span>                           |
  
## <a name="explanation"></a><span data-ttu-id="66088-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="66088-115">Explanation</span></span>  
 <span data-ttu-id="66088-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el valor del separador de componentes del intercambio no estaba limitado a los caracteres del juego de caracteres ASCII.</span><span class="sxs-lookup"><span data-stu-id="66088-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the component separator in the interchange was not limited to the characters in the ASCII character set.</span></span> <span data-ttu-id="66088-117">En X12, el terminador de segmento es el campo ISA6.</span><span class="sxs-lookup"><span data-stu-id="66088-117">In X12, the segment terminator is the ISA16 field.</span></span> <span data-ttu-id="66088-118">En EDIFACT, el terminador de segmento es el campo UNA1.</span><span class="sxs-lookup"><span data-stu-id="66088-118">In EDIFACT, the segment terminator is the UNA1 field.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="66088-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="66088-119">User Action</span></span>  
 <span data-ttu-id="66088-120">Para resolver este error, asegúrese de que el terminador de segmento (el campo ISA16 de un intercambio X12 o el campo UNA1 de un intercambio EDIFACT) está limitado a los caracteres del juego de caracteres ASCII.</span><span class="sxs-lookup"><span data-stu-id="66088-120">To resolve this error, make sure that the segment terminator (the ISA16 field in an X12 interchange or the UNA1 field in an EDIFACT interchange) is limited to the characters in the ASCII character set.</span></span> <span data-ttu-id="66088-121">Vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="66088-121">Have the interchange resent.</span></span>