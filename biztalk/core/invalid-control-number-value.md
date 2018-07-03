---
title: Valor de número de Control no válido. | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ac762e2-2d48-45e8-b4c4-2df246b7568c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09b274170505bf1b010d61fbefe9d43a51528aac
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019842"
---
# <a name="invalid-control-number-value"></a><span data-ttu-id="a9a06-102">Valor de número de control no válido.</span><span class="sxs-lookup"><span data-stu-id="a9a06-102">Invalid Control Number Value</span></span>
## <a name="details"></a><span data-ttu-id="a9a06-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a9a06-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="a9a06-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="a9a06-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="a9a06-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="a9a06-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="a9a06-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="a9a06-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="a9a06-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="a9a06-107">Event Source</span></span>   | <span data-ttu-id="a9a06-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9a06-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="a9a06-109">Componente</span><span class="sxs-lookup"><span data-stu-id="a9a06-109">Component</span></span>    |                                       <span data-ttu-id="a9a06-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="a9a06-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="a9a06-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a9a06-111">Symbolic Name</span></span>  |                       <span data-ttu-id="a9a06-112">X12Ta1InvalidControlNumberValueDescription</span><span class="sxs-lookup"><span data-stu-id="a9a06-112">X12Ta1InvalidControlNumberValueDescription</span></span>                       |
|  <span data-ttu-id="a9a06-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a9a06-113">Message Text</span></span>   |                              <span data-ttu-id="a9a06-114">Valor de número de control no válido.</span><span class="sxs-lookup"><span data-stu-id="a9a06-114">Invalid Control Number Value</span></span>                              |
  
## <a name="explanation"></a><span data-ttu-id="a9a06-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="a9a06-115">Explanation</span></span>  
 <span data-ttu-id="a9a06-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el valor de un número de control (intercambio, grupo o conjunto de transacciones) del intercambio no se ajustaba al tipo de datos o no tenía el número de dígitos correcto que especifica el esquema.</span><span class="sxs-lookup"><span data-stu-id="a9a06-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of a control number (interchange, group, or transaction set) in the interchange did not conform to the data type or did not have the correct number of digits specified by the schema.</span></span> <span data-ttu-id="a9a06-117">El esquema es X12ServiceSchema o EdifactServiceSchema en BaseArtifacts.dll.</span><span class="sxs-lookup"><span data-stu-id="a9a06-117">The schema is the X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a9a06-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a9a06-118">User Action</span></span>  
 <span data-ttu-id="a9a06-119">Para resolver este error, asegúrese de que el número de control se ajusta al tipo de datos y número de dígitos que especifica el esquema y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="a9a06-119">To resolve this error, make sure that the control number conforms to the data type and number of digits specified by the schema, and then have the interchange resent.</span></span>