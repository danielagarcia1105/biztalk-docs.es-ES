---
title: 'De sesión único: Evento 10740 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8e8521e7-32af-4a58-8b1a-66ea1d13f1e1
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9bf7c2cdaae3cffe280035f007cd1b49d2c70c8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970061"
---
# <a name="single-sign-on-event-10740"></a><span data-ttu-id="ebe16-102">De sesión único: Evento 10740</span><span class="sxs-lookup"><span data-stu-id="ebe16-102">Single Sign-On: Event 10740</span></span>
## <a name="details"></a><span data-ttu-id="ebe16-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ebe16-103">Details</span></span>  

|                 |                                                                                                                                                            |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ebe16-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ebe16-104">Product Name</span></span>   |                                                                 <span data-ttu-id="ebe16-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="ebe16-105">Enterprise Single Sign-On</span></span>                                                                  |
| <span data-ttu-id="ebe16-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ebe16-106">Product Version</span></span> |                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                 |
|    <span data-ttu-id="ebe16-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ebe16-107">Event ID</span></span>     |                                                                           <span data-ttu-id="ebe16-108">10740</span><span class="sxs-lookup"><span data-stu-id="ebe16-108">10740</span></span>                                                                            |
|  <span data-ttu-id="ebe16-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ebe16-109">Event Source</span></span>   |                                                                           <span data-ttu-id="ebe16-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ebe16-110">ENTSSO</span></span>                                                                           |
|    <span data-ttu-id="ebe16-111">Componente</span><span class="sxs-lookup"><span data-stu-id="ebe16-111">Component</span></span>    |                                                                            <span data-ttu-id="ebe16-112">N\D</span><span class="sxs-lookup"><span data-stu-id="ebe16-112">N\A</span></span>                                                                             |
|  <span data-ttu-id="ebe16-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ebe16-113">Symbolic Name</span></span>  |                                                               <span data-ttu-id="ebe16-114">SSO_WARN_INVALID_WINDOWS_USER</span><span class="sxs-lookup"><span data-stu-id="ebe16-114">SSO_WARN_INVALID_WINDOWS_USER</span></span>                                                                |
|  <span data-ttu-id="ebe16-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ebe16-115">Message Text</span></span>   | <span data-ttu-id="ebe16-116">Cuenta de Windows no válida para actualización de la aplicación.%r</span><span class="sxs-lookup"><span data-stu-id="ebe16-116">The Windows Account is not valid for application update.%r</span></span><br /><br /> <span data-ttu-id="ebe16-117">Nombre de la aplicación: %1 %r</span><span class="sxs-lookup"><span data-stu-id="ebe16-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="ebe16-118">Cuenta de Windows: %2 %r</span><span class="sxs-lookup"><span data-stu-id="ebe16-118">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="ebe16-119">Código de error: %3</span><span class="sxs-lookup"><span data-stu-id="ebe16-119">Error Code: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="ebe16-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="ebe16-120">Explanation</span></span>  
 <span data-ttu-id="ebe16-121">Este evento de advertencia indica que la cuenta de Windows (especificada en el mensaje de evento) no es válida para la actualización de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ebe16-121">This Warning event indicates that the Windows Account (specified in the event message) is not valid for application update.</span></span> <span data-ttu-id="ebe16-122">Esto puede ocurrir cuando se cambia la cuenta de Windows de una aplicación de grupo host.</span><span class="sxs-lookup"><span data-stu-id="ebe16-122">This can occur when changing the Windows account for a Host Group application.</span></span> <span data-ttu-id="ebe16-123">Las aplicaciones de grupo host se usan para inicio de sesión único desde sistemas externos en sistemas de Windows.</span><span class="sxs-lookup"><span data-stu-id="ebe16-123">Host Group applications are used for single sign-on from external systems to Windows systems.</span></span> <span data-ttu-id="ebe16-124">Estas aplicaciones pueden asignar un conjunto de usuarios externos a una única cuenta de Windows.</span><span class="sxs-lookup"><span data-stu-id="ebe16-124">They can map a set of external users to a single Windows account.</span></span> <span data-ttu-id="ebe16-125">La cuenta de Windows a la que se asignan se define en el campo de usuarios de aplicación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ebe16-125">The Windows account they are mapped to is defined in the Application Users field of the application.</span></span>  

## <a name="user-action"></a><span data-ttu-id="ebe16-126">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ebe16-126">User Action</span></span>  
 <span data-ttu-id="ebe16-127">Para resolver esta advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ebe16-127">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="ebe16-128">Compruebe si la cuenta de Windows que se usa es válida.</span><span class="sxs-lookup"><span data-stu-id="ebe16-128">Check that the Windows account your are using is valid.</span></span>  

- <span data-ttu-id="ebe16-129">Vuelva a crear la cuenta de Windows con las propiedades correctas de cuenta de Windows.</span><span class="sxs-lookup"><span data-stu-id="ebe16-129">Recreate the Windows account with the correct Windows account properties.</span></span>  

  <span data-ttu-id="ebe16-130">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ebe16-130">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="ebe16-131">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="ebe16-131">Password Synchronization</span></span>](../core/password-synchronization2.md)
