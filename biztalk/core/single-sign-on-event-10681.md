---
title: 'De sesión único: Evento 10681 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87ce2e50-cf54-4b23-b247-f137ce64ba1d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d2b400db062dc76b32d071032ee75c55ef48046
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011669"
---
# <a name="single-sign-on-event-10681"></a><span data-ttu-id="46e61-102">De sesión único: Evento 10681</span><span class="sxs-lookup"><span data-stu-id="46e61-102">Single Sign-On: Event 10681</span></span>
## <a name="details"></a><span data-ttu-id="46e61-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="46e61-103">Details</span></span>  

|                 |                                                                                                                                                                                                                      |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="46e61-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="46e61-104">Product Name</span></span>   |                                                                                              <span data-ttu-id="46e61-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="46e61-105">Enterprise Single Sign-On</span></span>                                                                                               |
| <span data-ttu-id="46e61-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="46e61-106">Product Version</span></span> |                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                              |
|    <span data-ttu-id="46e61-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="46e61-107">Event ID</span></span>     |                                                                                                        <span data-ttu-id="46e61-108">10681</span><span class="sxs-lookup"><span data-stu-id="46e61-108">10681</span></span>                                                                                                         |
|  <span data-ttu-id="46e61-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="46e61-109">Event Source</span></span>   |                                                                                                        <span data-ttu-id="46e61-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="46e61-110">ENTSSO</span></span>                                                                                                        |
|    <span data-ttu-id="46e61-111">Componente</span><span class="sxs-lookup"><span data-stu-id="46e61-111">Component</span></span>    |                                                                                                         <span data-ttu-id="46e61-112">N\D</span><span class="sxs-lookup"><span data-stu-id="46e61-112">N\A</span></span>                                                                                                          |
|  <span data-ttu-id="46e61-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="46e61-113">Symbolic Name</span></span>  |                                                                                         <span data-ttu-id="46e61-114">SSO_WARN_NO_WINDOWS_PASSWORD_CHANGE</span><span class="sxs-lookup"><span data-stu-id="46e61-114">SSO_WARN_NO_WINDOWS_PASSWORD_CHANGE</span></span>                                                                                          |
|  <span data-ttu-id="46e61-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="46e61-115">Message Text</span></span>   | <span data-ttu-id="46e61-116">Cambio de contraseña externa.</span><span class="sxs-lookup"><span data-stu-id="46e61-116">External password change.</span></span> <span data-ttu-id="46e61-117">No se cambió la contraseña de Windows porque uno o varios cambios de cuenta externa tienen error.%r</span><span class="sxs-lookup"><span data-stu-id="46e61-117">The Windows password was not changed because one or more of the external account changes failed.%r</span></span><br /><br /> <span data-ttu-id="46e61-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="46e61-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="46e61-119">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="46e61-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="46e61-120">Cuenta de Windows: %3</span><span class="sxs-lookup"><span data-stu-id="46e61-120">Windows Account: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="46e61-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="46e61-121">Explanation</span></span>  
 <span data-ttu-id="46e61-122">Este evento de advertencia indica que no se cambió la contraseña de Windows porque uno o varios cambios de cuenta externa tienen error.</span><span class="sxs-lookup"><span data-stu-id="46e61-122">This Warning event indicates that the Windows password was not changed because one or more of the external account changes failed.</span></span>  

## <a name="user-action"></a><span data-ttu-id="46e61-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="46e61-123">User Action</span></span>  
 <span data-ttu-id="46e61-124">Para solucionar la advertencia, realice una o varias de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="46e61-124">To resolve this warning, do one or more of the following:</span></span>  

-   <span data-ttu-id="46e61-125">Compruebe los registros del sistema y eventos de aplicación para los eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="46e61-125">Check the System and Application Event logs for associated events.</span></span>  

-   <span data-ttu-id="46e61-126">Compruebe la configuración del adaptador mediante las herramientas de administración de SSO.</span><span class="sxs-lookup"><span data-stu-id="46e61-126">Verify adapter configuration using the SSO administration tools.</span></span>  

-   <span data-ttu-id="46e61-127">Compruebe los sistemas externos.</span><span class="sxs-lookup"><span data-stu-id="46e61-127">Verify external systems.</span></span>  

## <a name="more-info"></a><span data-ttu-id="46e61-128">Más información</span><span class="sxs-lookup"><span data-stu-id="46e61-128">More info</span></span>

- [<span data-ttu-id="46e61-129">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="46e61-129">Password Synchronization</span></span>](../core/password-synchronization2.md)  

- <span data-ttu-id="46e61-130">**Propiedades del adaptador de sincronización de contraseñas: opciones** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="46e61-130">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
