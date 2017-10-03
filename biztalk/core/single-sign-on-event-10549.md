---
title: "Inicio de sesión único: Evento 10549 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a18eb63-700c-4f49-acc4-890abe2a00ff
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51a59feecdcf5daeef7013dd99eca1e778d49278
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10549"></a><span data-ttu-id="eefbb-102">Inicio de sesión único: Evento 10549</span><span class="sxs-lookup"><span data-stu-id="eefbb-102">Single Sign-On: Event 10549</span></span>
## <a name="details"></a><span data-ttu-id="eefbb-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="eefbb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eefbb-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="eefbb-104">Product Name</span></span>|<span data-ttu-id="eefbb-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="eefbb-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="eefbb-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="eefbb-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="eefbb-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="eefbb-107">Event ID</span></span>|<span data-ttu-id="eefbb-108">10549</span><span class="sxs-lookup"><span data-stu-id="eefbb-108">10549</span></span>|  
|<span data-ttu-id="eefbb-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="eefbb-109">Event Source</span></span>|<span data-ttu-id="eefbb-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="eefbb-110">ENTSSO</span></span>|  
|<span data-ttu-id="eefbb-111">Componente</span><span class="sxs-lookup"><span data-stu-id="eefbb-111">Component</span></span>|<span data-ttu-id="eefbb-112">CO</span><span class="sxs-lookup"><span data-stu-id="eefbb-112">CO</span></span>|  
|<span data-ttu-id="eefbb-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="eefbb-113">Symbolic Name</span></span>|<span data-ttu-id="eefbb-114">SSO_ERROR_CREATE_DATABASE_FAILED</span><span class="sxs-lookup"><span data-stu-id="eefbb-114">SSO_ERROR_CREATE_DATABASE_FAILED</span></span>|  
|<span data-ttu-id="eefbb-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="eefbb-115">Message Text</span></span>|<span data-ttu-id="eefbb-116">Error al crear e inicializar la base de datos de SSO.%r</span><span class="sxs-lookup"><span data-stu-id="eefbb-116">Creation and initialization of the SSO database failed.%r</span></span><br /><br /> <span data-ttu-id="eefbb-117">Nombre SQL Server: %1 %r</span><span class="sxs-lookup"><span data-stu-id="eefbb-117">SQL Server Name: %1%r</span></span><br /><br /> <span data-ttu-id="eefbb-118">Nombre de la base de datos SSO: %2 %r</span><span class="sxs-lookup"><span data-stu-id="eefbb-118">SSO Database Name: %2%r</span></span><br /><br /> <span data-ttu-id="eefbb-119">El usuario cliente: %3 %r</span><span class="sxs-lookup"><span data-stu-id="eefbb-119">Client User: %3%r</span></span><br /><br /> <span data-ttu-id="eefbb-120">Código de error: %4</span><span class="sxs-lookup"><span data-stu-id="eefbb-120">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="eefbb-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="eefbb-121">Explanation</span></span>  
 <span data-ttu-id="eefbb-122">Este error indica que no se pudo crear e inicializar la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="eefbb-122">This Error indicates that creation and initialization of the SSO database failed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="eefbb-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="eefbb-123">User Action</span></span>  
 <span data-ttu-id="eefbb-124">Para solucionar el error, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="eefbb-124">To resolve this error do the following:</span></span>  
  
-   <span data-ttu-id="eefbb-125">Compruebe si en los registros de eventos del sistema y la aplicación existen mensajes asociados.</span><span class="sxs-lookup"><span data-stu-id="eefbb-125">Check the system and application event logs for associated messages.</span></span>  
  
-   <span data-ttu-id="eefbb-126">Vuelva a ejecutar el programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="eefbb-126">Run Setup again.</span></span>  
  
 <span data-ttu-id="eefbb-127">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="eefbb-127">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="eefbb-128">Instalación de SSO</span><span class="sxs-lookup"><span data-stu-id="eefbb-128">Installing SSO</span></span>](../core/installing-sso.md)