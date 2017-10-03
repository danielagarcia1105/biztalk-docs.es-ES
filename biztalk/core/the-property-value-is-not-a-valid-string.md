---
title: "El valor de propiedad no es una cadena válida | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 78df6aca-26b5-4d49-93b0-71de19f5c9dd
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7dfcceba7944226f801101818c2bf8c96ac42ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-property-value-is-not-a-valid-string"></a><span data-ttu-id="ea25e-102">El valor de propiedad no es una cadena válida.</span><span class="sxs-lookup"><span data-stu-id="ea25e-102">The property value is not a valid string</span></span>
## <a name="details"></a><span data-ttu-id="ea25e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ea25e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ea25e-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ea25e-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="ea25e-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ea25e-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="ea25e-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ea25e-106">Event ID</span></span>|-|  
|<span data-ttu-id="ea25e-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ea25e-107">Event Source</span></span>|<span data-ttu-id="ea25e-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea25e-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="ea25e-109">Componente</span><span class="sxs-lookup"><span data-stu-id="ea25e-109">Component</span></span>|<span data-ttu-id="ea25e-110">Motor de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="ea25e-110">Batching Engine</span></span>|  
|<span data-ttu-id="ea25e-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ea25e-111">Symbolic Name</span></span>|<span data-ttu-id="ea25e-112">InvalidPropertyValue</span><span class="sxs-lookup"><span data-stu-id="ea25e-112">InvalidPropertyValue</span></span>|  
|<span data-ttu-id="ea25e-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ea25e-113">Message Text</span></span>|<span data-ttu-id="ea25e-114">El valor de propiedad no es una cadena válida.</span><span class="sxs-lookup"><span data-stu-id="ea25e-114">The property value is not a valid string</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ea25e-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="ea25e-115">Explanation</span></span>  
 <span data-ttu-id="ea25e-116">Este evento de error, indica que un valor especificado para una propiedad de una fila del cuadro de diálogo Filtro por lotes no era válido, pues la propiedad requería un valor de cadena y el valor especificado no lo era.</span><span class="sxs-lookup"><span data-stu-id="ea25e-116">This Error/Warning/Information event indicates that a value entered for a property in a row of the Batch Filter dialog box was invalid, because the property required a string value, but the value entered was not a string.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ea25e-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ea25e-117">User Action</span></span>  
 <span data-ttu-id="ea25e-118">Para resolver este error, abra el cuadro de diálogo Filtro por lotes de la página Configuración de creación de lotes de intercambio del cuadro de diálogo Propiedades de EDI.</span><span class="sxs-lookup"><span data-stu-id="ea25e-118">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="ea25e-119">Asegúrese de que el valor especificado para una propiedad de cadena sea una cadena.</span><span class="sxs-lookup"><span data-stu-id="ea25e-119">Make sure that the value entered for a string property is a string.</span></span>