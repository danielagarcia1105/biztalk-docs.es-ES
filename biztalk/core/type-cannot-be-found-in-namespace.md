---
title: No se encuentra el tipo de espacio de nombres | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66387fa6-3ba3-499f-99d6-bb0033c68adc
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b369b3ce29b989f01f0ea95d6f32a663d7e7bc5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980774"
---
# <a name="type-cannot-be-found-in-namespace"></a><span data-ttu-id="1ceb3-102">No se encuentra el tipo en el espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="1ceb3-102">Type cannot be found in namespace</span></span>
## <a name="details"></a><span data-ttu-id="1ceb3-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="1ceb3-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="1ceb3-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="1ceb3-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="1ceb3-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="1ceb3-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="1ceb3-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="1ceb3-106">Event ID</span></span>     |                                         <span data-ttu-id="1ceb3-107">0</span><span class="sxs-lookup"><span data-stu-id="1ceb3-107">0</span></span>                                          |
|  <span data-ttu-id="1ceb3-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="1ceb3-108">Event Source</span></span>   |                                         <span data-ttu-id="1ceb3-109">0</span><span class="sxs-lookup"><span data-stu-id="1ceb3-109">0</span></span>                                          |
|    <span data-ttu-id="1ceb3-110">Componente</span><span class="sxs-lookup"><span data-stu-id="1ceb3-110">Component</span></span>    |                                         <span data-ttu-id="1ceb3-111">0</span><span class="sxs-lookup"><span data-stu-id="1ceb3-111">0</span></span>                                          |
|  <span data-ttu-id="1ceb3-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="1ceb3-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="1ceb3-113">0</span><span class="sxs-lookup"><span data-stu-id="1ceb3-113">0</span></span>                                          |
|  <span data-ttu-id="1ceb3-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="1ceb3-114">Message Text</span></span>   |                <span data-ttu-id="1ceb3-115">Error: Tipo de "{0}"no se encuentra en el espacio de nombres"{1}"</span><span class="sxs-lookup"><span data-stu-id="1ceb3-115">Error: Type "{0}" cannot be found in namespace "{1}"</span></span>                |
  
## <a name="explanation"></a><span data-ttu-id="1ceb3-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="1ceb3-116">Explanation</span></span>  
 <span data-ttu-id="1ceb3-117">Este error indica que los artefactos que se crean hacen referencias a tipos que no se encuentran en el espacio de nombres especificado.</span><span class="sxs-lookup"><span data-stu-id="1ceb3-117">This error indicates artifacts that are created are referencing types which cannot be found in the namespace specified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1ceb3-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="1ceb3-118">User Action</span></span>  
 <span data-ttu-id="1ceb3-119">Agregue una referencia que contenga el tipo que no se encuentra y vuelva a ejecutar el asistente (si es propietario del Servicio WCF que está intentando consumir).</span><span class="sxs-lookup"><span data-stu-id="1ceb3-119">Add a reference that contain the type that is not found, and run the wizard again (if you own the WCF service that you are trying to consume).</span></span> <span data-ttu-id="1ceb3-120">En caso contrario, póngase en contacto con el proveedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="1ceb3-120">Otherwise, contact the service provider.</span></span>