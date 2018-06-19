---
title: No se reconoce el identificador de segmento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a00fe451-0a84-4dca-980c-682243fc9804
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a49de4c7f800d740d9219f787a325279eac4c15
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286652"
---
# <a name="unrecognized-segment-id"></a><span data-ttu-id="109d1-102">Id. de segmento no reconocido.</span><span class="sxs-lookup"><span data-stu-id="109d1-102">Unrecognized segment ID</span></span>
## <a name="details"></a><span data-ttu-id="109d1-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="109d1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="109d1-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="109d1-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="109d1-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="109d1-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="109d1-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="109d1-106">Event ID</span></span>|-|  
|<span data-ttu-id="109d1-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="109d1-107">Event Source</span></span>|<span data-ttu-id="109d1-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="109d1-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="109d1-109">Componente</span><span class="sxs-lookup"><span data-stu-id="109d1-109">Component</span></span>|<span data-ttu-id="109d1-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="109d1-110">EDI Engine</span></span>|  
|<span data-ttu-id="109d1-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="109d1-111">Symbolic Name</span></span>|<span data-ttu-id="109d1-112">EfactUnrecognizedSegmentIDDescription</span><span class="sxs-lookup"><span data-stu-id="109d1-112">EfactUnrecognizedSegmentIDDescription</span></span><br /><br /> <span data-ttu-id="109d1-113">X12UnrecognizedSegmentIDDescription</span><span class="sxs-lookup"><span data-stu-id="109d1-113">X12UnrecognizedSegmentIDDescription</span></span>|  
|<span data-ttu-id="109d1-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="109d1-114">Message Text</span></span>|<span data-ttu-id="109d1-115">Id. de segmento no reconocido.</span><span class="sxs-lookup"><span data-stu-id="109d1-115">Unrecognized segment ID</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="109d1-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="109d1-116">Explanation</span></span>  
 <span data-ttu-id="109d1-117">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque un segmento de un conjunto de transacciones del intercambio no se ha definido mediante el esquema de documento correspondiente.</span><span class="sxs-lookup"><span data-stu-id="109d1-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because a segment in a transaction set in the interchange was not defined by the corresponding document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="109d1-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="109d1-118">User Action</span></span>  
 <span data-ttu-id="109d1-119">Para resolver este error, pida al remitente del intercambio que quite el segmento no reconocido y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="109d1-119">To resolve this error, have the sender of the interchange remove the unrecognized segment and resend the interchange.</span></span>