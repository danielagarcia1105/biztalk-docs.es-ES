---
title: Valor no válido de autorización | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70d0dd75-b045-4b67-ba23-78551493f074
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 674585daa50f0adc0708a792b318bc0b736eca49
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974437"
---
# <a name="invalid-authorization-value"></a><span data-ttu-id="a52f3-102">Valor de autorización no válido.</span><span class="sxs-lookup"><span data-stu-id="a52f3-102">Invalid Authorization Value</span></span>
## <a name="details"></a><span data-ttu-id="a52f3-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a52f3-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="a52f3-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="a52f3-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="a52f3-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="a52f3-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="a52f3-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="a52f3-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="a52f3-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="a52f3-107">Event Source</span></span>   | <span data-ttu-id="a52f3-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a52f3-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="a52f3-109">Componente</span><span class="sxs-lookup"><span data-stu-id="a52f3-109">Component</span></span>    |                                       <span data-ttu-id="a52f3-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="a52f3-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="a52f3-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a52f3-111">Symbolic Name</span></span>  |                       <span data-ttu-id="a52f3-112">X12Ta1InvalidAuthorizationValueDescription</span><span class="sxs-lookup"><span data-stu-id="a52f3-112">X12Ta1InvalidAuthorizationValueDescription</span></span>                       |
|  <span data-ttu-id="a52f3-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a52f3-113">Message Text</span></span>   |                              <span data-ttu-id="a52f3-114">Valor de autorización no válido.</span><span class="sxs-lookup"><span data-stu-id="a52f3-114">Invalid Authorization Value</span></span>                               |
  
## <a name="explanation"></a><span data-ttu-id="a52f3-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="a52f3-115">Explanation</span></span>  
 <span data-ttu-id="a52f3-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el valor de la información sobre autorización en ISA02 no se ajustaba al tipo de datos que especifica el esquema (X12_AN) o no tenía el número de dígitos que requiere el esquema (10).</span><span class="sxs-lookup"><span data-stu-id="a52f3-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the Authorization Information in ISA02 did not conform to the data type specified by the schema (X12_AN), or did not have the number of digits required by the schema (10).</span></span> <span data-ttu-id="a52f3-117">El esquema es X12ServiceSchema en BaseArtifacts.dll.</span><span class="sxs-lookup"><span data-stu-id="a52f3-117">The schema is the X12ServiceSchema in BaseArtifacts.dll.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a52f3-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a52f3-118">User Action</span></span>  
 <span data-ttu-id="a52f3-119">Para resolver este error, asegúrese de que el valor del encabezado ISA02 se ajusta al tipo de datos de X12:AN y tiene 10 dígitos (con espacios finales) y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="a52f3-119">To resolve this error, make sure that the value in the ISA02 header conforms to the X12:AN data type and has 10 digits (with trailing spaces), and then have the interchange resent.</span></span>