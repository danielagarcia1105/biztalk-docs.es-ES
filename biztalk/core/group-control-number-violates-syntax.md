---
title: Número de control de grupo infringe la sintaxis | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e173c914-cb5c-4369-ac2f-8f9abee420cb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6580441f828f04697c1d3896d37a6fe8c6ce356
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008933"
---
# <a name="group-control-number-violates-syntax"></a><span data-ttu-id="03d33-102">El número de control de grupo infringe la sintaxis.</span><span class="sxs-lookup"><span data-stu-id="03d33-102">Group control number violates syntax</span></span>
## <a name="details"></a><span data-ttu-id="03d33-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="03d33-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="03d33-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="03d33-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="03d33-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="03d33-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="03d33-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="03d33-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="03d33-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="03d33-107">Event Source</span></span>   | <span data-ttu-id="03d33-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03d33-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="03d33-109">Componente</span><span class="sxs-lookup"><span data-stu-id="03d33-109">Component</span></span>    |                                       <span data-ttu-id="03d33-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="03d33-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="03d33-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="03d33-111">Symbolic Name</span></span>  |                          <span data-ttu-id="03d33-112">X12FaInvalidControlNumberDescription</span><span class="sxs-lookup"><span data-stu-id="03d33-112">X12FaInvalidControlNumberDescription</span></span>                          |
|  <span data-ttu-id="03d33-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="03d33-113">Message Text</span></span>   |                          <span data-ttu-id="03d33-114">El número de control de grupo infringe la sintaxis.</span><span class="sxs-lookup"><span data-stu-id="03d33-114">Group control number violates syntax</span></span>                          |
  
## <a name="explanation"></a><span data-ttu-id="03d33-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="03d33-115">Explanation</span></span>  
 <span data-ttu-id="03d33-116">Este evento de error, advertencia o información indica que la canalización de recepción no pudo procesar el intercambio X12 entrante porque el número de control de grupo contenido en los campos GS06 y GE02 del intercambio no se ajustaban al tipo de datos o la longitud que se especifica en el esquema de servicio.</span><span class="sxs-lookup"><span data-stu-id="03d33-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because the group control number in the GS06 and GE02 fields of the interchange did not conform to the data type or length specified in the service schema.</span></span> <span data-ttu-id="03d33-117">El esquema de servicio es X12ServiceSchema en BaseArtifacts.dll.</span><span class="sxs-lookup"><span data-stu-id="03d33-117">The service schema is the X12ServiceSchema in BaseArtifacts.dll.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="03d33-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="03d33-118">User Action</span></span>  
 <span data-ttu-id="03d33-119">Para resolver este error, asegúrese de que los números de control de grupo contenidos en los campos GS06 y GE02 del intercambio se ajustan al tipo de datos (X12_N0) y la longitud (entre uno y nueve dígitos) que se especifican en el esquema de servicio y, a continuación, reenvíe el intercambio.</span><span class="sxs-lookup"><span data-stu-id="03d33-119">To resolve this error, make sure that the group control numbers contained in the GS06 and GE02 fields of the interchange conform to the data type (X12_N0) and length (between one and nine digits) specified in the service schema, and then have the interchange resent.</span></span>