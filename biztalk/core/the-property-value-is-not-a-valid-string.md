---
title: El valor de propiedad no es una cadena válida | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 78df6aca-26b5-4d49-93b0-71de19f5c9dd
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac165b36f741afa2a876efcf0c3e0ece22beb4f6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969813"
---
# <a name="the-property-value-is-not-a-valid-string"></a><span data-ttu-id="c3d11-102">El valor de propiedad no es una cadena válida.</span><span class="sxs-lookup"><span data-stu-id="c3d11-102">The property value is not a valid string</span></span>
## <a name="details"></a><span data-ttu-id="c3d11-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="c3d11-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="c3d11-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="c3d11-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="c3d11-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="c3d11-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="c3d11-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="c3d11-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="c3d11-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="c3d11-107">Event Source</span></span>   | <span data-ttu-id="c3d11-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3d11-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="c3d11-109">Componente</span><span class="sxs-lookup"><span data-stu-id="c3d11-109">Component</span></span>    |                                    <span data-ttu-id="c3d11-110">Motor de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="c3d11-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="c3d11-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="c3d11-111">Symbolic Name</span></span>  |                                  <span data-ttu-id="c3d11-112">InvalidPropertyValue</span><span class="sxs-lookup"><span data-stu-id="c3d11-112">InvalidPropertyValue</span></span>                                  |
|  <span data-ttu-id="c3d11-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="c3d11-113">Message Text</span></span>   |                        <span data-ttu-id="c3d11-114">El valor de propiedad no es una cadena válida.</span><span class="sxs-lookup"><span data-stu-id="c3d11-114">The property value is not a valid string</span></span>                        |
  
## <a name="explanation"></a><span data-ttu-id="c3d11-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="c3d11-115">Explanation</span></span>  
 <span data-ttu-id="c3d11-116">Este evento de error, indica que un valor especificado para una propiedad de una fila del cuadro de diálogo Filtro por lotes no era válido, pues la propiedad requería un valor de cadena y el valor especificado no lo era.</span><span class="sxs-lookup"><span data-stu-id="c3d11-116">This Error/Warning/Information event indicates that a value entered for a property in a row of the Batch Filter dialog box was invalid, because the property required a string value, but the value entered was not a string.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c3d11-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="c3d11-117">User Action</span></span>  
 <span data-ttu-id="c3d11-118">Para resolver este error, abra el cuadro de diálogo Filtro por lotes de la página Configuración de creación de lotes de intercambio del cuadro de diálogo Propiedades de EDI.</span><span class="sxs-lookup"><span data-stu-id="c3d11-118">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="c3d11-119">Asegúrese de que el valor especificado para una propiedad de cadena sea una cadena.</span><span class="sxs-lookup"><span data-stu-id="c3d11-119">Make sure that the value entered for a string property is a string.</span></span>