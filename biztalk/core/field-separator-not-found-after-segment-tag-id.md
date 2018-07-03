---
title: Separador de campos no se encuentra después del Id. de etiqueta de segmento | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5f6f0a74-3560-4d6d-9893-85e8426e6b17
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82511305a9df96af2bfafe81ce41fb0eaf9ab604
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36965789"
---
# <a name="field-separator-not-found-after-segment-tag-id"></a><span data-ttu-id="151e9-102">No se encontró el separador de campos después del Id. de etiqueta de segmento.</span><span class="sxs-lookup"><span data-stu-id="151e9-102">Field separator not found after segment tag id</span></span>
## <a name="details"></a><span data-ttu-id="151e9-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="151e9-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="151e9-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="151e9-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="151e9-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="151e9-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="151e9-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="151e9-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="151e9-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="151e9-107">Event Source</span></span>   | <span data-ttu-id="151e9-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="151e9-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="151e9-109">Componente</span><span class="sxs-lookup"><span data-stu-id="151e9-109">Component</span></span>    |                                       <span data-ttu-id="151e9-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="151e9-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="151e9-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="151e9-111">Symbolic Name</span></span>  |                          <span data-ttu-id="151e9-112">X12SeFsNotFoundAfterTagIdDescription</span><span class="sxs-lookup"><span data-stu-id="151e9-112">X12SeFsNotFoundAfterTagIdDescription</span></span>                          |
|  <span data-ttu-id="151e9-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="151e9-113">Message Text</span></span>   |                     <span data-ttu-id="151e9-114">No se encontró el separador de campos después del Id. de etiqueta de segmento.</span><span class="sxs-lookup"><span data-stu-id="151e9-114">Field separator not found after segment tag id</span></span>                     |
  
## <a name="explanation"></a><span data-ttu-id="151e9-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="151e9-115">Explanation</span></span>  
 <span data-ttu-id="151e9-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el intercambio contenía un segmento que incluía un identificador de segmento sin separador de elementos de datos situado inmediatamente a continuación.</span><span class="sxs-lookup"><span data-stu-id="151e9-116">This Error/Warning/Information event indicates that the receive pipeline could not process the interchange because the interchange contained a segment that had a segment identifier without a data element separator immediately following it.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="151e9-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="151e9-117">User Action</span></span>  
 <span data-ttu-id="151e9-118">Para resolver este error, asegúrese de que todos los identificadores de segmento del intercambio tengan separadores de elementos de datos situados inmediatamente a continuación de ellos y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="151e9-118">To resolve this error, ensure that all segment identifiers in the interchange have data element separators immediately following them, and then have the interchange resent.</span></span>