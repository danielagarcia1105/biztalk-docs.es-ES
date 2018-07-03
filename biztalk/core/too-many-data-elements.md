---
title: Demasiados elementos de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5000577d-5748-4e81-a394-86b2a780d70f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2e4668c4afacfdb9ac646d7d889320f45bcff14
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992917"
---
# <a name="too-many-data-elements"></a><span data-ttu-id="086be-102">Demasiados elementos de datos.</span><span class="sxs-lookup"><span data-stu-id="086be-102">Too many data elements</span></span>
## <a name="details"></a><span data-ttu-id="086be-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="086be-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="086be-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="086be-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="086be-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="086be-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="086be-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="086be-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="086be-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="086be-107">Event Source</span></span>   | <span data-ttu-id="086be-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="086be-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="086be-109">Componente</span><span class="sxs-lookup"><span data-stu-id="086be-109">Component</span></span>    |                                       <span data-ttu-id="086be-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="086be-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="086be-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="086be-111">Symbolic Name</span></span>  |                          <span data-ttu-id="086be-112">X12DeTooManyDataElementsDescription</span><span class="sxs-lookup"><span data-stu-id="086be-112">X12DeTooManyDataElementsDescription</span></span>                           |
|  <span data-ttu-id="086be-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="086be-113">Message Text</span></span>   |                                 <span data-ttu-id="086be-114">Demasiados elementos de datos.</span><span class="sxs-lookup"><span data-stu-id="086be-114">Too many data elements</span></span>                                 |
  
## <a name="explanation"></a><span data-ttu-id="086be-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="086be-115">Explanation</span></span>  
 <span data-ttu-id="086be-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante o que la canalización de envío no pudo procesar el intercambio saliente porque un segmento del intercambio contenía más elementos de datos de los que permitía el esquema de documento o el esquema de servicio.</span><span class="sxs-lookup"><span data-stu-id="086be-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange or the send pipeline could not process the outgoing interchange because a segment in the interchange contained more data elements than allowed by the document schema or the service schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="086be-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="086be-117">User Action</span></span>  
 <span data-ttu-id="086be-118">Para resolver este error, pida al remitente del intercambio que se asegure de que los segmentos incluyen el número necesario de elementos de datos y que quite los elementos de datos en exceso del segmento en caso necesario, hasta que el segmento se ajuste al esquema.</span><span class="sxs-lookup"><span data-stu-id="086be-118">To resolve this error, have the sender of the interchange ensure that segments include the required number of data elements, removing excess data elements from the segment if necessary, until the segment conforms to the schema.</span></span>