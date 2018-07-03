---
title: 'De sesión único: Evento 10668 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0eb3dd4d-04b5-4713-93c1-76af012d6920
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a7a3efa9ba3e9ccae3cdc39c4549a4625e5d872
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974005"
---
# <a name="single-sign-on-event-10668"></a><span data-ttu-id="fcc5e-102">De sesión único: Evento 10668</span><span class="sxs-lookup"><span data-stu-id="fcc5e-102">Single Sign-On: Event 10668</span></span>
## <a name="details"></a><span data-ttu-id="fcc5e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="fcc5e-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="fcc5e-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="fcc5e-104">Product Name</span></span>   |                                                                                                                                                   <span data-ttu-id="fcc5e-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="fcc5e-105">Enterprise Single Sign-On</span></span>                                                                                                                                                   |
| <span data-ttu-id="fcc5e-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="fcc5e-106">Product Version</span></span> |                                                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                   |
|    <span data-ttu-id="fcc5e-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="fcc5e-107">Event ID</span></span>     |                                                                                                                                                             <span data-ttu-id="fcc5e-108">10668</span><span class="sxs-lookup"><span data-stu-id="fcc5e-108">10668</span></span>                                                                                                                                                             |
|  <span data-ttu-id="fcc5e-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="fcc5e-109">Event Source</span></span>   |                                                                                                                                                            <span data-ttu-id="fcc5e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="fcc5e-110">ENTSSO</span></span>                                                                                                                                                             |
|    <span data-ttu-id="fcc5e-111">Componente</span><span class="sxs-lookup"><span data-stu-id="fcc5e-111">Component</span></span>    |                                                                                                                                                              <span data-ttu-id="fcc5e-112">N\D</span><span class="sxs-lookup"><span data-stu-id="fcc5e-112">N\A</span></span>                                                                                                                                                              |
|  <span data-ttu-id="fcc5e-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="fcc5e-113">Symbolic Name</span></span>  |                                                                                                                                               <span data-ttu-id="fcc5e-114">SSO_WARN_NO_OLD_WINDOWS_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="fcc5e-114">SSO_WARN_NO_OLD_WINDOWS_PASSWORD</span></span>                                                                                                                                                |
|  <span data-ttu-id="fcc5e-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="fcc5e-115">Message Text</span></span>   | <span data-ttu-id="fcc5e-116">No se puede cambiar la contraseña de Windows porque la contraseña anterior de Windows para esta cuenta no está disponible en la base de datos de SSO.%r</span><span class="sxs-lookup"><span data-stu-id="fcc5e-116">Cannot change the Windows password because the old Windows password for this account is not available in the SSO database.%r</span></span><br /><br /> <span data-ttu-id="fcc5e-117">Use las herramientas de administración de SSO para establecer las credenciales externas para esta cuenta de Windows.%r</span><span class="sxs-lookup"><span data-stu-id="fcc5e-117">Use the SSO administration tools to set the external credentials for this Windows account.%r</span></span><br /><br /> <span data-ttu-id="fcc5e-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="fcc5e-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="fcc5e-119">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="fcc5e-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="fcc5e-120">Cuenta de Windows: %3</span><span class="sxs-lookup"><span data-stu-id="fcc5e-120">Windows Account: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="fcc5e-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="fcc5e-121">Explanation</span></span>  
 <span data-ttu-id="fcc5e-122">Este evento de advertencia indica que Sincronización de contraseñas no puede cambiar la contraseña de Windows porque la contraseña anterior de Windows para esta cuenta no está disponible en la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="fcc5e-122">This Warning event indicates that Password Sync cannot change the Windows password because the old Windows password for this account is not available in the SSO database.</span></span>  

## <a name="user-action"></a><span data-ttu-id="fcc5e-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="fcc5e-123">User Action</span></span>  
 <span data-ttu-id="fcc5e-124">Para resolver esta advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fcc5e-124">To resolve this warning, do the following:</span></span>  

-   <span data-ttu-id="fcc5e-125">Determine qué aplicaciones se asignaron a este adaptador (nombre en el mensaje de registro de eventos) y, a continuación, use las herramientas de administración de SSO para establecer las credenciales externas para esta cuenta de Windows.</span><span class="sxs-lookup"><span data-stu-id="fcc5e-125">Determine which Applications were assigned to this Adapter (name in event log message) and then use the SSO administration tools to set the external credentials for this Windows account.</span></span> <span data-ttu-id="fcc5e-126">Debe establecer la contraseña externa (para la cuenta de Windows especificada) en todas esas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="fcc5e-126">You must set the external password (for the given Windows Account) in all of those Applications.</span></span>  

## <a name="more-info"></a><span data-ttu-id="fcc5e-127">Más información</span><span class="sxs-lookup"><span data-stu-id="fcc5e-127">More info</span></span>

- [<span data-ttu-id="fcc5e-128">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="fcc5e-128">Password Synchronization</span></span>](../core/password-synchronization2.md)  

- <span data-ttu-id="fcc5e-129">**Propiedades del adaptador de sincronización de contraseñas: opciones** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="fcc5e-129">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
