---
title: 'De sesión único: Evento 10715 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f63c98d2-988e-466f-be40-171b13a34732
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9bc461aa812c2c61844c11d54743335ac89321a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994861"
---
# <a name="single-sign-on-event-10715"></a><span data-ttu-id="6fead-102">De sesión único: Evento 10715</span><span class="sxs-lookup"><span data-stu-id="6fead-102">Single Sign-On: Event 10715</span></span>
## <a name="details"></a><span data-ttu-id="6fead-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="6fead-103">Details</span></span>  

|                 |                                                                                                                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="6fead-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="6fead-104">Product Name</span></span>   |                                                                                            <span data-ttu-id="6fead-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="6fead-105">Enterprise Single Sign-On</span></span>                                                                                             |
| <span data-ttu-id="6fead-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="6fead-106">Product Version</span></span> |                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                            |
|    <span data-ttu-id="6fead-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="6fead-107">Event ID</span></span>     |                                                                                                      <span data-ttu-id="6fead-108">10715</span><span class="sxs-lookup"><span data-stu-id="6fead-108">10715</span></span>                                                                                                       |
|  <span data-ttu-id="6fead-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="6fead-109">Event Source</span></span>   |                                                                                                      <span data-ttu-id="6fead-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="6fead-110">ENTSSO</span></span>                                                                                                      |
|    <span data-ttu-id="6fead-111">Componente</span><span class="sxs-lookup"><span data-stu-id="6fead-111">Component</span></span>    |                                                                                                       <span data-ttu-id="6fead-112">N\D</span><span class="sxs-lookup"><span data-stu-id="6fead-112">N\A</span></span>                                                                                                        |
|  <span data-ttu-id="6fead-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="6fead-113">Symbolic Name</span></span>  |                                                                                            <span data-ttu-id="6fead-114">SSO_WARN_NO_CREATE_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="6fead-114">SSO_WARN_NO_CREATE_ADAPTER</span></span>                                                                                            |
|  <span data-ttu-id="6fead-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="6fead-115">Message Text</span></span>   | <span data-ttu-id="6fead-116">Para crear adaptadores, el usuario del cliente debe ser miembro de la cuenta de administradores de SSO.%r</span><span class="sxs-lookup"><span data-stu-id="6fead-116">The client user must be a member of the SSO Administrators account to create adapters.%r</span></span><br /><br /> <span data-ttu-id="6fead-117">Usuario cliente: %1 %r</span><span class="sxs-lookup"><span data-stu-id="6fead-117">Client User: %1%r</span></span><br /><br /> <span data-ttu-id="6fead-118">Administradores de SSO: %2 %r</span><span class="sxs-lookup"><span data-stu-id="6fead-118">SSO Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="6fead-119">Adaptador: %3 %r</span><span class="sxs-lookup"><span data-stu-id="6fead-119">Adapter: %3%r</span></span><br /><br /> <span data-ttu-id="6fead-120">Código de error: %4</span><span class="sxs-lookup"><span data-stu-id="6fead-120">Error Code: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="6fead-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="6fead-121">Explanation</span></span>  
 <span data-ttu-id="6fead-122">Este evento de advertencia indica que el usuario del cliente debe ser miembro de la cuenta de administradores de SSO para crear cuentas.</span><span class="sxs-lookup"><span data-stu-id="6fead-122">This Warning event indicates that the client user must be a member of the SSO Administrators account to create adapters.</span></span>  

## <a name="user-action"></a><span data-ttu-id="6fead-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="6fead-123">User Action</span></span>  
 <span data-ttu-id="6fead-124">Para resolver esta advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6fead-124">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="6fead-125">Inicie sesión con una cuenta que pertenezca al grupo de administradores de SSO.</span><span class="sxs-lookup"><span data-stu-id="6fead-125">Logon with an account that belongs to the SSO Administrators group.</span></span>  

  <span data-ttu-id="6fead-126">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6fead-126">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="6fead-127">Grupos de usuarios de SSO</span><span class="sxs-lookup"><span data-stu-id="6fead-127">SSO User Groups</span></span>](../core/sso-user-groups.md)
