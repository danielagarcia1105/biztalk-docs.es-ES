---
title: 'De sesión único: Evento 10611 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4549ac01-b828-478f-aea0-862e14fac149
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ca43eff86b20df7000c973f7c6ade472a8780de
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023570"
---
# <a name="single-sign-on-event-10611"></a><span data-ttu-id="938ca-102">De sesión único: Evento 10611</span><span class="sxs-lookup"><span data-stu-id="938ca-102">Single Sign-On: Event 10611</span></span>
## <a name="details"></a><span data-ttu-id="938ca-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="938ca-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="938ca-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="938ca-104">Product Name</span></span>   |                                                                                                         <span data-ttu-id="938ca-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="938ca-105">Enterprise Single Sign-On</span></span>                                                                                                         |
| <span data-ttu-id="938ca-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="938ca-106">Product Version</span></span> |                                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                         |
|    <span data-ttu-id="938ca-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="938ca-107">Event ID</span></span>     |                                                                                                                   <span data-ttu-id="938ca-108">10611</span><span class="sxs-lookup"><span data-stu-id="938ca-108">10611</span></span>                                                                                                                   |
|  <span data-ttu-id="938ca-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="938ca-109">Event Source</span></span>   |                                                                                                                  <span data-ttu-id="938ca-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="938ca-110">ENTSSO</span></span>                                                                                                                   |
|    <span data-ttu-id="938ca-111">Componente</span><span class="sxs-lookup"><span data-stu-id="938ca-111">Component</span></span>    |                                                                                                                    <span data-ttu-id="938ca-112">N/D</span><span class="sxs-lookup"><span data-stu-id="938ca-112">N/A</span></span>                                                                                                                    |
|  <span data-ttu-id="938ca-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="938ca-113">Symbolic Name</span></span>  |                                                                                                     <span data-ttu-id="938ca-114">SSO_INFO_SERVICE_STARTING_NO_SSL</span><span class="sxs-lookup"><span data-stu-id="938ca-114">SSO_INFO_SERVICE_STARTING_NO_SSL</span></span>                                                                                                      |
|  <span data-ttu-id="938ca-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="938ca-115">Message Text</span></span>   | <span data-ttu-id="938ca-116">Se está iniciando el servicio SSO.%r</span><span class="sxs-lookup"><span data-stu-id="938ca-116">The SSO service is starting.%r</span></span><br /><br /> <span data-ttu-id="938ca-117">Nombre de equipo: %1 %r</span><span class="sxs-lookup"><span data-stu-id="938ca-117">Computer Name: %1%r</span></span><br /><br /> <span data-ttu-id="938ca-118">Nombre de SQL Server: %2 %r</span><span class="sxs-lookup"><span data-stu-id="938ca-118">SQL Server Name: %2%r</span></span><br /><br /> <span data-ttu-id="938ca-119">Nombre de la base de datos SSO: %3 %r</span><span class="sxs-lookup"><span data-stu-id="938ca-119">SSO Database Name: %3%r</span></span><br /><br /> <span data-ttu-id="938ca-120">No se usa SSL.</span><span class="sxs-lookup"><span data-stu-id="938ca-120">Not using SSL.</span></span> <span data-ttu-id="938ca-121">Consulte la documentación para obtener información detallada sobre el procedimiento para proteger la conexión con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="938ca-121">See documentation for details on how to secure the SQL Server connection.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="938ca-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="938ca-122">Explanation</span></span>  
 <span data-ttu-id="938ca-123">El servicio ENTSSO se está iniciando sin usar la Capa de sockets seguros (SSL).</span><span class="sxs-lookup"><span data-stu-id="938ca-123">The ENTSSO Service is starting without using Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="938ca-124">Se recomienda proteger la conexión entre el servicio SSO y SQL.</span><span class="sxs-lookup"><span data-stu-id="938ca-124">It is recommended that you secure your connection from the SSO Service to SQL.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="938ca-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="938ca-125">User Action</span></span>  
 <span data-ttu-id="938ca-126">Consulte la documentación en [cómo habilitar SSL para SSO](../core/how-to-enable-ssl-for-sso.md)</span><span class="sxs-lookup"><span data-stu-id="938ca-126">See the documentation at [How to Enable SSL for SSO](../core/how-to-enable-ssl-for-sso.md)</span></span>  
  
 <span data-ttu-id="938ca-127">.</span><span class="sxs-lookup"><span data-stu-id="938ca-127">.</span></span>