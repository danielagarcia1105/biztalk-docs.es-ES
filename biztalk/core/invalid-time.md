---
title: Hora no válida | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6942eb77-3ef1-460c-ac4f-8f1339c25d1b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 555934e0be188011a69efb3966e5316bc716c254
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023826"
---
# <a name="invalid-time"></a><span data-ttu-id="487bf-102">Hora no válida</span><span class="sxs-lookup"><span data-stu-id="487bf-102">Invalid Time</span></span>
## <a name="details"></a><span data-ttu-id="487bf-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="487bf-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="487bf-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="487bf-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="487bf-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="487bf-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="487bf-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="487bf-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="487bf-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="487bf-107">Event Source</span></span>   | <span data-ttu-id="487bf-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="487bf-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="487bf-109">Componente</span><span class="sxs-lookup"><span data-stu-id="487bf-109">Component</span></span>    |                                       <span data-ttu-id="487bf-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="487bf-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="487bf-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="487bf-111">Symbolic Name</span></span>  |                              <span data-ttu-id="487bf-112">X12Ta1InvalidTimeDescription</span><span class="sxs-lookup"><span data-stu-id="487bf-112">X12Ta1InvalidTimeDescription</span></span>                              |
|  <span data-ttu-id="487bf-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="487bf-113">Message Text</span></span>   |                                      <span data-ttu-id="487bf-114">Hora no válida</span><span class="sxs-lookup"><span data-stu-id="487bf-114">Invalid Time</span></span>                                      |
  
## <a name="explanation"></a><span data-ttu-id="487bf-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="487bf-115">Explanation</span></span>  
 <span data-ttu-id="487bf-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque un valor de hora en un elemento de datos no se ajustaba al tipo de datos que especifica el esquema EDI o el valor de hora en el encabezado del campo GS05 en un intercambio X12 no se ajusta al esquema de servicio (X12ServiceSchema in BaseArtifacts.dll).</span><span class="sxs-lookup"><span data-stu-id="487bf-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because a time value in a data element did not conform to the data type specified by the EDI schema or the time value in the GS05 field header in an X12 interchange did not conform to the service schema (X12ServiceSchema in BaseArtifacts.dll).</span></span> <span data-ttu-id="487bf-117">Para X12, el esquema de servicio define una hora en el campo GS05 según el tipo de datos X12_TM y de entre cuatro y ocho caracteres de longitud.</span><span class="sxs-lookup"><span data-stu-id="487bf-117">For X12, the service schema defines a time in the GS05 field as of the X12_TM data type and between four and eight characters in length.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="487bf-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="487bf-118">User Action</span></span>  
 <span data-ttu-id="487bf-119">Para resolver este error, asegúrese de que un valor de hora en un elemento de datos se ajusta al tipo de datos que especifica el esquema EDI o un valor de hora en el encabezado GS05 de un intercambio X12 se ajusta al esquema de servicio y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="487bf-119">To resolve this error, make sure that a time value in a data element conforms to the data type specified by the EDI schema or a time value in the GS05 header of an X12 interchange conforms to the service schema, and then have the interchange resent.</span></span>