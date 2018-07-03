---
title: 'De sesión único: Evento 10599 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd671aa5-b243-4081-9a4e-87103be9a1d7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 326b94be9c05be6645a21b10f3ea302cf63be8e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015685"
---
# <a name="single-sign-on-event-10599"></a><span data-ttu-id="55584-102">De sesión único: Evento 10599</span><span class="sxs-lookup"><span data-stu-id="55584-102">Single Sign-On: Event 10599</span></span>
## <a name="details"></a><span data-ttu-id="55584-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="55584-103">Details</span></span>  
  
|                 |                                                                                                                                                                                    |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="55584-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="55584-104">Product Name</span></span>   |                                                                             <span data-ttu-id="55584-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="55584-105">Enterprise Single Sign-On</span></span>                                                                              |
| <span data-ttu-id="55584-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="55584-106">Product Version</span></span> |                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                             |
|    <span data-ttu-id="55584-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="55584-107">Event ID</span></span>     |                                                                                       <span data-ttu-id="55584-108">10599</span><span class="sxs-lookup"><span data-stu-id="55584-108">10599</span></span>                                                                                        |
|  <span data-ttu-id="55584-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="55584-109">Event Source</span></span>   |                                                                                       <span data-ttu-id="55584-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="55584-110">ENTSSO</span></span>                                                                                       |
|    <span data-ttu-id="55584-111">Componente</span><span class="sxs-lookup"><span data-stu-id="55584-111">Component</span></span>    |                                                                                        <span data-ttu-id="55584-112">N/D</span><span class="sxs-lookup"><span data-stu-id="55584-112">N/A</span></span>                                                                                         |
|  <span data-ttu-id="55584-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="55584-113">Symbolic Name</span></span>  |                                                                              <span data-ttu-id="55584-114">SSO_WARN_ENTSSO_IS_ADMIN</span><span class="sxs-lookup"><span data-stu-id="55584-114">SSO_WARN_ENTSSO_IS_ADMIN</span></span>                                                                              |
|  <span data-ttu-id="55584-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="55584-115">Message Text</span></span>   | <span data-ttu-id="55584-116">El servicio SSO se está ejecutando en una cuenta de administrador local.</span><span class="sxs-lookup"><span data-stu-id="55584-116">The SSO service is running under a local administrator account.</span></span> <span data-ttu-id="55584-117">Por motivos de seguridad, esta práctica no es recomendable.</span><span class="sxs-lookup"><span data-stu-id="55584-117">This is not recommended for security reasons.</span></span> <span data-ttu-id="55584-118">Consulte la documentación de details.%r</span><span class="sxs-lookup"><span data-stu-id="55584-118">See documentation for details.%r</span></span><br /><br /> <span data-ttu-id="55584-119">Cuenta de servicio SSO: %1</span><span class="sxs-lookup"><span data-stu-id="55584-119">SSO Service Account: %1</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="55584-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="55584-120">Explanation</span></span>  
 <span data-ttu-id="55584-121">El servicio SSO especificado se está ejecutando en una cuenta de administrador local.</span><span class="sxs-lookup"><span data-stu-id="55584-121">The SSO service specified is running under a local administrator account.</span></span> <span data-ttu-id="55584-122">Por motivos de seguridad, esta práctica no es recomendable.</span><span class="sxs-lookup"><span data-stu-id="55584-122">This is not recommended for security reasons.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="55584-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="55584-123">User Action</span></span>  
 <span data-ttu-id="55584-124">Para obtener más información, consulte [recomendaciones de seguridad de inicio de sesión único](../core/sso-security-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="55584-124">For more information, see [SSO Security Recommendations](../core/sso-security-recommendations.md).</span></span>