---
title: 'Inicio de sesión único: Evento 10511 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98371982-0db5-4ae0-9f92-f05a58e23b83
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c080812d70dc78a0fe2a9b217833f961da951401
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271516"
---
# <a name="single-sign-on-event-10511"></a><span data-ttu-id="873ab-102">Inicio de sesión único: Evento 10511</span><span class="sxs-lookup"><span data-stu-id="873ab-102">Single Sign-On: Event 10511</span></span>
## <a name="details"></a><span data-ttu-id="873ab-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="873ab-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="873ab-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="873ab-104">Product Name</span></span>|<span data-ttu-id="873ab-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="873ab-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="873ab-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="873ab-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="873ab-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="873ab-107">Event ID</span></span>|<span data-ttu-id="873ab-108">10511</span><span class="sxs-lookup"><span data-stu-id="873ab-108">10511</span></span>|  
|<span data-ttu-id="873ab-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="873ab-109">Event Source</span></span>|<span data-ttu-id="873ab-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="873ab-110">ENTSSO</span></span>|  
|<span data-ttu-id="873ab-111">Componente</span><span class="sxs-lookup"><span data-stu-id="873ab-111">Component</span></span>|<span data-ttu-id="873ab-112">N\D</span><span class="sxs-lookup"><span data-stu-id="873ab-112">N\A</span></span>|  
|<span data-ttu-id="873ab-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="873ab-113">Symbolic Name</span></span>|<span data-ttu-id="873ab-114">SSO_ERROR_NO_DSN</span><span class="sxs-lookup"><span data-stu-id="873ab-114">SSO_ERROR_NO_DSN</span></span>|  
|<span data-ttu-id="873ab-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="873ab-115">Message Text</span></span>|<span data-ttu-id="873ab-116">No se encuentran los nombres de servidor SQL Server y de base de datos de SSO en el Registro.</span><span class="sxs-lookup"><span data-stu-id="873ab-116">The SQL Server and SSO database names were not found in the registry.</span></span> <span data-ttu-id="873ab-117">Use las herramientas de administración de SSO para configurar estos valores.</span><span class="sxs-lookup"><span data-stu-id="873ab-117">Use the SSO administration tools to configure these values.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="873ab-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="873ab-118">Explanation</span></span>  
 <span data-ttu-id="873ab-119">Este evento de error indica que no se encuentran los nombres de servidor SQL Server y de base de datos de SSO en el Registro.</span><span class="sxs-lookup"><span data-stu-id="873ab-119">This Error event indicates that the SQL Server and SSO database names were not found in the registry.</span></span> <span data-ttu-id="873ab-120">El servicio SSO necesita tal información para poder conectarse con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="873ab-120">The SSO service requires this information so it can connect to the SSO database.</span></span> <span data-ttu-id="873ab-121">Esta información se establece en el Registro durante la configuración.</span><span class="sxs-lookup"><span data-stu-id="873ab-121">This information is set in the registry during configuration.</span></span> <span data-ttu-id="873ab-122">Por lo tanto, el evento indica que es posible que la configuración no se haya completado correctamente o que las entradas del Registro se eliminaron una vez completada la configuración.</span><span class="sxs-lookup"><span data-stu-id="873ab-122">This may indicate that configuration did not complete correctly or that the registry entries have been deleted after configuration was completed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="873ab-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="873ab-123">User Action</span></span>  
 <span data-ttu-id="873ab-124">Para resolver este error, realice una o varias de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="873ab-124">To resolve this error, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="873ab-125">Si sospecha que existe un error de configuración más grave, quite la configuración del producto y vuelva a configurarlo mediante el programa de configuración.</span><span class="sxs-lookup"><span data-stu-id="873ab-125">If you suspect a wider configuration failure, unconfigure the product and then reconfigure using the configuration program.</span></span>  
  
-   <span data-ttu-id="873ab-126">Como alternativa, las entradas del Registro específicas faltantes se pueden establecer a través de la herramienta de línea de comandos de SSO "ssoconfig.exe" que se encuentra en el directorio de instalación de SSO (normalmente, C:\Archivos de programa\Archivos comunes\Inicio de sesión único empresarial).</span><span class="sxs-lookup"><span data-stu-id="873ab-126">Alternatively these specific missing registry entries can be set using the SSO command line tool, ssoconfig.exe located in the SSO installation directory, typically C:\Program Files\Common Files\Enterprise Single Sign-On.</span></span> <span data-ttu-id="873ab-127">Es posible que el directorio de instalación de SSO sea diferente.</span><span class="sxs-lookup"><span data-stu-id="873ab-127">Your SSO installation directory may be different.</span></span> <span data-ttu-id="873ab-128">Use la **- setDB** opción para establecer los nombres de base de datos de SQL Server y SSO necesarios.</span><span class="sxs-lookup"><span data-stu-id="873ab-128">Use the **-setDB** option to set the required SQL Server and SSO database names.</span></span>  
  
 <span data-ttu-id="873ab-129">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="873ab-129">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="873ab-130">Implementación de Enterprise Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="873ab-130">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)