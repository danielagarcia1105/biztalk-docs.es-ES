---
title: "El segmento ISA debe tener una longitud mínima de 108 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57641445-cebb-4219-998d-54038d7ddf19
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ecd5c6761c6dbcc59ad6353efa2772b9eecf387
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="isa-segment-needs-to-have-a-minimum-length-of-108"></a><span data-ttu-id="6d0d1-102">El segmento ISA debe tener una longitud mínima de 108</span><span class="sxs-lookup"><span data-stu-id="6d0d1-102">ISA segment needs to have a minimum length of 108</span></span>
## <a name="details"></a><span data-ttu-id="6d0d1-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="6d0d1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6d0d1-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="6d0d1-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="6d0d1-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="6d0d1-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="6d0d1-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="6d0d1-106">Event ID</span></span>|-|  
|<span data-ttu-id="6d0d1-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="6d0d1-107">Event Source</span></span>|<span data-ttu-id="6d0d1-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d0d1-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="6d0d1-109">Componente</span><span class="sxs-lookup"><span data-stu-id="6d0d1-109">Component</span></span>|<span data-ttu-id="6d0d1-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="6d0d1-110">EDI Engine</span></span>|  
|<span data-ttu-id="6d0d1-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="6d0d1-111">Symbolic Name</span></span>|<span data-ttu-id="6d0d1-112">NseIsaSuffix1LFDescription</span><span class="sxs-lookup"><span data-stu-id="6d0d1-112">NseIsaSuffix1LFDescription</span></span>|  
|<span data-ttu-id="6d0d1-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="6d0d1-113">Message Text</span></span>|<span data-ttu-id="6d0d1-114">El segmento ISA debe tener una longitud mínima de 108. La instancia tiene {0}.</span><span class="sxs-lookup"><span data-stu-id="6d0d1-114">ISA segment needs to have a minimum length of 108, instance has {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6d0d1-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="6d0d1-115">Explanation</span></span>  
 <span data-ttu-id="6d0d1-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el segmento ISA del intercambio no se ajustaba al número de dígitos que establece el esquema de servicio (X12ServiceSchema o EdifactServiceSchema en BaseArtifacts.dll).</span><span class="sxs-lookup"><span data-stu-id="6d0d1-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the ISA segment in the interchange did not conform to the number of digits established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6d0d1-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="6d0d1-117">User Action</span></span>  
 <span data-ttu-id="6d0d1-118">Para resolver este error, asegúrese de que cada uno de los campos del segmento ISA (desde ISA01 hasta ISA16) tiene el número de dígitos mínimo requerido.</span><span class="sxs-lookup"><span data-stu-id="6d0d1-118">To resolve this error, make sure that each of the fields in the ISA segment (from ISA01 to ISA16) has the required minimum number of digits.</span></span> <span data-ttu-id="6d0d1-119">Para ver el número mínimo de dígitos, abra la consola de administración de BizTalk Server, así como el nodo Grupo de BizTalk, el nodo Aplicaciones, el nodo Aplicación EDI de BizTalk y, a continuación, el nodo de esquema. Abra Microsoft.BizTalk.Edi.BaseArtifacts.X12ServiceSchema con el nodo raíz de ISA y, a continuación, haga clic en la Vista Esquema.</span><span class="sxs-lookup"><span data-stu-id="6d0d1-119">You can see the minimum number of digits by opening the BizTalk Server Administration Console; opening the BizTalk Group node, the Applications node, the BizTalk EDI Application node, and then the schema node; opening the Microsoft.BizTalk.Edi.BaseArtifacts.X12ServiceSchema with the root node of ISA; and then clicking the Schema View.</span></span>