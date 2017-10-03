---
title: "Inicio de sesión único: Evento 10510 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4553ad4c-9553-4b8b-b3a3-72aed2a61202
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 053f75541597e3b2e721c53714aaaf8517c3c49f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10510"></a><span data-ttu-id="ba75a-102">Inicio de sesión único: Evento 10510</span><span class="sxs-lookup"><span data-stu-id="ba75a-102">Single Sign-On: Event 10510</span></span>
## <a name="details"></a><span data-ttu-id="ba75a-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ba75a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ba75a-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ba75a-104">Product Name</span></span>|<span data-ttu-id="ba75a-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="ba75a-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="ba75a-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ba75a-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="ba75a-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ba75a-107">Event ID</span></span>|<span data-ttu-id="ba75a-108">10510</span><span class="sxs-lookup"><span data-stu-id="ba75a-108">10510</span></span>|  
|<span data-ttu-id="ba75a-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ba75a-109">Event Source</span></span>|<span data-ttu-id="ba75a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ba75a-110">ENTSSO</span></span>|  
|<span data-ttu-id="ba75a-111">Componente</span><span class="sxs-lookup"><span data-stu-id="ba75a-111">Component</span></span>|<span data-ttu-id="ba75a-112">N\D</span><span class="sxs-lookup"><span data-stu-id="ba75a-112">N\A</span></span>|  
|<span data-ttu-id="ba75a-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ba75a-113">Symbolic Name</span></span>|<span data-ttu-id="ba75a-114">SSO_INFO_DLL_LOAD_FAILED</span><span class="sxs-lookup"><span data-stu-id="ba75a-114">SSO_INFO_DLL_LOAD_FAILED</span></span>|  
|<span data-ttu-id="ba75a-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ba75a-115">Message Text</span></span>|<span data-ttu-id="ba75a-116">No se pudo cargar %1.</span><span class="sxs-lookup"><span data-stu-id="ba75a-116">Failed to load %1.</span></span> <span data-ttu-id="ba75a-117">Compruebe que este archivo está disponible.</span><span class="sxs-lookup"><span data-stu-id="ba75a-117">Check that this file is available.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ba75a-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="ba75a-118">Explanation</span></span>  
 <span data-ttu-id="ba75a-119">Este evento de información indica que el servicio SSO no pudo cargar la DLL.</span><span class="sxs-lookup"><span data-stu-id="ba75a-119">This Information event indicates that the SSO service has failed to load the DLL.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ba75a-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ba75a-120">User Action</span></span>  
 <span data-ttu-id="ba75a-121">Para solucionar el evento, realice una o varias de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="ba75a-121">To resolve this event, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="ba75a-122">Compruebe si la DLL se encuentra en el directorio de instalación de SSO, normalmente C:\Archivos de programa\Archivos comunes\Inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="ba75a-122">Verify the DLL is located in the SSO installation directory, typically C:\Program Files\Common Files\Enterprise Single Sign-On.</span></span> <span data-ttu-id="ba75a-123">Es posible que el directorio de instalación de SSO sea diferente.</span><span class="sxs-lookup"><span data-stu-id="ba75a-123">Your SSO installation directory may be different.</span></span>  
  
-   <span data-ttu-id="ba75a-124">Si la única DLL falta o está dañada, intente reemplazarla y, seguidamente, reinicie el servicio.</span><span class="sxs-lookup"><span data-stu-id="ba75a-124">If the single DLL is missing or corrupted, attempt to replace it and then restart the service.</span></span>  
  
 <span data-ttu-id="ba75a-125">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ba75a-125">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="ba75a-126">Implementación de Enterprise Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="ba75a-126">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)