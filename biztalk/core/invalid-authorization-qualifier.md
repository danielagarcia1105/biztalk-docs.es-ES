---
title: Calificador de autorización no válido | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bc2a9f83-833f-4ea0-9421-7382ee1b1a54
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbf33e8bd42b18134bd31f02f791b306ece97272
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257444"
---
# <a name="invalid-authorization-qualifier"></a><span data-ttu-id="eea40-102">Calificador de autorización no válido.</span><span class="sxs-lookup"><span data-stu-id="eea40-102">Invalid Authorization Qualifier</span></span>
## <a name="details"></a><span data-ttu-id="eea40-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="eea40-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eea40-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="eea40-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="eea40-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="eea40-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="eea40-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="eea40-106">Event ID</span></span>|-|  
|<span data-ttu-id="eea40-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="eea40-107">Event Source</span></span>|<span data-ttu-id="eea40-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eea40-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="eea40-109">Componente</span><span class="sxs-lookup"><span data-stu-id="eea40-109">Component</span></span>|<span data-ttu-id="eea40-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="eea40-110">EDI Engine</span></span>|  
|<span data-ttu-id="eea40-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="eea40-111">Symbolic Name</span></span>|<span data-ttu-id="eea40-112">X12Ta1InvalidAuthorizationQualifierDescription</span><span class="sxs-lookup"><span data-stu-id="eea40-112">X12Ta1InvalidAuthorizationQualifierDescription</span></span>|  
|<span data-ttu-id="eea40-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="eea40-113">Message Text</span></span>|<span data-ttu-id="eea40-114">Calificador de autorización no válido.</span><span class="sxs-lookup"><span data-stu-id="eea40-114">Invalid Authorization Qualifier</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="eea40-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="eea40-115">Explanation</span></span>  
 <span data-ttu-id="eea40-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el valor del calificador de autorización en ISA01 no coincidía con ninguno de los valores de enumeración que especifica el esquema.</span><span class="sxs-lookup"><span data-stu-id="eea40-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the Authorization Qualifier in ISA01 did not match any of the enumeration values specified by the schema.</span></span> <span data-ttu-id="eea40-117">El esquema es X12ServiceSchema en BaseArtifacts.dll.</span><span class="sxs-lookup"><span data-stu-id="eea40-117">The schema is the X12ServiceSchema in BaseArtifacts.dll.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="eea40-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="eea40-118">User Action</span></span>  
 <span data-ttu-id="eea40-119">Para resolver este error, asegúrese de que el valor en el encabezado ISA01 coincide con uno de los valores de enumeración especificados por X12ServiceSchema y reenvíe el intercambio.</span><span class="sxs-lookup"><span data-stu-id="eea40-119">To resolve this error, make sure that the value in the ISA01 header matches one of the enumeration values specified by the X12ServiceSchema, and then have the interchange resent.</span></span>