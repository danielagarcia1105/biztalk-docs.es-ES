---
title: "Inicio de sesión único: Evento 10558 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 84637b67-09df-4c1e-b9f2-85a738ba0d7a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c2ee5c21bdf90e6aedcdbe2ac83e0e51a7f48f6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10558"></a><span data-ttu-id="df1ef-102">Inicio de sesión único: Evento 10558</span><span class="sxs-lookup"><span data-stu-id="df1ef-102">Single Sign-On: Event 10558</span></span>
## <a name="details"></a><span data-ttu-id="df1ef-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="df1ef-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="df1ef-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="df1ef-104">Product Name</span></span>|<span data-ttu-id="df1ef-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="df1ef-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="df1ef-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="df1ef-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="df1ef-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="df1ef-107">Event ID</span></span>|<span data-ttu-id="df1ef-108">10558</span><span class="sxs-lookup"><span data-stu-id="df1ef-108">10558</span></span>|  
|<span data-ttu-id="df1ef-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="df1ef-109">Event Source</span></span>|<span data-ttu-id="df1ef-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="df1ef-110">ENTSSO</span></span>|  
|<span data-ttu-id="df1ef-111">Componente</span><span class="sxs-lookup"><span data-stu-id="df1ef-111">Component</span></span>|<span data-ttu-id="df1ef-112">N/D</span><span class="sxs-lookup"><span data-stu-id="df1ef-112">N/A</span></span>|  
|<span data-ttu-id="df1ef-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="df1ef-113">Symbolic Name</span></span>|<span data-ttu-id="df1ef-114">SSO_WARN_USER_OWN_MAPPINGS</span><span class="sxs-lookup"><span data-stu-id="df1ef-114">SSO_WARN_USER_OWN_MAPPINGS</span></span>|  
|<span data-ttu-id="df1ef-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="df1ef-115">Message Text</span></span>|<span data-ttu-id="df1ef-116">Sólo se permiten usuarios de aplicación para controlar sus propias asignaciones.%r</span><span class="sxs-lookup"><span data-stu-id="df1ef-116">Application Users are only allowed to control their own mappings.%r</span></span><br /><br /> <span data-ttu-id="df1ef-117">Nombre de dominio: %1 %r</span><span class="sxs-lookup"><span data-stu-id="df1ef-117">Domain Name: %1%r</span></span><br /><br /> <span data-ttu-id="df1ef-118">Nombre de usuario: %2 %r</span><span class="sxs-lookup"><span data-stu-id="df1ef-118">User Name: %2%r</span></span><br /><br /> <span data-ttu-id="df1ef-119">Nombre de la aplicación: %3 %r</span><span class="sxs-lookup"><span data-stu-id="df1ef-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="df1ef-120">Usuario cliente: %4</span><span class="sxs-lookup"><span data-stu-id="df1ef-120">Client User: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="df1ef-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="df1ef-121">Explanation</span></span>  
 <span data-ttu-id="df1ef-122">Un usuario de aplicación intentó controlar las asignaciones de otro usuario.</span><span class="sxs-lookup"><span data-stu-id="df1ef-122">An attempt was made by an Application User to control the mappings of a different user.</span></span> <span data-ttu-id="df1ef-123">Esto no está permitido.</span><span class="sxs-lookup"><span data-stu-id="df1ef-123">This is not allowed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="df1ef-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="df1ef-124">User Action</span></span>  
 <span data-ttu-id="df1ef-125">Las asignaciones sólo pueden ser controladas por los usuarios de aplicación de esas asignaciones específicas.</span><span class="sxs-lookup"><span data-stu-id="df1ef-125">Mappings can only be controlled by the Application Users for those specific mappings.</span></span>