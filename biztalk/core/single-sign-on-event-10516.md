---
title: 'De sesión único: Evento 10516 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d20df92f-c995-4cbc-a8f9-21cea30b82c9
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d0f3ab8e5d368c04b1a93b9e7e00efa76c50283
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023530"
---
# <a name="single-sign-on-event-10516"></a><span data-ttu-id="95d88-102">De sesión único: Evento 10516</span><span class="sxs-lookup"><span data-stu-id="95d88-102">Single Sign-On: Event 10516</span></span>
## <a name="details"></a><span data-ttu-id="95d88-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="95d88-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                                                                                                 |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="95d88-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="95d88-104">Product Name</span></span>   |                                                                                                                                                            <span data-ttu-id="95d88-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="95d88-105">Enterprise Single Sign-On</span></span>                                                                                                                                                            |
| <span data-ttu-id="95d88-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="95d88-106">Product Version</span></span> |                                                                                                                                           [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                            |
|    <span data-ttu-id="95d88-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="95d88-107">Event ID</span></span>     |                                                                                                                                                                      <span data-ttu-id="95d88-108">10516</span><span class="sxs-lookup"><span data-stu-id="95d88-108">10516</span></span>                                                                                                                                                                      |
|  <span data-ttu-id="95d88-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="95d88-109">Event Source</span></span>   |                                                                                                                                                                     <span data-ttu-id="95d88-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="95d88-110">ENTSSO</span></span>                                                                                                                                                                      |
|    <span data-ttu-id="95d88-111">Componente</span><span class="sxs-lookup"><span data-stu-id="95d88-111">Component</span></span>    |                                                                                                                                                                       <span data-ttu-id="95d88-112">N\D</span><span class="sxs-lookup"><span data-stu-id="95d88-112">N\A</span></span>                                                                                                                                                                       |
|  <span data-ttu-id="95d88-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="95d88-113">Symbolic Name</span></span>  |                                                                                                                                                           <span data-ttu-id="95d88-114">SSO_ERROR_BAD_SSO_APP_ADMIN</span><span class="sxs-lookup"><span data-stu-id="95d88-114">SSO_ERROR_BAD_SSO_APP_ADMIN</span></span>                                                                                                                                                           |
|  <span data-ttu-id="95d88-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="95d88-115">Message Text</span></span>   | <span data-ttu-id="95d88-116">Cuenta de administradores afiliados de SSO no válida.</span><span class="sxs-lookup"><span data-stu-id="95d88-116">The SSO Affiliate Administrators account is not valid.</span></span> <span data-ttu-id="95d88-117">Si se trata de una cuenta local, compruebe si existe en el servidor.</span><span class="sxs-lookup"><span data-stu-id="95d88-117">If it is a local account check that this account exists on the server.</span></span> <span data-ttu-id="95d88-118">Si se trata de una cuenta de dominio, póngase en contacto con el administrador de dominio.</span><span class="sxs-lookup"><span data-stu-id="95d88-118">If it is a domain account contact your domain administrator.</span></span> <span data-ttu-id="95d88-119">Cuando la cuenta sea válida, habilite SSO.%r</span><span class="sxs-lookup"><span data-stu-id="95d88-119">Enable SSO when the account is valid.%r</span></span><br /><br /> <span data-ttu-id="95d88-120">Administradores afiliados de SSO: %1 %r</span><span class="sxs-lookup"><span data-stu-id="95d88-120">SSO Affiliate Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="95d88-121">Cuentas no válidas: %2 %r</span><span class="sxs-lookup"><span data-stu-id="95d88-121">Invalid accounts: %2%r</span></span><br /><br /> <span data-ttu-id="95d88-122">Código de error: %3</span><span class="sxs-lookup"><span data-stu-id="95d88-122">Error Code: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="95d88-123">Explicación</span><span class="sxs-lookup"><span data-stu-id="95d88-123">Explanation</span></span>  
 <span data-ttu-id="95d88-124">Este evento de error indica que el grupo o la cuenta de administradores afiliados de SSO creada por el inicio de sesión único empresarial no es una cuenta de Windows válida.</span><span class="sxs-lookup"><span data-stu-id="95d88-124">This Error event indicates that the SSO Affiliate Administrator account or group created by Enterprise Sing Sign-on is not a valid Windows account.</span></span> <span data-ttu-id="95d88-125">La cuenta de administradores afiliados de SSO puede ser una cuenta de grupo de Windows o una cuenta individual.</span><span class="sxs-lookup"><span data-stu-id="95d88-125">The SSO Affiliate Administrators account can be either a Windows group account or an individual account.</span></span> <span data-ttu-id="95d88-126">La cuenta de administradores afiliados de SSO también puede ser una cuenta de grupo local o de dominio.</span><span class="sxs-lookup"><span data-stu-id="95d88-126">The SSO Affiliate Administrator account can also be either a domain or local group account.</span></span>  

## <a name="user-action"></a><span data-ttu-id="95d88-127">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="95d88-127">User Action</span></span>  
 <span data-ttu-id="95d88-128">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="95d88-128">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="95d88-129">Compruebe si existe la cuenta de administradores afiliados de SSO.</span><span class="sxs-lookup"><span data-stu-id="95d88-129">Verify the SSO Affiliate Administrator account exists.</span></span>  

  <span data-ttu-id="95d88-130">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="95d88-130">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="95d88-131">Grupos de usuarios de SSO</span><span class="sxs-lookup"><span data-stu-id="95d88-131">SSO User Groups</span></span>](../core/sso-user-groups.md)  

- [<span data-ttu-id="95d88-132">Cómo actualizar la base de datos SSO</span><span class="sxs-lookup"><span data-stu-id="95d88-132">How to Update the SSO Database</span></span>](../core/how-to-update-the-sso-database.md)
