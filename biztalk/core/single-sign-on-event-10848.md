---
title: "Inicio de sesión único: Evento 10848 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 61888420-29a6-4c64-a884-1b074b586f21
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9511d46a43180626a31f36c9f887b0ac532e088a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10848"></a><span data-ttu-id="ad035-102">Inicio de sesión único: Evento 10848</span><span class="sxs-lookup"><span data-stu-id="ad035-102">Single Sign-On: Event 10848</span></span>
## <a name="details"></a><span data-ttu-id="ad035-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ad035-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ad035-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ad035-104">Product Name</span></span>|<span data-ttu-id="ad035-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="ad035-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="ad035-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ad035-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="ad035-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ad035-107">Event ID</span></span>|<span data-ttu-id="ad035-108">10848</span><span class="sxs-lookup"><span data-stu-id="ad035-108">10848</span></span>|  
|<span data-ttu-id="ad035-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ad035-109">Event Source</span></span>|<span data-ttu-id="ad035-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ad035-110">ENTSSO</span></span>|  
|<span data-ttu-id="ad035-111">Componente</span><span class="sxs-lookup"><span data-stu-id="ad035-111">Component</span></span>|<span data-ttu-id="ad035-112">N/D</span><span class="sxs-lookup"><span data-stu-id="ad035-112">N/A</span></span>|  
|<span data-ttu-id="ad035-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ad035-113">Symbolic Name</span></span>|<span data-ttu-id="ad035-114">ENTSSO_E_DIRECT_SYNC_NOT_ALLOWED_AMBIGUOUS</span><span class="sxs-lookup"><span data-stu-id="ad035-114">ENTSSO_E_DIRECT_SYNC_NOT_ALLOWED_AMBIGUOUS</span></span>|  
|<span data-ttu-id="ad035-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ad035-115">Message Text</span></span>|<span data-ttu-id="ad035-116">No se permite la sincronización directa de contraseñas de la aplicación porque sus campos son ambiguos.</span><span class="sxs-lookup"><span data-stu-id="ad035-116">Direct password sync is not allowed for this application because its fields are ambiguous.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ad035-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="ad035-117">Explanation</span></span>  
 <span data-ttu-id="ad035-118">Si existen dos campos, sólo uno de ellos debe marcarse para sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="ad035-118">If there are more than two fields, then one and only one must be marked for password sync.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ad035-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ad035-119">User Action</span></span>  
 <span data-ttu-id="ad035-120">Para solucionar este problema, debe eliminar la aplicación y crearla nuevamente para que respete estas pautas.</span><span class="sxs-lookup"><span data-stu-id="ad035-120">To remedy this situation, you must delete the application and recreate it so that it follows these guidelines.</span></span>