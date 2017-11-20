---
title: "Inicio de sesión único: Evento 10753 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b538083-180b-4a15-bedf-aac4fc351c30
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6fc43f8ffba195b7a0156a9004d140f1e3c585db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10753"></a><span data-ttu-id="b1fde-102">Inicio de sesión único: Evento 10753</span><span class="sxs-lookup"><span data-stu-id="b1fde-102">Single Sign-On: Event 10753</span></span>
## <a name="details"></a><span data-ttu-id="b1fde-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="b1fde-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b1fde-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="b1fde-104">Product Name</span></span>|<span data-ttu-id="b1fde-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="b1fde-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="b1fde-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="b1fde-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="b1fde-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="b1fde-107">Event ID</span></span>|<span data-ttu-id="b1fde-108">10753</span><span class="sxs-lookup"><span data-stu-id="b1fde-108">10753</span></span>|  
|<span data-ttu-id="b1fde-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="b1fde-109">Event Source</span></span>|<span data-ttu-id="b1fde-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b1fde-110">ENTSSO</span></span>|  
|<span data-ttu-id="b1fde-111">Componente</span><span class="sxs-lookup"><span data-stu-id="b1fde-111">Component</span></span>|<span data-ttu-id="b1fde-112">N/D</span><span class="sxs-lookup"><span data-stu-id="b1fde-112">N/A</span></span>|  
|<span data-ttu-id="b1fde-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b1fde-113">Symbolic Name</span></span>|<span data-ttu-id="b1fde-114">ENTSSO_E_MAPPING_EXISTS</span><span class="sxs-lookup"><span data-stu-id="b1fde-114">ENTSSO_E_MAPPING_EXISTS</span></span>|  
|<span data-ttu-id="b1fde-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b1fde-115">Message Text</span></span>|<span data-ttu-id="b1fde-116">La asignación ya existe.</span><span class="sxs-lookup"><span data-stu-id="b1fde-116">The mapping already exists.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b1fde-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="b1fde-117">Explanation</span></span>  
 <span data-ttu-id="b1fde-118">La asignación ya existe en la cuenta de Windows que se encuentra en uso o en la cuenta externa.</span><span class="sxs-lookup"><span data-stu-id="b1fde-118">This mapping already exists, either on the Windows account already in use or the external account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b1fde-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b1fde-119">User Action</span></span>  
 <span data-ttu-id="b1fde-120">Compruebe las asignaciones existentes y la asignación que intenta crear.</span><span class="sxs-lookup"><span data-stu-id="b1fde-120">Check the existing mappings and the mapping you are trying to create.</span></span> <span data-ttu-id="b1fde-121">Si la asignación que desea ya existe, use ésta y elimine la nueva.</span><span class="sxs-lookup"><span data-stu-id="b1fde-121">If the mapping you want already exists, use it and delete your new one.</span></span> <span data-ttu-id="b1fde-122">De lo contrario, elimine la asignación nueva y vuelva a crearla.</span><span class="sxs-lookup"><span data-stu-id="b1fde-122">If not, delete your new one and recreate it.</span></span>