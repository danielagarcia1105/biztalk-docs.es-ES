---
title: El segmento tiene uno o más delimitadores finales en el componente o subcomponente nivel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 517f1cfc-66c1-47e6-be94-2c76c1f89230
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94b95e45cc4c6676bdbd2e787661a73547f45148
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024248"
---
# <a name="segment-has-trailing-delimiters-at-component-or-sub-component-level"></a><span data-ttu-id="179ec-102">El segmento tiene uno o más delimitadores finales en el nivel de componente o subcomponente.</span><span class="sxs-lookup"><span data-stu-id="179ec-102">Segment has trailing delimiter(s) at component or sub-component level</span></span>
## <a name="details"></a><span data-ttu-id="179ec-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="179ec-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="179ec-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="179ec-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="179ec-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="179ec-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="179ec-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="179ec-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="179ec-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="179ec-107">Event Source</span></span>   | <span data-ttu-id="179ec-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="179ec-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="179ec-109">Componente</span><span class="sxs-lookup"><span data-stu-id="179ec-109">Component</span></span>    |                                       <span data-ttu-id="179ec-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="179ec-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="179ec-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="179ec-111">Symbolic Name</span></span>  |                      <span data-ttu-id="179ec-112">X12SeSegmentHasTrailingDelimiterDescription</span><span class="sxs-lookup"><span data-stu-id="179ec-112">X12SeSegmentHasTrailingDelimiterDescription</span></span>                       |
|  <span data-ttu-id="179ec-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="179ec-113">Message Text</span></span>   |         <span data-ttu-id="179ec-114">El segmento tiene uno o más delimitadores finales en el nivel de componente o subcomponente.</span><span class="sxs-lookup"><span data-stu-id="179ec-114">Segment has trailing delimiter(s) at component or sub-component level</span></span>          |
  
## <a name="explanation"></a><span data-ttu-id="179ec-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="179ec-115">Explanation</span></span>  
 <span data-ttu-id="179ec-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el intercambio contenía delimitadores finales y estos no están habilitados para la entidad como remitente del intercambio.</span><span class="sxs-lookup"><span data-stu-id="179ec-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the interchange contained trailing delimiters, but trailing delimiters were not enabled for the party as interchange sender.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="179ec-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="179ec-117">User Action</span></span>  
 <span data-ttu-id="179ec-118">Para resolver este error, habilite los separadores finales tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="179ec-118">To resolve this error, enable trailing separators as follows:</span></span>  
  
1.  <span data-ttu-id="179ec-119">Abra la consola de administración de BizTalk Server, vaya a la carpeta Entidades y abra las Propiedades de EDI para la entidad.</span><span class="sxs-lookup"><span data-stu-id="179ec-119">Open the BizTalk Server Administration Console, move to the Parties folder, and open the EDI Properties for the party.</span></span>  
  
2.  <span data-ttu-id="179ec-120">Vaya a la página Validación y generación de confirmación para X12 o EDIFACT, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="179ec-120">Move to the Validation and ACK Generation page for X12 or EDIFACT, as appropriate.</span></span>  
  
3.  <span data-ttu-id="179ec-121">Haga clic en "Permitir separadores finales".</span><span class="sxs-lookup"><span data-stu-id="179ec-121">Click "Allow trailing separators".</span></span>