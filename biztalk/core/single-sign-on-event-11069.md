---
title: 'De sesión único: Evento 11069 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1accfe68-000c-4b5e-909c-244e18eba110
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e9df27e7a5ac5f4fcedb10935fb8e63a6e0bea0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986165"
---
# <a name="single-sign-on-event-11069"></a><span data-ttu-id="4094b-102">De sesión único: Evento 11069</span><span class="sxs-lookup"><span data-stu-id="4094b-102">Single Sign-On: Event 11069</span></span>
## <a name="details"></a><span data-ttu-id="4094b-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="4094b-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="4094b-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="4094b-104">Product Name</span></span>   |                                                                                               <span data-ttu-id="4094b-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="4094b-105">Enterprise Single Sign-On</span></span>                                                                                               |
| <span data-ttu-id="4094b-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="4094b-106">Product Version</span></span> |                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    <span data-ttu-id="4094b-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="4094b-107">Event ID</span></span>     |                                                                                                         <span data-ttu-id="4094b-108">11069</span><span class="sxs-lookup"><span data-stu-id="4094b-108">11069</span></span>                                                                                                         |
|  <span data-ttu-id="4094b-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="4094b-109">Event Source</span></span>   |                                                                                                        <span data-ttu-id="4094b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="4094b-110">ENTSSO</span></span>                                                                                                         |
|    <span data-ttu-id="4094b-111">Componente</span><span class="sxs-lookup"><span data-stu-id="4094b-111">Component</span></span>    |                                                                                                          <span data-ttu-id="4094b-112">N/D</span><span class="sxs-lookup"><span data-stu-id="4094b-112">N/A</span></span>                                                                                                          |
|  <span data-ttu-id="4094b-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="4094b-113">Symbolic Name</span></span>  |                                                                                             <span data-ttu-id="4094b-114">SSO_WARN_PS_PCNS_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="4094b-114">SSO_WARN_PS_PCNS_NOT_ALLOWED</span></span>                                                                                              |
|  <span data-ttu-id="4094b-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="4094b-115">Message Text</span></span>   | <span data-ttu-id="4094b-116">Este servidor de SSO actualmente no está configurado para permitir cambios de contraseña de Windows desde PCNS.</span><span class="sxs-lookup"><span data-stu-id="4094b-116">This SSO server is currently not configured to allow Windows password changes from PCNS.</span></span> <span data-ttu-id="4094b-117">Use 'ssoconfig -allowPS PCNS yes' o la MMC de administración de SSO.%r</span><span class="sxs-lookup"><span data-stu-id="4094b-117">Use 'ssoconfig -allowPS PCNS yes' or the SSO Administration MMC.%r</span></span><br /><br /> <span data-ttu-id="4094b-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="4094b-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="4094b-119">Usuario cliente: %2</span><span class="sxs-lookup"><span data-stu-id="4094b-119">Client User: %2</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="4094b-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="4094b-120">Explanation</span></span>  
 <span data-ttu-id="4094b-121">Este servidor de SSO actualmente no está configurado para permitir cambios de contraseña de Windows desde PCNS.</span><span class="sxs-lookup"><span data-stu-id="4094b-121">This SSO server is currently not configured to allow Windows password changes from PCNS.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4094b-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="4094b-122">User Action</span></span>  
 <span data-ttu-id="4094b-123">Para permitir que los cambios de contraseña de Windows desde PCNS, en el **servidores complemento**, **propiedades de sincronización de contraseña** ficha, seleccione **Permitir sincronización de contraseñas desde PCNS.**</span><span class="sxs-lookup"><span data-stu-id="4094b-123">To allow Windows password changes from PCNS, in the **Servers Snap-In**, **Password Sync Properties** tab, select **Allow Password Sync from PCNS.**</span></span>  
  
 <span data-ttu-id="4094b-124">Para obtener más información, consulte [cómo usar el complemento de servidores](../core/how-to-use-the-servers-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="4094b-124">For more information, see [How to Use the Servers Snap-in](../core/how-to-use-the-servers-snap-in.md).</span></span>