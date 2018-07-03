---
title: 'De sesión único: Evento 10678 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6af92ce1-fdac-432f-be6b-cf8958aee776
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1fa3cde1cb26023ab4115f5538b8a3081eaaf1bc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977437"
---
# <a name="single-sign-on-event-10678"></a><span data-ttu-id="79c07-102">De sesión único: Evento 10678</span><span class="sxs-lookup"><span data-stu-id="79c07-102">Single Sign-On: Event 10678</span></span>
## <a name="details"></a><span data-ttu-id="79c07-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="79c07-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                 |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="79c07-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="79c07-104">Product Name</span></span>   |                                                                                                                    <span data-ttu-id="79c07-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="79c07-105">Enterprise Single Sign-On</span></span>                                                                                                                    |
| <span data-ttu-id="79c07-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="79c07-106">Product Version</span></span> |                                                                                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                    |
|    <span data-ttu-id="79c07-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="79c07-107">Event ID</span></span>     |                                                                                                                              <span data-ttu-id="79c07-108">10678</span><span class="sxs-lookup"><span data-stu-id="79c07-108">10678</span></span>                                                                                                                              |
|  <span data-ttu-id="79c07-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="79c07-109">Event Source</span></span>   |                                                                                                                             <span data-ttu-id="79c07-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="79c07-110">ENTSSO</span></span>                                                                                                                              |
|    <span data-ttu-id="79c07-111">Componente</span><span class="sxs-lookup"><span data-stu-id="79c07-111">Component</span></span>    |                                                                                                                               <span data-ttu-id="79c07-112">N\D</span><span class="sxs-lookup"><span data-stu-id="79c07-112">N\A</span></span>                                                                                                                               |
|  <span data-ttu-id="79c07-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="79c07-113">Symbolic Name</span></span>  |                                                                                                                   <span data-ttu-id="79c07-114">SSO_WARN_PASSWORD_MISMATCH</span><span class="sxs-lookup"><span data-stu-id="79c07-114">SSO_WARN_PASSWORD_MISMATCH</span></span>                                                                                                                    |
|  <span data-ttu-id="79c07-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="79c07-115">Message Text</span></span>   | <span data-ttu-id="79c07-116">Cambio de contraseña externa.</span><span class="sxs-lookup"><span data-stu-id="79c07-116">External password change.</span></span> <span data-ttu-id="79c07-117">La contraseña anterior proporcionada por el adaptador no coincide con la contraseña existente para la cuenta externa.%r</span><span class="sxs-lookup"><span data-stu-id="79c07-117">The old password supplied by the adapter does not match the existing password for the external account.%r</span></span><br /><br /> <span data-ttu-id="79c07-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="79c07-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="79c07-119">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="79c07-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="79c07-120">Nombre de la aplicación: %3 %r</span><span class="sxs-lookup"><span data-stu-id="79c07-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="79c07-121">Cuenta externa: %4</span><span class="sxs-lookup"><span data-stu-id="79c07-121">External Account: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="79c07-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="79c07-122">Explanation</span></span>  
 <span data-ttu-id="79c07-123">Este evento de advertencia incida que la contraseña anterior proporcionada por el adaptador no coincide con la contraseña existente para la cuenta externa.</span><span class="sxs-lookup"><span data-stu-id="79c07-123">This Warning event indicates that the old password supplied by the adapter does not match the existing password for the external account.</span></span>  

## <a name="user-action"></a><span data-ttu-id="79c07-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="79c07-124">User Action</span></span>  
 <span data-ttu-id="79c07-125">Para solucionar la advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="79c07-125">To resolve this warning do the following:</span></span>  

-   <span data-ttu-id="79c07-126">Determine qué aplicaciones se asignaron a este adaptador (nombre en el mensaje de registro de eventos) y, a continuación, use las herramientas de administración de SSO para establecer las credenciales externas para esta cuenta externa.</span><span class="sxs-lookup"><span data-stu-id="79c07-126">Determine which Applications were assigned to this Adapter (name in event log message) and then use the SSO administration tools to set the external credentials for this external account.</span></span> <span data-ttu-id="79c07-127">Debe establecer la contraseña externa (para la cuenta especificada) en todas esas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="79c07-127">You must set the external password (for the given account) in all of those Applications.</span></span>  

## <a name="more-info"></a><span data-ttu-id="79c07-128">Más información</span><span class="sxs-lookup"><span data-stu-id="79c07-128">More info</span></span>

- [<span data-ttu-id="79c07-129">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="79c07-129">Password Synchronization</span></span>](../core/password-synchronization2.md)  

- <span data-ttu-id="79c07-130">**Propiedades del adaptador de sincronización de contraseñas: opciones** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="79c07-130">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
