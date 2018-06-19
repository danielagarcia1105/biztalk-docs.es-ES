---
title: 'Inicio de sesión único: Evento 10665 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d0de9d0-9b46-4f3a-b796-1ce3de01cf4c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a7d4d5c4140448914ff77b09a692cc3a2136dfc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271156"
---
# <a name="single-sign-on-event-10665"></a><span data-ttu-id="36c6c-102">Inicio de sesión único: Evento 10665</span><span class="sxs-lookup"><span data-stu-id="36c6c-102">Single Sign-On: Event 10665</span></span>
## <a name="details"></a><span data-ttu-id="36c6c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="36c6c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="36c6c-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="36c6c-104">Product Name</span></span>|<span data-ttu-id="36c6c-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="36c6c-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="36c6c-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="36c6c-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="36c6c-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="36c6c-107">Event ID</span></span>|<span data-ttu-id="36c6c-108">10665</span><span class="sxs-lookup"><span data-stu-id="36c6c-108">10665</span></span>|  
|<span data-ttu-id="36c6c-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="36c6c-109">Event Source</span></span>|<span data-ttu-id="36c6c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="36c6c-110">ENTSSO</span></span>|  
|<span data-ttu-id="36c6c-111">Componente</span><span class="sxs-lookup"><span data-stu-id="36c6c-111">Component</span></span>|<span data-ttu-id="36c6c-112">N\D</span><span class="sxs-lookup"><span data-stu-id="36c6c-112">N\A</span></span>|  
|<span data-ttu-id="36c6c-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="36c6c-113">Symbolic Name</span></span>|<span data-ttu-id="36c6c-114">SSO_WARN_NO_PROPERTIES</span><span class="sxs-lookup"><span data-stu-id="36c6c-114">SSO_WARN_NO_PROPERTIES</span></span>|  
|<span data-ttu-id="36c6c-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="36c6c-115">Message Text</span></span>|<span data-ttu-id="36c6c-116">Error al leer las propiedades del adaptador de sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="36c6c-116">Error reading password sync adapter properties.</span></span> <span data-ttu-id="36c6c-117">Se usan los valores predeterminados.%r</span><span class="sxs-lookup"><span data-stu-id="36c6c-117">Using defaults.%r</span></span><br /><br /> <span data-ttu-id="36c6c-118">Adaptador: %1 %r</span><span class="sxs-lookup"><span data-stu-id="36c6c-118">Adapter: %1%r</span></span><br /><br /> <span data-ttu-id="36c6c-119">Código de error: %2</span><span class="sxs-lookup"><span data-stu-id="36c6c-119">Error Code: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="36c6c-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="36c6c-120">Explanation</span></span>  
 <span data-ttu-id="36c6c-121">Este evento de advertencia indica que se produjo un error al leer las propiedades predeterminadas del adaptador de sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="36c6c-121">This Warning event indicates that there was an error reading the default password sync adapter properties.</span></span> <span data-ttu-id="36c6c-122">Cada adaptador de sincronización de contraseñas tiene propiedades de configuración asociadas a él.</span><span class="sxs-lookup"><span data-stu-id="36c6c-122">Each password sync adapter has configuration properties associated with it.</span></span> <span data-ttu-id="36c6c-123">Estas propiedades se guardan en el almacén de configuración de SSO y se crean mediante las herramientas de línea de comandos o la MMC de administración de SSO cuando se crea el adaptador de sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="36c6c-123">These properties are stored in the SSO config store and are created by the SSO command line tools or the SSO Admin MMC when the password sync adapter is created.</span></span>  <span data-ttu-id="36c6c-124">Si dicho adaptador se creó a través de otro medio, es posible que falten propiedades y, por lo tanto, puede emitirse este error.</span><span class="sxs-lookup"><span data-stu-id="36c6c-124">There can be missing properties if the password sync adapter was created by any other means, then this error can be issued.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="36c6c-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="36c6c-125">User Action</span></span>  
 <span data-ttu-id="36c6c-126">Para solucionar la advertencia, realice una o varias de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="36c6c-126">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="36c6c-127">Compruebe las propiedades del adaptador de sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="36c6c-127">Verify password sync adapter properties.</span></span>  
  
-   <span data-ttu-id="36c6c-128">Vuelva a crear el adaptador de sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="36c6c-128">Recreate the password sync adapter</span></span>  
  
## <a name="more-info"></a><span data-ttu-id="36c6c-129">Más información</span><span class="sxs-lookup"><span data-stu-id="36c6c-129">More info</span></span>
  
-   <span data-ttu-id="36c6c-130">**Propiedades del adaptador de sincronización de contraseñas: Opciones**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="36c6c-130">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
  
-   [<span data-ttu-id="36c6c-131">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="36c6c-131">Password Synchronization</span></span>](../core/password-synchronization2.md)