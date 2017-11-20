---
title: Hay demasiados elementos de datos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5000577d-5748-4e81-a394-86b2a780d70f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebf1fb61e4870b2a661876bf9375b3d3fe9abdd2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="too-many-data-elements"></a><span data-ttu-id="ec9f7-102">Demasiados elementos de datos.</span><span class="sxs-lookup"><span data-stu-id="ec9f7-102">Too many data elements</span></span>
## <a name="details"></a><span data-ttu-id="ec9f7-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ec9f7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ec9f7-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ec9f7-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="ec9f7-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ec9f7-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="ec9f7-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ec9f7-106">Event ID</span></span>|-|  
|<span data-ttu-id="ec9f7-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ec9f7-107">Event Source</span></span>|<span data-ttu-id="ec9f7-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec9f7-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="ec9f7-109">Componente</span><span class="sxs-lookup"><span data-stu-id="ec9f7-109">Component</span></span>|<span data-ttu-id="ec9f7-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="ec9f7-110">EDI Engine</span></span>|  
|<span data-ttu-id="ec9f7-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ec9f7-111">Symbolic Name</span></span>|<span data-ttu-id="ec9f7-112">X12DeTooManyDataElementsDescription</span><span class="sxs-lookup"><span data-stu-id="ec9f7-112">X12DeTooManyDataElementsDescription</span></span>|  
|<span data-ttu-id="ec9f7-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ec9f7-113">Message Text</span></span>|<span data-ttu-id="ec9f7-114">Demasiados elementos de datos.</span><span class="sxs-lookup"><span data-stu-id="ec9f7-114">Too many data elements</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ec9f7-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="ec9f7-115">Explanation</span></span>  
 <span data-ttu-id="ec9f7-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante o que la canalización de envío no pudo procesar el intercambio saliente porque un segmento del intercambio contenía más elementos de datos de los que permitía el esquema de documento o el esquema de servicio.</span><span class="sxs-lookup"><span data-stu-id="ec9f7-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange or the send pipeline could not process the outgoing interchange because a segment in the interchange contained more data elements than allowed by the document schema or the service schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ec9f7-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ec9f7-117">User Action</span></span>  
 <span data-ttu-id="ec9f7-118">Para resolver este error, pida al remitente del intercambio que se asegure de que los segmentos incluyen el número necesario de elementos de datos y que quite los elementos de datos en exceso del segmento en caso necesario, hasta que el segmento se ajuste al esquema.</span><span class="sxs-lookup"><span data-stu-id="ec9f7-118">To resolve this error, have the sender of the interchange ensure that segments include the required number of data elements, removing excess data elements from the segment if necessary, until the segment conforms to the schema.</span></span>