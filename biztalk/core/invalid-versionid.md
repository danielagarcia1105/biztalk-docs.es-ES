---
title: "Id. de versión no válido | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 563af6e8-f496-46c9-8b5f-7b941b2d08a5
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5edd2dddc5df19d99c434ec60cad46664ba378e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-versionid"></a><span data-ttu-id="efca8-102">Id. de versión no válido.</span><span class="sxs-lookup"><span data-stu-id="efca8-102">Invalid VersionId</span></span>
## <a name="details"></a><span data-ttu-id="efca8-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="efca8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="efca8-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="efca8-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="efca8-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="efca8-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="efca8-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="efca8-106">Event ID</span></span>|-|  
|<span data-ttu-id="efca8-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="efca8-107">Event Source</span></span>|<span data-ttu-id="efca8-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efca8-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="efca8-109">Componente</span><span class="sxs-lookup"><span data-stu-id="efca8-109">Component</span></span>|<span data-ttu-id="efca8-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="efca8-110">EDI Engine</span></span>|  
|<span data-ttu-id="efca8-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="efca8-111">Symbolic Name</span></span>|<span data-ttu-id="efca8-112">X12Ta1InvalidVersionIdDescription</span><span class="sxs-lookup"><span data-stu-id="efca8-112">X12Ta1InvalidVersionIdDescription</span></span>|  
|<span data-ttu-id="efca8-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="efca8-113">Message Text</span></span>|<span data-ttu-id="efca8-114">Id. de versión no válido.</span><span class="sxs-lookup"><span data-stu-id="efca8-114">Invalid VersionId</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="efca8-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="efca8-115">Explanation</span></span>  
 <span data-ttu-id="efca8-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el identificador de versión del intercambio (el campo GS08 de un intercambio X12 o el campo UNG7 de un intercambio EDIFACT) no se ajustaba al tipo de datos y al número de dígitos que establece el esquema de servicio (X12ServiceSchema o EdifactServiceSchema en BaseArtifacts.dll).</span><span class="sxs-lookup"><span data-stu-id="efca8-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the version identifier in the interchange (the GS08 field in an X12 interchange or the UNG7 field in an EDIFACT interchange) did not conform to the data type and number of digits established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span> <span data-ttu-id="efca8-117">El campo GS08 debe ser del tipo de datos X12_AN y tener entre 1 y 12 dígitos.</span><span class="sxs-lookup"><span data-stu-id="efca8-117">The GS08 field must be of the X12_AN data type and between 1 and 12 digits.</span></span> <span data-ttu-id="efca8-118">La versión en UNG7.1 debe ser del tipo de datos EDIFACT_AN y tener entre 1 y 3 dígitos.</span><span class="sxs-lookup"><span data-stu-id="efca8-118">The version in UNG7.1 must be of the EDIFACT_AN data type and between 1 and 3 digits.</span></span> <span data-ttu-id="efca8-119">La versión en UNG7.2 debe ser del tipo de datos EDIFACT_AN y tener entre 1 y 3 dígitos.</span><span class="sxs-lookup"><span data-stu-id="efca8-119">The release in UNG7.2 must be of the EDIFACT_AN data type and between 1 and 3 digits.</span></span> <span data-ttu-id="efca8-120">El código asignado a la asociación en UNG7.3 debe ser del tipo de datos EDIFACT_AN y tener entre 1 y 6 dígitos.</span><span class="sxs-lookup"><span data-stu-id="efca8-120">The Association assigned code in UNG7.3 must be of the EDIFACT_AN data type and between 1 and 6 digits.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="efca8-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="efca8-121">User Action</span></span>  
 <span data-ttu-id="efca8-122">Para resolver este error, asegúrese de que la versión en GS08 o UNG7 se ajusta al tipo de datos y el número de dígitos que especifica el esquema de servicio y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="efca8-122">To resolve this error, make sure that the version in GS08 or UNG7 conforms to the data type and number of digits specified by the service schema, and then have the interchange resent.</span></span>