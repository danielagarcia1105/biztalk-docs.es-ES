---
title: 'Inicio de sesión único: Evento 10806 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 23650d6b-b6a4-4c41-96cd-476e5b0f7f63
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd3f432a408cffcbd1ccd27508550fd0888c5213
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277180"
---
# <a name="single-sign-on-event-10806"></a><span data-ttu-id="600f0-102">Inicio de sesión único: Evento 10806</span><span class="sxs-lookup"><span data-stu-id="600f0-102">Single Sign-On: Event 10806</span></span>
## <a name="details"></a><span data-ttu-id="600f0-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="600f0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="600f0-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="600f0-104">Product Name</span></span>|<span data-ttu-id="600f0-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="600f0-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="600f0-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="600f0-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="600f0-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="600f0-107">Event ID</span></span>|<span data-ttu-id="600f0-108">10806</span><span class="sxs-lookup"><span data-stu-id="600f0-108">10806</span></span>|  
|<span data-ttu-id="600f0-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="600f0-109">Event Source</span></span>|<span data-ttu-id="600f0-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="600f0-110">ENTSSO</span></span>|  
|<span data-ttu-id="600f0-111">Componente</span><span class="sxs-lookup"><span data-stu-id="600f0-111">Component</span></span>|<span data-ttu-id="600f0-112">N/D</span><span class="sxs-lookup"><span data-stu-id="600f0-112">N/A</span></span>|  
|<span data-ttu-id="600f0-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="600f0-113">Symbolic Name</span></span>|<span data-ttu-id="600f0-114">ENTSSO_E_APP_ASSIGNED_TO_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="600f0-114">ENTSSO_E_APP_ASSIGNED_TO_ADAPTER</span></span>|  
|<span data-ttu-id="600f0-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="600f0-115">Message Text</span></span>|<span data-ttu-id="600f0-116">No se puede eliminar la aplicación porque actualmente está asignada a un adaptador.</span><span class="sxs-lookup"><span data-stu-id="600f0-116">The application cannot be deleted because it is currently assigned to an adapter.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="600f0-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="600f0-117">Explanation</span></span>  
 <span data-ttu-id="600f0-118">No se puede eliminar una aplicación si está asignada a un adaptador.</span><span class="sxs-lookup"><span data-stu-id="600f0-118">An application cannot be deleted when it is assigned to an adapter.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="600f0-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="600f0-119">User Action</span></span>  
 <span data-ttu-id="600f0-120">Quite la asignación de la aplicación del adaptador y, a continuación, elimínela.</span><span class="sxs-lookup"><span data-stu-id="600f0-120">Unassign the application from the adapter, and then delete it.</span></span>