---
title: 'De sesión único: Evento 10512 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4edf0512-112d-40b8-9e29-7dd67f999b6d
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54ba5a340a1a7590dae72016a3e747726ea68125
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980965"
---
# <a name="single-sign-on-event-10512"></a><span data-ttu-id="d12f6-102">De sesión único: Evento 10512</span><span class="sxs-lookup"><span data-stu-id="d12f6-102">Single Sign-On: Event 10512</span></span>
## <a name="details"></a><span data-ttu-id="d12f6-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="d12f6-103">Details</span></span>  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="d12f6-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="d12f6-104">Product Name</span></span>   |                 <span data-ttu-id="d12f6-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="d12f6-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="d12f6-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="d12f6-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="d12f6-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="d12f6-107">Event ID</span></span>     |                           <span data-ttu-id="d12f6-108">10512</span><span class="sxs-lookup"><span data-stu-id="d12f6-108">10512</span></span>                            |
|  <span data-ttu-id="d12f6-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="d12f6-109">Event Source</span></span>   |                           <span data-ttu-id="d12f6-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d12f6-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="d12f6-111">Componente</span><span class="sxs-lookup"><span data-stu-id="d12f6-111">Component</span></span>    |                            <span data-ttu-id="d12f6-112">N\D</span><span class="sxs-lookup"><span data-stu-id="d12f6-112">N\A</span></span>                             |
|  <span data-ttu-id="d12f6-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d12f6-113">Symbolic Name</span></span>  |                   <span data-ttu-id="d12f6-114">SSO_ERROR_LOADLIBRARY</span><span class="sxs-lookup"><span data-stu-id="d12f6-114">SSO_ERROR_LOADLIBRARY</span></span>                    |
|  <span data-ttu-id="d12f6-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d12f6-115">Message Text</span></span>   |      <span data-ttu-id="d12f6-116">No se pudo cargar %1%r</span><span class="sxs-lookup"><span data-stu-id="d12f6-116">Failed to load %1%r</span></span><br /><br /> <span data-ttu-id="d12f6-117">Código de error: %2.</span><span class="sxs-lookup"><span data-stu-id="d12f6-117">Error code: %2.</span></span>       |

## <a name="explanation"></a><span data-ttu-id="d12f6-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="d12f6-118">Explanation</span></span>  
 <span data-ttu-id="d12f6-119">Este evento de error indica que la Biblioteca de vínculos dinámicos (DLL) no se pudo cargar en el proceso del servidor de SSO.</span><span class="sxs-lookup"><span data-stu-id="d12f6-119">This Error event indicates that the specified Dynamic Link Library (DLL) could not be loaded into the SSO server process.</span></span> <span data-ttu-id="d12f6-120">La falta de la DLL en el directorio de instalación de SSO (normalmente, C:\Archivos de programa\Archivos comunes\Inicio de sesión único empresarial) puede indicar que el programa de instalación no se completó correctamente o que la DLL se eliminó después de que éste se completó.</span><span class="sxs-lookup"><span data-stu-id="d12f6-120">If the DLL is missing in the SSO installation directory, typically C:\Program Files\Common Files\Enterprise Single Sign-On, it may indicate that setup was not completed correctly, or that the DLL was deleted after setup was completed.</span></span> <span data-ttu-id="d12f6-121">Si la DLL está presente, el servicio SSO podría tener problemas con la resolución de la ruta de acceso correcta a ella.</span><span class="sxs-lookup"><span data-stu-id="d12f6-121">If the DLL is present, then there could be a problem with the SSO service resolving the correct path to the DLL.</span></span> <span data-ttu-id="d12f6-122">Además, la DLL podría estar dañada.</span><span class="sxs-lookup"><span data-stu-id="d12f6-122">Additionally, the DLL itself could be corrupted.</span></span>  

## <a name="user-action"></a><span data-ttu-id="d12f6-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d12f6-123">User Action</span></span>  
 <span data-ttu-id="d12f6-124">Para resolver este error, realice una o varias de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="d12f6-124">To resolve this error, do one or more of the following:</span></span>  

- <span data-ttu-id="d12f6-125">Si se sospecha que puede existir un error más grave de instalación, tal vez sea necesario desinstalar el producto y volver a instalarlo.</span><span class="sxs-lookup"><span data-stu-id="d12f6-125">If a wider failure of setup is suspected it may be necessary to uninstall and reinstall the product.</span></span>  

- <span data-ttu-id="d12f6-126">Si la única DLL falta o está dañada, intente reemplazarla y, seguidamente, reinicie el servicio.</span><span class="sxs-lookup"><span data-stu-id="d12f6-126">If the single DLL is missing or corrupted, attempt to replace it and then restart the service.</span></span>  

  <span data-ttu-id="d12f6-127">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="d12f6-127">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="d12f6-128">Implementación de Enterprise Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="d12f6-128">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)
