---
title: Valor de indicador de prueba no válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d81d501-4020-4ff9-955c-5674a99d250b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89245453e7b1b7d8c40e33bf25a3ab3aac1933db
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991029"
---
# <a name="invalid-test-indicator-value"></a><span data-ttu-id="f3c90-102">Valor del indicador de prueba no válido.</span><span class="sxs-lookup"><span data-stu-id="f3c90-102">Invalid Test Indicator Value</span></span>
## <a name="details"></a><span data-ttu-id="f3c90-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="f3c90-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="f3c90-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="f3c90-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="f3c90-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="f3c90-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="f3c90-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="f3c90-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="f3c90-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="f3c90-107">Event Source</span></span>   | <span data-ttu-id="f3c90-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3c90-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="f3c90-109">Componente</span><span class="sxs-lookup"><span data-stu-id="f3c90-109">Component</span></span>    |                                       <span data-ttu-id="f3c90-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="f3c90-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="f3c90-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="f3c90-111">Symbolic Name</span></span>  |                       <span data-ttu-id="f3c90-112">X12Ta1InvalidTestIndicatorValueDescription</span><span class="sxs-lookup"><span data-stu-id="f3c90-112">X12Ta1InvalidTestIndicatorValueDescription</span></span>                       |
|  <span data-ttu-id="f3c90-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="f3c90-113">Message Text</span></span>   |                              <span data-ttu-id="f3c90-114">Valor del indicador de prueba no válido.</span><span class="sxs-lookup"><span data-stu-id="f3c90-114">Invalid Test Indicator Value</span></span>                              |
  
## <a name="explanation"></a><span data-ttu-id="f3c90-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="f3c90-115">Explanation</span></span>  
 <span data-ttu-id="f3c90-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el indicador de prueba del campo UNB11 no se ajustaba al tipo de datos y al número de dígitos que establece el esquema de servicio (X12ServiceSchema o EdifactServiceSchema en BaseArtifacts.dll).</span><span class="sxs-lookup"><span data-stu-id="f3c90-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the Test Indicator in the UNB11 field did not conform to the data type and number of digits established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f3c90-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="f3c90-117">User Action</span></span>  
 <span data-ttu-id="f3c90-118">Para resolver este error, asegúrese de que el campo UNB11 sea del tipo de datos EDIFACT_N y tenga 1 carácter de longitud.</span><span class="sxs-lookup"><span data-stu-id="f3c90-118">To resolve this error, make sure that the UNB11 field is of the EDIFACT_N data type and is 1 character in length.</span></span> <span data-ttu-id="f3c90-119">Vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="f3c90-119">Have the interchange resent.</span></span>