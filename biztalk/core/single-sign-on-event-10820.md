---
title: "Inicio de sesión único: Evento 10820 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2da93a2c-d00d-4ca0-a0cf-453cee4bf3c3
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46a3ae1be84ca0b936fe38463e51e6385071f7a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10820"></a><span data-ttu-id="19888-102">Inicio de sesión único: Evento 10820</span><span class="sxs-lookup"><span data-stu-id="19888-102">Single Sign-On: Event 10820</span></span>
## <a name="details"></a><span data-ttu-id="19888-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="19888-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="19888-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="19888-104">Product Name</span></span>|<span data-ttu-id="19888-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="19888-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="19888-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="19888-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="19888-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="19888-107">Event ID</span></span>|<span data-ttu-id="19888-108">10820</span><span class="sxs-lookup"><span data-stu-id="19888-108">10820</span></span>|  
|<span data-ttu-id="19888-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="19888-109">Event Source</span></span>|<span data-ttu-id="19888-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="19888-110">ENTSSO</span></span>|  
|<span data-ttu-id="19888-111">Componente</span><span class="sxs-lookup"><span data-stu-id="19888-111">Component</span></span>|<span data-ttu-id="19888-112">N/D</span><span class="sxs-lookup"><span data-stu-id="19888-112">N/A</span></span>|  
|<span data-ttu-id="19888-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="19888-113">Symbolic Name</span></span>|<span data-ttu-id="19888-114">ENTSSO_E_REQUIRE_OLD_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="19888-114">ENTSSO_E_REQUIRE_OLD_PASSWORD</span></span>|  
|<span data-ttu-id="19888-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="19888-115">Message Text</span></span>|<span data-ttu-id="19888-116">Al cambiar la contraseña de una cuenta externa, el adaptador debe proporcionar la contraseña anterior.</span><span class="sxs-lookup"><span data-stu-id="19888-116">When changing the password for an external account the adapter must supply the old password.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="19888-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="19888-117">Explanation</span></span>  
 <span data-ttu-id="19888-118">Esta aplicación está configurada para que el adaptador de sincronización de contraseñas deba proporcionar la contraseña anterior.</span><span class="sxs-lookup"><span data-stu-id="19888-118">This application is configured in such a way that the password sync adapter is required to supply the old password.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="19888-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="19888-119">User Action</span></span>  
 <span data-ttu-id="19888-120">Compruebe la configuración del adaptador de sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="19888-120">Check the configuration of your password sync adapter.</span></span>