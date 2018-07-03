---
title: 'De sesión único: Evento 10567 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3f29c8d9-3da2-4de7-b61f-8c586382b68f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ac0bed16a9e80860b23738e175b2bdafb883283
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975933"
---
# <a name="single-sign-on-event-10567"></a><span data-ttu-id="ea2d7-102">De sesión único: Evento 10567</span><span class="sxs-lookup"><span data-stu-id="ea2d7-102">Single Sign-On: Event 10567</span></span>
## <a name="details"></a><span data-ttu-id="ea2d7-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ea2d7-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                           |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ea2d7-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ea2d7-104">Product Name</span></span>   |                                                                                         <span data-ttu-id="ea2d7-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="ea2d7-105">Enterprise Single Sign-On</span></span>                                                                                         |
| <span data-ttu-id="ea2d7-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ea2d7-106">Product Version</span></span> |                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                         |
|    <span data-ttu-id="ea2d7-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ea2d7-107">Event ID</span></span>     |                                                                                                   <span data-ttu-id="ea2d7-108">10567</span><span class="sxs-lookup"><span data-stu-id="ea2d7-108">10567</span></span>                                                                                                   |
|  <span data-ttu-id="ea2d7-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ea2d7-109">Event Source</span></span>   |                                                                                                  <span data-ttu-id="ea2d7-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ea2d7-110">ENTSSO</span></span>                                                                                                   |
|    <span data-ttu-id="ea2d7-111">Componente</span><span class="sxs-lookup"><span data-stu-id="ea2d7-111">Component</span></span>    |                                                                                                    <span data-ttu-id="ea2d7-112">N/D</span><span class="sxs-lookup"><span data-stu-id="ea2d7-112">N/A</span></span>                                                                                                    |
|  <span data-ttu-id="ea2d7-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ea2d7-113">Symbolic Name</span></span>  |                                                                                      <span data-ttu-id="ea2d7-114">SSO_WARN_INVALID_APP_USER_GROUP</span><span class="sxs-lookup"><span data-stu-id="ea2d7-114">SSO_WARN_INVALID_APP_USER_GROUP</span></span>                                                                                      |
|  <span data-ttu-id="ea2d7-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ea2d7-115">Message Text</span></span>   | <span data-ttu-id="ea2d7-116">Cuenta de usuarios de aplicación no válida para actualización de la aplicación.%r</span><span class="sxs-lookup"><span data-stu-id="ea2d7-116">The Application Users account is not valid for application update.%r</span></span><br /><br /> <span data-ttu-id="ea2d7-117">Nombre de la aplicación: %1 %r</span><span class="sxs-lookup"><span data-stu-id="ea2d7-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="ea2d7-118">Usuarios de aplicación: %2 %r</span><span class="sxs-lookup"><span data-stu-id="ea2d7-118">Application Users: %2%r</span></span><br /><br /> <span data-ttu-id="ea2d7-119">Cuentas no válidas: %3 %r</span><span class="sxs-lookup"><span data-stu-id="ea2d7-119">Invalid accounts: %3%r</span></span><br /><br /> <span data-ttu-id="ea2d7-120">Código de error: %4</span><span class="sxs-lookup"><span data-stu-id="ea2d7-120">Error Code: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="ea2d7-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="ea2d7-121">Explanation</span></span>  
 <span data-ttu-id="ea2d7-122">Ha intentado actualizar una cuenta de usuarios de aplicación que no es válida o que no existe.</span><span class="sxs-lookup"><span data-stu-id="ea2d7-122">You have attempted to update an Application Users account which is either invalid or does not exist.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ea2d7-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ea2d7-123">User Action</span></span>  
 <span data-ttu-id="ea2d7-124">Compruebe si el nombre de la cuenta es correcto.</span><span class="sxs-lookup"><span data-stu-id="ea2d7-124">Check that the name of the account is correct.</span></span>