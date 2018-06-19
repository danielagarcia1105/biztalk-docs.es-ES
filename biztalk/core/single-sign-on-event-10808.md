---
title: 'Inicio de sesión único: Evento 10808 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b4efc1d-f163-4440-a78e-53065c6af36c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b891a8cb076c332eca8918ece713385c1bbccc3a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277092"
---
# <a name="single-sign-on-event-10808"></a><span data-ttu-id="318a9-102">Inicio de sesión único: Evento 10808</span><span class="sxs-lookup"><span data-stu-id="318a9-102">Single Sign-On: Event 10808</span></span>
## <a name="details"></a><span data-ttu-id="318a9-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="318a9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="318a9-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="318a9-104">Product Name</span></span>|<span data-ttu-id="318a9-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="318a9-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="318a9-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="318a9-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="318a9-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="318a9-107">Event ID</span></span>|<span data-ttu-id="318a9-108">10808</span><span class="sxs-lookup"><span data-stu-id="318a9-108">10808</span></span>|  
|<span data-ttu-id="318a9-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="318a9-109">Event Source</span></span>|<span data-ttu-id="318a9-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="318a9-110">ENTSSO</span></span>|  
|<span data-ttu-id="318a9-111">Componente</span><span class="sxs-lookup"><span data-stu-id="318a9-111">Component</span></span>|<span data-ttu-id="318a9-112">N/D</span><span class="sxs-lookup"><span data-stu-id="318a9-112">N/A</span></span>|  
|<span data-ttu-id="318a9-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="318a9-113">Symbolic Name</span></span>|<span data-ttu-id="318a9-114">ENTSSO_E_HISSO_SYSTEM_NOT_ENABLED</span><span class="sxs-lookup"><span data-stu-id="318a9-114">ENTSSO_E_HISSO_SYSTEM_NOT_ENABLED</span></span>|  
|<span data-ttu-id="318a9-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="318a9-115">Message Text</span></span>|<span data-ttu-id="318a9-116">El sistema SSO no está habilitado para Inicio de sesión único iniciado por host.</span><span class="sxs-lookup"><span data-stu-id="318a9-116">The SSO system is not enabled for Host Initiated Single Sign-On.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="318a9-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="318a9-117">Explanation</span></span>  
 <span data-ttu-id="318a9-118">El sistema SSO no está habilitado para Inicio de sesión único iniciado por host.</span><span class="sxs-lookup"><span data-stu-id="318a9-118">The SSO system is not enabled for Host Initiated Single Sign-On.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="318a9-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="318a9-119">User Action</span></span>  
 <span data-ttu-id="318a9-120">Use las herramientas administrativas para configurar el inicio de sesión único iniciado por host.</span><span class="sxs-lookup"><span data-stu-id="318a9-120">Use the administrative tools to configure Host Initiated Single Sign-On.</span></span> <span data-ttu-id="318a9-121">Esto establecerá el marcador</span><span class="sxs-lookup"><span data-stu-id="318a9-121">This will set the</span></span>  
  
 <span data-ttu-id="318a9-122">SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS en la información global.</span><span class="sxs-lookup"><span data-stu-id="318a9-122">SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS flag on the global information.</span></span>