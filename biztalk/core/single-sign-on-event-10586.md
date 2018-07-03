---
title: 'De sesión único: Evento 10586 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7d480e9-dc34-44ac-9272-0caf80237bd9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b353c5d9fb569da7bcc35927e31ce5c3e68ae11
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978881"
---
# <a name="single-sign-on-event-10586"></a><span data-ttu-id="7a29a-102">De sesión único: Evento 10586</span><span class="sxs-lookup"><span data-stu-id="7a29a-102">Single Sign-On: Event 10586</span></span>
## <a name="details"></a><span data-ttu-id="7a29a-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="7a29a-103">Details</span></span>  
  
|                 |                                                             |
|-----------------|-------------------------------------------------------------|
|  <span data-ttu-id="7a29a-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="7a29a-104">Product Name</span></span>   |                  <span data-ttu-id="7a29a-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="7a29a-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="7a29a-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="7a29a-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]  |
|    <span data-ttu-id="7a29a-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="7a29a-107">Event ID</span></span>     |                            <span data-ttu-id="7a29a-108">10586</span><span class="sxs-lookup"><span data-stu-id="7a29a-108">10586</span></span>                            |
|  <span data-ttu-id="7a29a-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="7a29a-109">Event Source</span></span>   |                           <span data-ttu-id="7a29a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="7a29a-110">ENTSSO</span></span>                            |
|    <span data-ttu-id="7a29a-111">Componente</span><span class="sxs-lookup"><span data-stu-id="7a29a-111">Component</span></span>    |                             <span data-ttu-id="7a29a-112">N/D</span><span class="sxs-lookup"><span data-stu-id="7a29a-112">N/A</span></span>                             |
|  <span data-ttu-id="7a29a-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7a29a-113">Symbolic Name</span></span>  |                   <span data-ttu-id="7a29a-114">SSO_WARN_CRED_CACHE_OFF</span><span class="sxs-lookup"><span data-stu-id="7a29a-114">SSO_WARN_CRED_CACHE_OFF</span></span>                   |
|  <span data-ttu-id="7a29a-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7a29a-115">Message Text</span></span>   | <span data-ttu-id="7a29a-116">La memoria caché de credenciales se deshabilitó para este servidor de SSO.</span><span class="sxs-lookup"><span data-stu-id="7a29a-116">The credential cache has been disabled for this SSO server.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="7a29a-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="7a29a-117">Explanation</span></span>  
 <span data-ttu-id="7a29a-118">Se deshabilitó la memoria caché de credenciales que, por lo general, está habilitada.</span><span class="sxs-lookup"><span data-stu-id="7a29a-118">The credential cache, which is generally enabled, has been disabled.</span></span> <span data-ttu-id="7a29a-119">Sólo el administrador del sistema puede habilitar o deshabilitar la memoria caché de credenciales.</span><span class="sxs-lookup"><span data-stu-id="7a29a-119">Only a system administrator can enable or disable the credential cache.</span></span> <span data-ttu-id="7a29a-120">En ciertos casos, si se deshabilita esta memoria, hay más credenciales actuales del sistema ENTSSO, aunque esto podría disminuir el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="7a29a-120">Disabling the credential cache will sometimes result in more current credentials from the ENTSSO system, although it could slow down peformance.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7a29a-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7a29a-121">User Action</span></span>  
 <span data-ttu-id="7a29a-122">Para volver a habilitar la caché de credenciales, vea la tabla de propiedades de aplicaciones afiliadas en [aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md).</span><span class="sxs-lookup"><span data-stu-id="7a29a-122">To re-enable the credential cache, see the Afflilate Application Properties table in [SSO Affiliate Applications](../core/sso-affiliate-applications.md).</span></span>