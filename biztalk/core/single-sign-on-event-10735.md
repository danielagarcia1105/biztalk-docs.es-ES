---
title: 'De sesión único: Evento 10735 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 31c791c6-1901-4441-b329-ed75833cb83e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ede774a4a212d71aa65165f7da1f6de5bb04103c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979229"
---
# <a name="single-sign-on-event-10735"></a><span data-ttu-id="1ed7b-102">De sesión único: Evento 10735</span><span class="sxs-lookup"><span data-stu-id="1ed7b-102">Single Sign-On: Event 10735</span></span>
## <a name="details"></a><span data-ttu-id="1ed7b-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="1ed7b-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="1ed7b-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="1ed7b-104">Product Name</span></span>   |                                                                                                             <span data-ttu-id="1ed7b-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="1ed7b-105">Enterprise Single Sign-On</span></span>                                                                                                              |
| <span data-ttu-id="1ed7b-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="1ed7b-106">Product Version</span></span> |                                                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                             |
|    <span data-ttu-id="1ed7b-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="1ed7b-107">Event ID</span></span>     |                                                                                                                       <span data-ttu-id="1ed7b-108">10735</span><span class="sxs-lookup"><span data-stu-id="1ed7b-108">10735</span></span>                                                                                                                        |
|  <span data-ttu-id="1ed7b-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="1ed7b-109">Event Source</span></span>   |                                                                                                                       <span data-ttu-id="1ed7b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1ed7b-110">ENTSSO</span></span>                                                                                                                       |
|    <span data-ttu-id="1ed7b-111">Componente</span><span class="sxs-lookup"><span data-stu-id="1ed7b-111">Component</span></span>    |                                                                                                                        <span data-ttu-id="1ed7b-112">N\D</span><span class="sxs-lookup"><span data-stu-id="1ed7b-112">N\A</span></span>                                                                                                                         |
|  <span data-ttu-id="1ed7b-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="1ed7b-113">Symbolic Name</span></span>  |                                                                                                              <span data-ttu-id="1ed7b-114">SSO_WARN_PS_APP_DISABLED</span><span class="sxs-lookup"><span data-stu-id="1ed7b-114">SSO_WARN_PS_APP_DISABLED</span></span>                                                                                                              |
|  <span data-ttu-id="1ed7b-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="1ed7b-115">Message Text</span></span>   | <span data-ttu-id="1ed7b-116">Cambio de contraseña externa.</span><span class="sxs-lookup"><span data-stu-id="1ed7b-116">External password change.</span></span> <span data-ttu-id="1ed7b-117">No se pudo cambiar la contraseña de la cuenta externa porque la aplicación está deshabilitada.%r</span><span class="sxs-lookup"><span data-stu-id="1ed7b-117">The password was not changed for the external account because the application is disabled.%r</span></span><br /><br /> <span data-ttu-id="1ed7b-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="1ed7b-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="1ed7b-119">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="1ed7b-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="1ed7b-120">Nombre de la aplicación: %3 %r</span><span class="sxs-lookup"><span data-stu-id="1ed7b-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="1ed7b-121">Cuenta externa: %4</span><span class="sxs-lookup"><span data-stu-id="1ed7b-121">External Account: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="1ed7b-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="1ed7b-122">Explanation</span></span>  
 <span data-ttu-id="1ed7b-123">Este evento de advertencia indica que no se cambió la contraseña de la cuenta externa porque la aplicación está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="1ed7b-123">This Warning event indicates that a password was not changed for the external account because the application is disabled.</span></span>  

## <a name="user-action"></a><span data-ttu-id="1ed7b-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="1ed7b-124">User Action</span></span>  
 <span data-ttu-id="1ed7b-125">Para resolver esta advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1ed7b-125">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="1ed7b-126">Habilite la aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="1ed7b-126">Enable the affiliate application</span></span>  

  <span data-ttu-id="1ed7b-127">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1ed7b-127">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="1ed7b-128">Cómo habilitar una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="1ed7b-128">How to Enable an Affiliate Application</span></span>](../core/how-to-enable-an-affiliate-application.md)  

- [<span data-ttu-id="1ed7b-129">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="1ed7b-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
