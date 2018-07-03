---
title: No es válido el valor de propiedad bytes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8599688-9f05-4983-8850-9ac1479ce9cc
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ef443c74c47883d04bcad2c1da5bb9423f7c01d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977855"
---
# <a name="the-byte-property-value-is-not-valid"></a><span data-ttu-id="a3e7a-102">El valor de la propiedad en bytes no es válido.</span><span class="sxs-lookup"><span data-stu-id="a3e7a-102">The byte property value is not valid</span></span>
## <a name="details"></a><span data-ttu-id="a3e7a-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a3e7a-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="a3e7a-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="a3e7a-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="a3e7a-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="a3e7a-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="a3e7a-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="a3e7a-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="a3e7a-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="a3e7a-107">Event Source</span></span>   | <span data-ttu-id="a3e7a-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3e7a-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="a3e7a-109">Componente</span><span class="sxs-lookup"><span data-stu-id="a3e7a-109">Component</span></span>    |                                    <span data-ttu-id="a3e7a-110">Motor de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="a3e7a-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="a3e7a-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a3e7a-111">Symbolic Name</span></span>  |                                <span data-ttu-id="a3e7a-112">InvalidBytePropertyValue</span><span class="sxs-lookup"><span data-stu-id="a3e7a-112">InvalidBytePropertyValue</span></span>                                |
|  <span data-ttu-id="a3e7a-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a3e7a-113">Message Text</span></span>   |                          <span data-ttu-id="a3e7a-114">El valor de la propiedad en bytes no es válido.</span><span class="sxs-lookup"><span data-stu-id="a3e7a-114">The byte property value is not valid</span></span>                          |
  
## <a name="explanation"></a><span data-ttu-id="a3e7a-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="a3e7a-115">Explanation</span></span>  
 <span data-ttu-id="a3e7a-116">Este evento de error, advertencia o información indica que un valor especificado para una propiedad de una fila del cuadro de diálogo Filtro por lotes no era válido, pues la propiedad requería un valor en bytes y el valor especificado no lo era.</span><span class="sxs-lookup"><span data-stu-id="a3e7a-116">This Error/Warning/Information event indicates that a value entered for a property in a row of the Batch Filter dialog box was invalid, because the property required a byte value, but the value entered was not a byte.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a3e7a-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a3e7a-117">User Action</span></span>  
 <span data-ttu-id="a3e7a-118">Para resolver este error, abra el cuadro de diálogo Filtro por lotes de la página Configuración de creación de lotes de intercambio del cuadro de diálogo Propiedades de EDI.</span><span class="sxs-lookup"><span data-stu-id="a3e7a-118">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="a3e7a-119">Asegúrese de que el valor especificado para una propiedad que requiera un valor en bytes sea en realidad en bytes.</span><span class="sxs-lookup"><span data-stu-id="a3e7a-119">Make sure that the value entered for a property that requires a byte value is in fact a byte.</span></span>