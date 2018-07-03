---
title: Los delimitadores no son únicos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c37cc55-8923-4124-9004-91ee5093df9c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d724533fb89d3f4d43654aadaf43094adb80e06
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966747"
---
# <a name="delimiters-are-not-unique"></a><span data-ttu-id="29d06-102">Los delimitadores no son únicos</span><span class="sxs-lookup"><span data-stu-id="29d06-102">Delimiters are not unique</span></span>
## <a name="details"></a><span data-ttu-id="29d06-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="29d06-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="29d06-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="29d06-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="29d06-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="29d06-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="29d06-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="29d06-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="29d06-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="29d06-107">Event Source</span></span>   | <span data-ttu-id="29d06-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29d06-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="29d06-109">Componente</span><span class="sxs-lookup"><span data-stu-id="29d06-109">Component</span></span>    |                                       <span data-ttu-id="29d06-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="29d06-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="29d06-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="29d06-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="29d06-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="29d06-112">Message Text</span></span>   |                               <span data-ttu-id="29d06-113">Los delimitadores no son únicos</span><span class="sxs-lookup"><span data-stu-id="29d06-113">Delimiters are not unique</span></span>                                |
  
## <a name="explanation"></a><span data-ttu-id="29d06-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="29d06-114">Explanation</span></span>  
 <span data-ttu-id="29d06-115">Este evento de error,  indica que la canalización de envío EDI no pudo procesar un intercambio saliente porque coincidían dos o más de los separadores identificados en el intercambio y usados para separar facetas del intercambio.</span><span class="sxs-lookup"><span data-stu-id="29d06-115">This Error/Warning/Information event indicates that the EDI send pipeline could not process an outgoing interchange because two or more of the separators identified in the interchange, and used to separate facets of the interchange, were the same.</span></span> <span data-ttu-id="29d06-116">Los separadores se identifican en el segmento ISA de un intercambio X12 y en el segmento UNA de un intercambio EDIFACT.</span><span class="sxs-lookup"><span data-stu-id="29d06-116">The separators are identified in the ISA segment of an X12 interchange and in the UNA segment of an EDIFACT interchange.</span></span> <span data-ttu-id="29d06-117">Dos o más separadores con el mismo valor pueden tener lugar en un escenario de lote conservado o si se recibe un intercambio mediante una transmisión de atravesar y posteriormente el puerto de envío lo recoge como archivo XML en el cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="29d06-117">Two or more separators with the same value can occur in a preserved batch scenario, or if an interchange is received via a passthrough transmit and then picked up by the send port as an XML file in the MessageBox.</span></span> <span data-ttu-id="29d06-118">Esta condición de error provocará un error en el procesamiento del intercambio.</span><span class="sxs-lookup"><span data-stu-id="29d06-118">This error condition will cause processing of the interchange to fail.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="29d06-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="29d06-119">User Action</span></span>  
 <span data-ttu-id="29d06-120">Para resolver este error, identifique los separadores del intercambio que tengan el mismo valor y cambie el valor de uno de los separadores.</span><span class="sxs-lookup"><span data-stu-id="29d06-120">To resolve this error, identify which separators in the interchange have the same value, and change the value of one of the separators.</span></span>