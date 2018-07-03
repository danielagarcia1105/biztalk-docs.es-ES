---
title: Esquema no encontrado para CLR Namespace y rootName | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db283d81-1cb0-460d-ace4-49a91ceb4a02
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a830d46a439ad85e5e9e3d54afaca688dac201ca
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966349"
---
# <a name="schema-not-found-for-clr-namespace-and-rootname"></a><span data-ttu-id="dfdb8-102">Esquema no encontrado para CLR Namespace y rootName</span><span class="sxs-lookup"><span data-stu-id="dfdb8-102">Schema not found for CLR Namespace and rootName</span></span>
## <a name="details"></a><span data-ttu-id="dfdb8-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="dfdb8-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="dfdb8-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="dfdb8-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="dfdb8-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="dfdb8-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="dfdb8-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="dfdb8-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="dfdb8-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="dfdb8-107">Event Source</span></span>   | <span data-ttu-id="dfdb8-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfdb8-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="dfdb8-109">Componente</span><span class="sxs-lookup"><span data-stu-id="dfdb8-109">Component</span></span>    |                                       <span data-ttu-id="dfdb8-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="dfdb8-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="dfdb8-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="dfdb8-111">Symbolic Name</span></span>  |                               <span data-ttu-id="dfdb8-112">SchemaNotFoundForCLRAndRN</span><span class="sxs-lookup"><span data-stu-id="dfdb8-112">SchemaNotFoundForCLRAndRN</span></span>                                |
|  <span data-ttu-id="dfdb8-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="dfdb8-113">Message Text</span></span>   |              <span data-ttu-id="dfdb8-114">Esquema no encontrado para CLR Namespace = {0} y rootName = {1}</span><span class="sxs-lookup"><span data-stu-id="dfdb8-114">Schema not found for CLR Namespace = {0} and rootName = {1}</span></span>               |
  
## <a name="explanation"></a><span data-ttu-id="dfdb8-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="dfdb8-115">Explanation</span></span>  
 <span data-ttu-id="dfdb8-116">Este evento de error, advertencia o información indica que la canalización de recepción no encontró el esquema del documento mediante el nombre raíz asociado con el intercambio y el espacio de nombres asociado con la entidad que se ha resuelto para el intercambio.</span><span class="sxs-lookup"><span data-stu-id="dfdb8-116">This Error/Warning/Information event indicates that the receive pipeline could not find the document schema using the root name associated with the interchange and the namespace associated with the party that was resolved for the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dfdb8-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="dfdb8-117">User Action</span></span>  
 <span data-ttu-id="dfdb8-118">Para resolver este error, asegúrese de que el nombre raíz tomado del intercambio y el espacio de nombres determinado a partir de las propiedades de la entidad resuelta se corresponden juntos con un esquema implementado.</span><span class="sxs-lookup"><span data-stu-id="dfdb8-118">To resolve this error, ensure that the root name taken from the interchange and the namespace determined from the properties of the resolved party correspond together to a deployed schema.</span></span> <span data-ttu-id="dfdb8-119">BizTalk determina el nombre raíz a partir del tipo de documento y la versión del intercambio.</span><span class="sxs-lookup"><span data-stu-id="dfdb8-119">BizTalk determines the root name from the document type and version in the interchange.</span></span> <span data-ttu-id="dfdb8-120">BizTalk determina el esquema a partir del campo Espacio de nombres de destino predeterminado (para esquemas predeterminados) o de la cuadrícula "Habilitar definiciones de conjuntos de transacciones personalizadas" (para esquemas personalizados) en las propiedades de procesamiento de intercambio.</span><span class="sxs-lookup"><span data-stu-id="dfdb8-120">BizTalk determines the schema from the Default Target Namespace field (for default schemas) or the "Enable custom transaction set definitions" grid (for custom schemas) in the Interchange Processing Properties.</span></span>