---
title: 'De sesión único: Evento 10510 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4553ad4c-9553-4b8b-b3a3-72aed2a61202
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6043dabf397bb987b58707885cbf91d36de50eab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011349"
---
# <a name="single-sign-on-event-10510"></a><span data-ttu-id="3246f-102">De sesión único: Evento 10510</span><span class="sxs-lookup"><span data-stu-id="3246f-102">Single Sign-On: Event 10510</span></span>
## <a name="details"></a><span data-ttu-id="3246f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="3246f-103">Details</span></span>  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="3246f-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="3246f-104">Product Name</span></span>   |                 <span data-ttu-id="3246f-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="3246f-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="3246f-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="3246f-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="3246f-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="3246f-107">Event ID</span></span>     |                           <span data-ttu-id="3246f-108">10510</span><span class="sxs-lookup"><span data-stu-id="3246f-108">10510</span></span>                            |
|  <span data-ttu-id="3246f-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="3246f-109">Event Source</span></span>   |                           <span data-ttu-id="3246f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3246f-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="3246f-111">Componente</span><span class="sxs-lookup"><span data-stu-id="3246f-111">Component</span></span>    |                            <span data-ttu-id="3246f-112">N\D</span><span class="sxs-lookup"><span data-stu-id="3246f-112">N\A</span></span>                             |
|  <span data-ttu-id="3246f-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3246f-113">Symbolic Name</span></span>  |                  <span data-ttu-id="3246f-114">SSO_INFO_DLL_LOAD_FAILED</span><span class="sxs-lookup"><span data-stu-id="3246f-114">SSO_INFO_DLL_LOAD_FAILED</span></span>                  |
|  <span data-ttu-id="3246f-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3246f-115">Message Text</span></span>   |   <span data-ttu-id="3246f-116">No se pudo cargar %1.</span><span class="sxs-lookup"><span data-stu-id="3246f-116">Failed to load %1.</span></span> <span data-ttu-id="3246f-117">Compruebe que este archivo está disponible.</span><span class="sxs-lookup"><span data-stu-id="3246f-117">Check that this file is available.</span></span>    |

## <a name="explanation"></a><span data-ttu-id="3246f-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="3246f-118">Explanation</span></span>  
 <span data-ttu-id="3246f-119">Este evento de información indica que el servicio SSO no pudo cargar la DLL.</span><span class="sxs-lookup"><span data-stu-id="3246f-119">This Information event indicates that the SSO service has failed to load the DLL.</span></span>  

## <a name="user-action"></a><span data-ttu-id="3246f-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3246f-120">User Action</span></span>  
 <span data-ttu-id="3246f-121">Para solucionar el evento, realice una o varias de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="3246f-121">To resolve this event, do one or more of the following:</span></span>  

- <span data-ttu-id="3246f-122">Compruebe si la DLL se encuentra en el directorio de instalación de SSO, normalmente C:\Archivos de programa\Archivos comunes\Inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="3246f-122">Verify the DLL is located in the SSO installation directory, typically C:\Program Files\Common Files\Enterprise Single Sign-On.</span></span> <span data-ttu-id="3246f-123">Es posible que el directorio de instalación de SSO sea diferente.</span><span class="sxs-lookup"><span data-stu-id="3246f-123">Your SSO installation directory may be different.</span></span>  

- <span data-ttu-id="3246f-124">Si la única DLL falta o está dañada, intente reemplazarla y, seguidamente, reinicie el servicio.</span><span class="sxs-lookup"><span data-stu-id="3246f-124">If the single DLL is missing or corrupted, attempt to replace it and then restart the service.</span></span>  

  <span data-ttu-id="3246f-125">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="3246f-125">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="3246f-126">Implementación de Enterprise Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="3246f-126">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)
