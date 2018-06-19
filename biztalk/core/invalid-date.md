---
title: Fecha no válida | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a41da9c5-9dcf-44cd-be5b-922e6c267ec3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 259456e781f5f5255f9fed8a51c8eb0569dd57b4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257396"
---
# <a name="invalid-date"></a><span data-ttu-id="46fb1-102">Fecha no válida.</span><span class="sxs-lookup"><span data-stu-id="46fb1-102">Invalid Date</span></span>
## <a name="details"></a><span data-ttu-id="46fb1-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="46fb1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="46fb1-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="46fb1-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="46fb1-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="46fb1-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="46fb1-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="46fb1-106">Event ID</span></span>|-|  
|<span data-ttu-id="46fb1-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="46fb1-107">Event Source</span></span>|<span data-ttu-id="46fb1-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46fb1-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="46fb1-109">Componente</span><span class="sxs-lookup"><span data-stu-id="46fb1-109">Component</span></span>|<span data-ttu-id="46fb1-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="46fb1-110">EDI Engine</span></span>|  
|<span data-ttu-id="46fb1-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="46fb1-111">Symbolic Name</span></span>|<span data-ttu-id="46fb1-112">X12DeInvalidDateDescription</span><span class="sxs-lookup"><span data-stu-id="46fb1-112">X12DeInvalidDateDescription</span></span>|  
|<span data-ttu-id="46fb1-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="46fb1-113">Message Text</span></span>|<span data-ttu-id="46fb1-114">Fecha no válida.</span><span class="sxs-lookup"><span data-stu-id="46fb1-114">Invalid Date</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="46fb1-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="46fb1-115">Explanation</span></span>  
 <span data-ttu-id="46fb1-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante o que la canalización de envío no pudo procesar el intercambio saliente porque un valor de fecha en un elemento de datos no se ajustaba al tipo de datos que especifica el esquema EDI o el valor de fecha en el encabezado del campo GS04 en un intercambio X12 no se ajustaba al esquema de servicio (X12ServiceSchema en BaseArtifacts.dll).</span><span class="sxs-lookup"><span data-stu-id="46fb1-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange or the send pipeline could not process the outgoing interchange because a date value in a data element did not conform to the data type specified by the EDI schema or the date value in the GS04 field header in an X12 interchange did not conform to the service schema (X12ServiceSchema in BaseArtifacts.dll).</span></span> <span data-ttu-id="46fb1-117">Para X12, el esquema de servicio define una fecha en el campo GS04 según el tipo de datos X12_DT y de entre seis y ocho caracteres de longitud.</span><span class="sxs-lookup"><span data-stu-id="46fb1-117">For X12, the service schema defines a date in the GS04 field as of the X12_DT data type and between six and eight characters in length.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="46fb1-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="46fb1-118">User Action</span></span>  
 <span data-ttu-id="46fb1-119">Para resolver este error, asegúrese de que el valor de hora en un elemento de datos se ajusta al tipo de datos que especifica el esquema EDI o el valor de fecha en el encabezado GS04 de un intercambio X12 se ajusta al esquema de servicio y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="46fb1-119">To resolve this error, make sure that the time value in a data element conforms to the data type specified by the EDI schema or the date value in the GS04 header of an X12 interchange conforms to the service schema, and then have the interchange resent.</span></span>