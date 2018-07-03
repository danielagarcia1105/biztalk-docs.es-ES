---
title: 'De sesión único: Evento 10511 | Microsoft Docs'
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
ms.openlocfilehash: 828dab394e773f99b31ca23f19b2816ab8558a10
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992093"
---
# <a name="single-sign-on-event-10511"></a><span data-ttu-id="a2035-102">De sesión único: Evento 10511</span><span class="sxs-lookup"><span data-stu-id="a2035-102">Single Sign-On: Event 10511</span></span>
## <a name="details"></a><span data-ttu-id="a2035-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a2035-103">Details</span></span>  

|                 |                                                                                                                                   |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="a2035-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="a2035-104">Product Name</span></span>   |                                                     <span data-ttu-id="a2035-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="a2035-105">Enterprise Single Sign-On</span></span>                                                     |
| <span data-ttu-id="a2035-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="a2035-106">Product Version</span></span> |                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                     |
|    <span data-ttu-id="a2035-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="a2035-107">Event ID</span></span>     |                                                               <span data-ttu-id="a2035-108">10511</span><span class="sxs-lookup"><span data-stu-id="a2035-108">10511</span></span>                                                               |
|  <span data-ttu-id="a2035-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="a2035-109">Event Source</span></span>   |                                                              <span data-ttu-id="a2035-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a2035-110">ENTSSO</span></span>                                                               |
|    <span data-ttu-id="a2035-111">Componente</span><span class="sxs-lookup"><span data-stu-id="a2035-111">Component</span></span>    |                                                                <span data-ttu-id="a2035-112">N\D</span><span class="sxs-lookup"><span data-stu-id="a2035-112">N\A</span></span>                                                                |
|  <span data-ttu-id="a2035-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a2035-113">Symbolic Name</span></span>  |                                                         <span data-ttu-id="a2035-114">SSO_ERROR_NO_DSN</span><span class="sxs-lookup"><span data-stu-id="a2035-114">SSO_ERROR_NO_DSN</span></span>                                                          |
|  <span data-ttu-id="a2035-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a2035-115">Message Text</span></span>   | <span data-ttu-id="a2035-116">No se encuentran los nombres de servidor SQL Server y de base de datos de SSO en el Registro.</span><span class="sxs-lookup"><span data-stu-id="a2035-116">The SQL Server and SSO database names were not found in the registry.</span></span> <span data-ttu-id="a2035-117">Use las herramientas de administración de SSO para configurar estos valores.</span><span class="sxs-lookup"><span data-stu-id="a2035-117">Use the SSO administration tools to configure these values.</span></span> |

## <a name="explanation"></a><span data-ttu-id="a2035-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="a2035-118">Explanation</span></span>  
 <span data-ttu-id="a2035-119">Este evento de error indica que no se encuentran los nombres de servidor SQL Server y de base de datos de SSO en el Registro.</span><span class="sxs-lookup"><span data-stu-id="a2035-119">This Error event indicates that the SQL Server and SSO database names were not found in the registry.</span></span> <span data-ttu-id="a2035-120">El servicio SSO necesita tal información para poder conectarse con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="a2035-120">The SSO service requires this information so it can connect to the SSO database.</span></span> <span data-ttu-id="a2035-121">Esta información se establece en el Registro durante la configuración.</span><span class="sxs-lookup"><span data-stu-id="a2035-121">This information is set in the registry during configuration.</span></span> <span data-ttu-id="a2035-122">Por lo tanto, el evento indica que es posible que la configuración no se haya completado correctamente o que las entradas del Registro se eliminaron una vez completada la configuración.</span><span class="sxs-lookup"><span data-stu-id="a2035-122">This may indicate that configuration did not complete correctly or that the registry entries have been deleted after configuration was completed.</span></span>  

## <a name="user-action"></a><span data-ttu-id="a2035-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a2035-123">User Action</span></span>  
 <span data-ttu-id="a2035-124">Para resolver este error, realice una o varias de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="a2035-124">To resolve this error, do one or more of the following:</span></span>  

- <span data-ttu-id="a2035-125">Si sospecha que existe un error de configuración más grave, quite la configuración del producto y vuelva a configurarlo mediante el programa de configuración.</span><span class="sxs-lookup"><span data-stu-id="a2035-125">If you suspect a wider configuration failure, unconfigure the product and then reconfigure using the configuration program.</span></span>  

- <span data-ttu-id="a2035-126">Como alternativa, las entradas del Registro específicas faltantes se pueden establecer a través de la herramienta de línea de comandos de SSO "ssoconfig.exe" que se encuentra en el directorio de instalación de SSO (normalmente, C:\Archivos de programa\Archivos comunes\Inicio de sesión único empresarial).</span><span class="sxs-lookup"><span data-stu-id="a2035-126">Alternatively these specific missing registry entries can be set using the SSO command line tool, ssoconfig.exe located in the SSO installation directory, typically C:\Program Files\Common Files\Enterprise Single Sign-On.</span></span> <span data-ttu-id="a2035-127">Es posible que el directorio de instalación de SSO sea diferente.</span><span class="sxs-lookup"><span data-stu-id="a2035-127">Your SSO installation directory may be different.</span></span> <span data-ttu-id="a2035-128">Use la **- setDB** opción para establecer los nombres de base de datos de SQL Server y SSO necesarios.</span><span class="sxs-lookup"><span data-stu-id="a2035-128">Use the **-setDB** option to set the required SQL Server and SSO database names.</span></span>  

  <span data-ttu-id="a2035-129">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="a2035-129">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="a2035-130">Implementación de Enterprise Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="a2035-130">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)
