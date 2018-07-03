---
title: No se pueden combinar operaciones debido a una colisión de nombre | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81ddb8b7-6f7e-420c-b7c3-921c0e305326
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57bbb3b085af45ede5632e20f67d5e6c0c4e304e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992325"
---
# <a name="cannot-merge-operations-due-to-name-collision"></a><span data-ttu-id="34cc4-102">No se pueden combinar operaciones debido a una colisión de nombres</span><span class="sxs-lookup"><span data-stu-id="34cc4-102">Cannot merge operations due to name collision</span></span>
## <a name="details"></a><span data-ttu-id="34cc4-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="34cc4-103">Details</span></span>  
  
|                 |                                                                                                             |
|-----------------|-------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="34cc4-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="34cc4-104">Product Name</span></span>   |             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]              |
| <span data-ttu-id="34cc4-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="34cc4-105">Product Version</span></span> |                         [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                          |
|    <span data-ttu-id="34cc4-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="34cc4-106">Event ID</span></span>     |                                                      <span data-ttu-id="34cc4-107">0</span><span class="sxs-lookup"><span data-stu-id="34cc4-107">0</span></span>                                                      |
|  <span data-ttu-id="34cc4-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="34cc4-108">Event Source</span></span>   |                                                      <span data-ttu-id="34cc4-109">0</span><span class="sxs-lookup"><span data-stu-id="34cc4-109">0</span></span>                                                      |
|    <span data-ttu-id="34cc4-110">Componente</span><span class="sxs-lookup"><span data-stu-id="34cc4-110">Component</span></span>    |                                                      <span data-ttu-id="34cc4-111">0</span><span class="sxs-lookup"><span data-stu-id="34cc4-111">0</span></span>                                                      |
|  <span data-ttu-id="34cc4-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="34cc4-112">Symbolic Name</span></span>  |                                                      <span data-ttu-id="34cc4-113">0</span><span class="sxs-lookup"><span data-stu-id="34cc4-113">0</span></span>                                                      |
|  <span data-ttu-id="34cc4-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="34cc4-114">Message Text</span></span>   | <span data-ttu-id="34cc4-115">No se puede combinar la operación "{0}" debido a una colisión de nombre.</span><span class="sxs-lookup"><span data-stu-id="34cc4-115">Cannot merge operation "{0}" due to name collision.</span></span> <span data-ttu-id="34cc4-116">Todas las operaciones de un servicio web deben tener nombres únicos.</span><span class="sxs-lookup"><span data-stu-id="34cc4-116">All operations in a web service must have unique names.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="34cc4-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="34cc4-117">Explanation</span></span>  
 <span data-ttu-id="34cc4-118">Este error indica que el nombre de puerto o el nombre de operación de dos puertos diferentes que se están combinando son iguales.</span><span class="sxs-lookup"><span data-stu-id="34cc4-118">This error indicates the port name or the operation name of two different ports that are being merged have the same name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="34cc4-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="34cc4-119">User Action</span></span>  
 <span data-ttu-id="34cc4-120">Con el Asistente para configuración de puertos, asegúrese de que todos los puertos que se combinan tienen nombres de puerto y de operación diferentes.</span><span class="sxs-lookup"><span data-stu-id="34cc4-120">Using the Port Configuration Wizard, ensure that all the ports that are being merged have different port names and operation.</span></span>  
  
 <span data-ttu-id="34cc4-121">Para obtener más información sobre la configuración de puertos, vea los recursos siguientes en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="34cc4-121">For additional information on port configuration, see the following resource in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="34cc4-122">Cómo ejecutar al Asistente para configuración de puerto</span><span class="sxs-lookup"><span data-stu-id="34cc4-122">How to Run the Port Configuration Wizard</span></span>](../core/how-to-run-the-port-configuration-wizard.md)