---
title: "Inicio de sesión único: Evento 10512 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4edf0512-112d-40b8-9e29-7dd67f999b6d
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a586af2b280e9d968b87a7cb3e7680a17457ca0a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10512"></a><span data-ttu-id="7e1f0-102">Inicio de sesión único: Evento 10512</span><span class="sxs-lookup"><span data-stu-id="7e1f0-102">Single Sign-On: Event 10512</span></span>
## <a name="details"></a><span data-ttu-id="7e1f0-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="7e1f0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7e1f0-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="7e1f0-104">Product Name</span></span>|<span data-ttu-id="7e1f0-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="7e1f0-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="7e1f0-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="7e1f0-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="7e1f0-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="7e1f0-107">Event ID</span></span>|<span data-ttu-id="7e1f0-108">10512</span><span class="sxs-lookup"><span data-stu-id="7e1f0-108">10512</span></span>|  
|<span data-ttu-id="7e1f0-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="7e1f0-109">Event Source</span></span>|<span data-ttu-id="7e1f0-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="7e1f0-110">ENTSSO</span></span>|  
|<span data-ttu-id="7e1f0-111">Componente</span><span class="sxs-lookup"><span data-stu-id="7e1f0-111">Component</span></span>|<span data-ttu-id="7e1f0-112">N\D</span><span class="sxs-lookup"><span data-stu-id="7e1f0-112">N\A</span></span>|  
|<span data-ttu-id="7e1f0-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7e1f0-113">Symbolic Name</span></span>|<span data-ttu-id="7e1f0-114">SSO_ERROR_LOADLIBRARY</span><span class="sxs-lookup"><span data-stu-id="7e1f0-114">SSO_ERROR_LOADLIBRARY</span></span>|  
|<span data-ttu-id="7e1f0-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7e1f0-115">Message Text</span></span>|<span data-ttu-id="7e1f0-116">No se pudo cargar %1%r</span><span class="sxs-lookup"><span data-stu-id="7e1f0-116">Failed to load %1%r</span></span><br /><br /> <span data-ttu-id="7e1f0-117">Código de error: %2.</span><span class="sxs-lookup"><span data-stu-id="7e1f0-117">Error code: %2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7e1f0-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="7e1f0-118">Explanation</span></span>  
 <span data-ttu-id="7e1f0-119">Este evento de error indica que la Biblioteca de vínculos dinámicos (DLL) no se pudo cargar en el proceso del servidor de SSO.</span><span class="sxs-lookup"><span data-stu-id="7e1f0-119">This Error event indicates that the specified Dynamic Link Library (DLL) could not be loaded into the SSO server process.</span></span> <span data-ttu-id="7e1f0-120">La falta de la DLL en el directorio de instalación de SSO (normalmente, C:\Archivos de programa\Archivos comunes\Inicio de sesión único empresarial) puede indicar que el programa de instalación no se completó correctamente o que la DLL se eliminó después de que éste se completó.</span><span class="sxs-lookup"><span data-stu-id="7e1f0-120">If the DLL is missing in the SSO installation directory, typically C:\Program Files\Common Files\Enterprise Single Sign-On, it may indicate that setup was not completed correctly, or that the DLL was deleted after setup was completed.</span></span> <span data-ttu-id="7e1f0-121">Si la DLL está presente, el servicio SSO podría tener problemas con la resolución de la ruta de acceso correcta a ella.</span><span class="sxs-lookup"><span data-stu-id="7e1f0-121">If the DLL is present, then there could be a problem with the SSO service resolving the correct path to the DLL.</span></span> <span data-ttu-id="7e1f0-122">Además, la DLL podría estar dañada.</span><span class="sxs-lookup"><span data-stu-id="7e1f0-122">Additionally, the DLL itself could be corrupted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7e1f0-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7e1f0-123">User Action</span></span>  
 <span data-ttu-id="7e1f0-124">Para resolver este error, realice una o varias de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="7e1f0-124">To resolve this error, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="7e1f0-125">Si se sospecha que puede existir un error más grave de instalación, tal vez sea necesario desinstalar el producto y volver a instalarlo.</span><span class="sxs-lookup"><span data-stu-id="7e1f0-125">If a wider failure of setup is suspected it may be necessary to uninstall and reinstall the product.</span></span>  
  
-   <span data-ttu-id="7e1f0-126">Si la única DLL falta o está dañada, intente reemplazarla y, seguidamente, reinicie el servicio.</span><span class="sxs-lookup"><span data-stu-id="7e1f0-126">If the single DLL is missing or corrupted, attempt to replace it and then restart the service.</span></span>  
  
 <span data-ttu-id="7e1f0-127">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="7e1f0-127">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="7e1f0-128">Implementación de Enterprise Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="7e1f0-128">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)