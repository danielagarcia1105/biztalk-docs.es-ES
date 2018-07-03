---
title: 'De sesión único: Evento 11037 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b523ff56-112e-4798-97d2-b1b19e130ec7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ceec837a53d4cad3c236373a907497795efbd12a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998901"
---
# <a name="single-sign-on-event-11037"></a><span data-ttu-id="7475f-102">De sesión único: Evento 11037</span><span class="sxs-lookup"><span data-stu-id="7475f-102">Single Sign-On: Event 11037</span></span>
## <a name="details"></a><span data-ttu-id="7475f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="7475f-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="7475f-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="7475f-104">Product Name</span></span>   |                                                                                                               <span data-ttu-id="7475f-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="7475f-105">Enterprise Single Sign-On</span></span>                                                                                                               |
| <span data-ttu-id="7475f-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="7475f-106">Product Version</span></span> |                                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                               |
|    <span data-ttu-id="7475f-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="7475f-107">Event ID</span></span>     |                                                                                                                         <span data-ttu-id="7475f-108">11037</span><span class="sxs-lookup"><span data-stu-id="7475f-108">11037</span></span>                                                                                                                         |
|  <span data-ttu-id="7475f-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="7475f-109">Event Source</span></span>   |                                                                                                                        <span data-ttu-id="7475f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="7475f-110">ENTSSO</span></span>                                                                                                                         |
|    <span data-ttu-id="7475f-111">Componente</span><span class="sxs-lookup"><span data-stu-id="7475f-111">Component</span></span>    |                                                                                                                          <span data-ttu-id="7475f-112">N/D</span><span class="sxs-lookup"><span data-stu-id="7475f-112">N/A</span></span>                                                                                                                          |
|  <span data-ttu-id="7475f-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7475f-113">Symbolic Name</span></span>  |                                                                                                              <span data-ttu-id="7475f-114">SSO_INFO_PS_MAPPING_INVALID</span><span class="sxs-lookup"><span data-stu-id="7475f-114">SSO_INFO_PS_MAPPING_INVALID</span></span>                                                                                                              |
|  <span data-ttu-id="7475f-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7475f-115">Message Text</span></span>   | <span data-ttu-id="7475f-116">Cambio de contraseña externa.</span><span class="sxs-lookup"><span data-stu-id="7475f-116">External password change.</span></span> <span data-ttu-id="7475f-117">No se cambió la contraseña de la cuenta externa porque la asignación ya no es válida.%r</span><span class="sxs-lookup"><span data-stu-id="7475f-117">The password was not changed for the external account because the mapping is no longer valid.%r</span></span><br /><br /> <span data-ttu-id="7475f-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="7475f-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="7475f-119">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="7475f-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="7475f-120">Nombre de la aplicación: %3 %r</span><span class="sxs-lookup"><span data-stu-id="7475f-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="7475f-121">Cuenta externa: %4</span><span class="sxs-lookup"><span data-stu-id="7475f-121">External Account: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="7475f-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="7475f-122">Explanation</span></span>  
 <span data-ttu-id="7475f-123">La asignación ya no forma parte del grupo de usuarios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="7475f-123">The mapping is no longer a part of the Application Users group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7475f-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7475f-124">User Action</span></span>  
 <span data-ttu-id="7475f-125">El mensaje enumera el nombre de la cuenta externa y la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7475f-125">The message lists the name of the external account and application.</span></span> <span data-ttu-id="7475f-126">Puede usar esta información para averiguar por qué la asignación ya no es válida.</span><span class="sxs-lookup"><span data-stu-id="7475f-126">You can use this information to find out why the mapping is no longer valid.</span></span>