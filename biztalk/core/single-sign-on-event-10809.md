---
title: 'Inicio de sesión único: Evento 10809 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7331d12b-1000-4a60-83b3-f092968e0e51
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e010c6ee391e72ec270ddbdc767bed861836cb8f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277020"
---
# <a name="single-sign-on-event-10809"></a><span data-ttu-id="eaf5d-102">Inicio de sesión único: Evento 10809</span><span class="sxs-lookup"><span data-stu-id="eaf5d-102">Single Sign-On: Event 10809</span></span>
## <a name="details"></a><span data-ttu-id="eaf5d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="eaf5d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eaf5d-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="eaf5d-104">Product Name</span></span>|<span data-ttu-id="eaf5d-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="eaf5d-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="eaf5d-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="eaf5d-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="eaf5d-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="eaf5d-107">Event ID</span></span>|<span data-ttu-id="eaf5d-108">10809</span><span class="sxs-lookup"><span data-stu-id="eaf5d-108">10809</span></span>|  
|<span data-ttu-id="eaf5d-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="eaf5d-109">Event Source</span></span>|<span data-ttu-id="eaf5d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="eaf5d-110">ENTSSO</span></span>|  
|<span data-ttu-id="eaf5d-111">Componente</span><span class="sxs-lookup"><span data-stu-id="eaf5d-111">Component</span></span>|<span data-ttu-id="eaf5d-112">N/D</span><span class="sxs-lookup"><span data-stu-id="eaf5d-112">N/A</span></span>|  
|<span data-ttu-id="eaf5d-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="eaf5d-113">Symbolic Name</span></span>|<span data-ttu-id="eaf5d-114">ENTSSO_E_HISSO_APP_NOT_ENABLED</span><span class="sxs-lookup"><span data-stu-id="eaf5d-114">ENTSSO_E_HISSO_APP_NOT_ENABLED</span></span>|  
|<span data-ttu-id="eaf5d-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="eaf5d-115">Message Text</span></span>|<span data-ttu-id="eaf5d-116">La aplicación no está habilitada para Inicio de sesión único iniciado por host.</span><span class="sxs-lookup"><span data-stu-id="eaf5d-116">The application is not enabled for Host Initiated Single Sign-On.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="eaf5d-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="eaf5d-117">Explanation</span></span>  
 <span data-ttu-id="eaf5d-118">La aplicación no está habilitada para Inicio de sesión único iniciado por host.</span><span class="sxs-lookup"><span data-stu-id="eaf5d-118">The application is not enabled for Host Initiated Single Sign-On.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="eaf5d-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="eaf5d-119">User Action</span></span>  
 <span data-ttu-id="eaf5d-120">Use las herramientas administrativas para configurar el inicio de sesión único iniciado por host.</span><span class="sxs-lookup"><span data-stu-id="eaf5d-120">Use the administrative tools to configure Host Initiated Single Sign-On.</span></span> <span data-ttu-id="eaf5d-121">Esto establecerá el marcador</span><span class="sxs-lookup"><span data-stu-id="eaf5d-121">This will set the</span></span>  
  
 <span data-ttu-id="eaf5d-122">SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="eaf5d-122">SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS flag on the application.</span></span>