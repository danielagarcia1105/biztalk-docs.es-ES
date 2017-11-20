---
title: "El valor no puede ser vacío ni ser nulo para operadores distintos de existe | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 44de42c8-eab7-4b13-b55a-d33eabe75c52
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b5e257b78df8bf872764542d711637d33714349
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-value-cannot-be-empty-or-null-for-an-operator-other-than-exists"></a><span data-ttu-id="43fcb-102">El valor no puede estar vacío ni nulo para operadores distintos de Existe.</span><span class="sxs-lookup"><span data-stu-id="43fcb-102">The value cannot be empty or null for an operator other than Exists</span></span>
## <a name="details"></a><span data-ttu-id="43fcb-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="43fcb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="43fcb-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="43fcb-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="43fcb-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="43fcb-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="43fcb-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="43fcb-106">Event ID</span></span>|-|  
|<span data-ttu-id="43fcb-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="43fcb-107">Event Source</span></span>|<span data-ttu-id="43fcb-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43fcb-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="43fcb-109">Componente</span><span class="sxs-lookup"><span data-stu-id="43fcb-109">Component</span></span>|<span data-ttu-id="43fcb-110">Motor de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="43fcb-110">Batching Engine</span></span>|  
|<span data-ttu-id="43fcb-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="43fcb-111">Symbolic Name</span></span>|<span data-ttu-id="43fcb-112">ValueCannotBeNullOrEmpty</span><span class="sxs-lookup"><span data-stu-id="43fcb-112">ValueCannotBeNullOrEmpty</span></span>|  
|<span data-ttu-id="43fcb-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="43fcb-113">Message Text</span></span>|<span data-ttu-id="43fcb-114">El valor no puede estar vacío ni nulo para operadores distintos de Existe.</span><span class="sxs-lookup"><span data-stu-id="43fcb-114">The value cannot be empty or null for an operator other than Exists</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="43fcb-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="43fcb-115">Explanation</span></span>  
 <span data-ttu-id="43fcb-116">Este evento de error indica que un valor especificado para una propiedad de una fila del cuadro de diálogo Filtro por lotes no era válido debido a que el operador no era Existe, pero el valor especificado estaba vacío o era nulo.</span><span class="sxs-lookup"><span data-stu-id="43fcb-116">This Error/Warning/Information event indicates that a value entered for a property in a row of the Batch Filter dialog box was invalid, because the operator was not Exists, but the value entered was either empty or null.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="43fcb-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="43fcb-117">User Action</span></span>  
 <span data-ttu-id="43fcb-118">Para resolver este error, abra el cuadro de diálogo Filtro por lotes de la página Configuración de creación de lotes de intercambio del cuadro de diálogo Propiedades de EDI.</span><span class="sxs-lookup"><span data-stu-id="43fcb-118">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="43fcb-119">Asegúrese de que, si el operador para una fila no es Existe, el valor especificado no está vacío ni es nulo.</span><span class="sxs-lookup"><span data-stu-id="43fcb-119">Make sure that if the operator for a row is not Exists, the value entered is neither empty nor null.</span></span>