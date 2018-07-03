---
title: El valor no puede estar vacío ni nulo para operadores distintos de existe | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 44de42c8-eab7-4b13-b55a-d33eabe75c52
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da58cdbb1ba351d5f9500587facc99026a503176
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977333"
---
# <a name="the-value-cannot-be-empty-or-null-for-an-operator-other-than-exists"></a><span data-ttu-id="47b5b-102">El valor no puede estar vacío ni nulo para operadores distintos de Existe.</span><span class="sxs-lookup"><span data-stu-id="47b5b-102">The value cannot be empty or null for an operator other than Exists</span></span>
## <a name="details"></a><span data-ttu-id="47b5b-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="47b5b-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="47b5b-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="47b5b-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="47b5b-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="47b5b-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="47b5b-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="47b5b-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="47b5b-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="47b5b-107">Event Source</span></span>   | <span data-ttu-id="47b5b-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47b5b-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="47b5b-109">Componente</span><span class="sxs-lookup"><span data-stu-id="47b5b-109">Component</span></span>    |                                    <span data-ttu-id="47b5b-110">Motor de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="47b5b-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="47b5b-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="47b5b-111">Symbolic Name</span></span>  |                                <span data-ttu-id="47b5b-112">ValueCannotBeNullOrEmpty</span><span class="sxs-lookup"><span data-stu-id="47b5b-112">ValueCannotBeNullOrEmpty</span></span>                                |
|  <span data-ttu-id="47b5b-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="47b5b-113">Message Text</span></span>   |          <span data-ttu-id="47b5b-114">El valor no puede estar vacío ni nulo para operadores distintos de Existe.</span><span class="sxs-lookup"><span data-stu-id="47b5b-114">The value cannot be empty or null for an operator other than Exists</span></span>           |
  
## <a name="explanation"></a><span data-ttu-id="47b5b-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="47b5b-115">Explanation</span></span>  
 <span data-ttu-id="47b5b-116">Este evento de error indica que un valor especificado para una propiedad de una fila del cuadro de diálogo Filtro por lotes no era válido debido a que el operador no era Existe, pero el valor especificado estaba vacío o era nulo.</span><span class="sxs-lookup"><span data-stu-id="47b5b-116">This Error/Warning/Information event indicates that a value entered for a property in a row of the Batch Filter dialog box was invalid, because the operator was not Exists, but the value entered was either empty or null.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="47b5b-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="47b5b-117">User Action</span></span>  
 <span data-ttu-id="47b5b-118">Para resolver este error, abra el cuadro de diálogo Filtro por lotes de la página Configuración de creación de lotes de intercambio del cuadro de diálogo Propiedades de EDI.</span><span class="sxs-lookup"><span data-stu-id="47b5b-118">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="47b5b-119">Asegúrese de que, si el operador para una fila no es Existe, el valor especificado no está vacío ni es nulo.</span><span class="sxs-lookup"><span data-stu-id="47b5b-119">Make sure that if the operator for a row is not Exists, the value entered is neither empty nor null.</span></span>