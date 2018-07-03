---
title: 'De sesión único: Evento 11071 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c0f61b9-cd86-482b-a8fe-0093a928c89b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74bc4793937574cc90021b95b6c1850409d57871
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975893"
---
# <a name="single-sign-on-event-11071"></a><span data-ttu-id="6f5b0-102">De sesión único: Evento 11071</span><span class="sxs-lookup"><span data-stu-id="6f5b0-102">Single Sign-On: Event 11071</span></span>
## <a name="details"></a><span data-ttu-id="6f5b0-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="6f5b0-103">Details</span></span>  
  
|                 |                                                                                                                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="6f5b0-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="6f5b0-104">Product Name</span></span>   |                                                                                   <span data-ttu-id="6f5b0-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="6f5b0-105">Enterprise Single Sign-On</span></span>                                                                                   |
| <span data-ttu-id="6f5b0-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="6f5b0-106">Product Version</span></span> |                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                   |
|    <span data-ttu-id="6f5b0-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="6f5b0-107">Event ID</span></span>     |                                                                                             <span data-ttu-id="6f5b0-108">11071</span><span class="sxs-lookup"><span data-stu-id="6f5b0-108">11071</span></span>                                                                                             |
|  <span data-ttu-id="6f5b0-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="6f5b0-109">Event Source</span></span>   |                                                                                            <span data-ttu-id="6f5b0-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="6f5b0-110">ENTSSO</span></span>                                                                                             |
|    <span data-ttu-id="6f5b0-111">Componente</span><span class="sxs-lookup"><span data-stu-id="6f5b0-111">Component</span></span>    |                                                                                              <span data-ttu-id="6f5b0-112">N/D</span><span class="sxs-lookup"><span data-stu-id="6f5b0-112">N/A</span></span>                                                                                              |
|  <span data-ttu-id="6f5b0-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="6f5b0-113">Symbolic Name</span></span>  |                                                                         <span data-ttu-id="6f5b0-114">SSO_WARN_PS_WIN_CHANGE_DISCARDED_ZERO_LENGTH</span><span class="sxs-lookup"><span data-stu-id="6f5b0-114">SSO_WARN_PS_WIN_CHANGE_DISCARDED_ZERO_LENGTH</span></span>                                                                          |
|  <span data-ttu-id="6f5b0-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="6f5b0-115">Message Text</span></span>   | <span data-ttu-id="6f5b0-116">Se descartó el cambio de contraseña de Windows dado que su longitud es de cero caracteres.%r</span><span class="sxs-lookup"><span data-stu-id="6f5b0-116">A Windows password change was discarded because the Windows password length is zero characters.%r</span></span><br /><br /> <span data-ttu-id="6f5b0-117">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="6f5b0-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="6f5b0-118">Cuenta de Windows: %2 %r</span><span class="sxs-lookup"><span data-stu-id="6f5b0-118">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="6f5b0-119">Usuario cliente: %3</span><span class="sxs-lookup"><span data-stu-id="6f5b0-119">Client User: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="6f5b0-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="6f5b0-120">Explanation</span></span>  
 <span data-ttu-id="6f5b0-121">Se descartó el cambio de contraseña de Windows dado que su longitud es de cero caracteres.</span><span class="sxs-lookup"><span data-stu-id="6f5b0-121">A Windows password change was discarded because the Windows password length is zero characters.</span></span> <span data-ttu-id="6f5b0-122">Se proporcionan la cuenta de Windows y el nombre de cuenta.</span><span class="sxs-lookup"><span data-stu-id="6f5b0-122">The Windows account and client user name are provided.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6f5b0-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="6f5b0-123">User Action</span></span>  
 <span data-ttu-id="6f5b0-124">Vuelva a cambiar la contraseña con el número y el tipo de caracteres requeridos por el sistema SSO.</span><span class="sxs-lookup"><span data-stu-id="6f5b0-124">Change the password again, using the number and type of characters required by your SSO system.</span></span>