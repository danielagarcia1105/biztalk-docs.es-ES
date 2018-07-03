---
title: 'De sesión único: Evento 11070 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb669df9-710a-4792-bdd4-cca0c03fcda2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 799e175f6425b91c98f6e96ec9f0bd73d8d0ebdf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994325"
---
# <a name="single-sign-on-event-11070"></a><span data-ttu-id="4892a-102">De sesión único: Evento 11070</span><span class="sxs-lookup"><span data-stu-id="4892a-102">Single Sign-On: Event 11070</span></span>
## <a name="details"></a><span data-ttu-id="4892a-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="4892a-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="4892a-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="4892a-104">Product Name</span></span>   |                                                                                               <span data-ttu-id="4892a-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="4892a-105">Enterprise Single Sign-On</span></span>                                                                                               |
| <span data-ttu-id="4892a-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="4892a-106">Product Version</span></span> |                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    <span data-ttu-id="4892a-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="4892a-107">Event ID</span></span>     |                                                                                                         <span data-ttu-id="4892a-108">11070</span><span class="sxs-lookup"><span data-stu-id="4892a-108">11070</span></span>                                                                                                         |
|  <span data-ttu-id="4892a-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="4892a-109">Event Source</span></span>   |                                                                                                        <span data-ttu-id="4892a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="4892a-110">ENTSSO</span></span>                                                                                                         |
|    <span data-ttu-id="4892a-111">Componente</span><span class="sxs-lookup"><span data-stu-id="4892a-111">Component</span></span>    |                                                                                                          <span data-ttu-id="4892a-112">N/D</span><span class="sxs-lookup"><span data-stu-id="4892a-112">N/A</span></span>                                                                                                          |
|  <span data-ttu-id="4892a-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="4892a-113">Symbolic Name</span></span>  |                                                                                             <span data-ttu-id="4892a-114">SSO_WARN_PS_MIIS_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="4892a-114">SSO_WARN_PS_MIIS_NOT_ALLOWED</span></span>                                                                                              |
|  <span data-ttu-id="4892a-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="4892a-115">Message Text</span></span>   | <span data-ttu-id="4892a-116">Este servidor de SSO actualmente no está configurado para permitir cambios de contraseña de Windows desde MIIS.</span><span class="sxs-lookup"><span data-stu-id="4892a-116">This SSO server is currently not configured to allow Windows password changes from MIIS.</span></span> <span data-ttu-id="4892a-117">Use 'ssoconfig -allowPS MIIS yes' o la MMC de administración de SSO.%r</span><span class="sxs-lookup"><span data-stu-id="4892a-117">Use 'ssoconfig -allowPS MIIS yes' or the SSO Administration MMC.%r</span></span><br /><br /> <span data-ttu-id="4892a-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="4892a-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="4892a-119">Usuario cliente: %2</span><span class="sxs-lookup"><span data-stu-id="4892a-119">Client User: %2</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="4892a-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="4892a-120">Explanation</span></span>  
 <span data-ttu-id="4892a-121">Este servidor de SSO actualmente no está configurado para permitir cambios de contraseña de Windows desde MIIS.</span><span class="sxs-lookup"><span data-stu-id="4892a-121">This SSO server is currently not configured to allow Windows password changes from MIIS.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4892a-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="4892a-122">User Action</span></span>  
 <span data-ttu-id="4892a-123">Para permitir que los cambios de contraseña de Windows desde MIIS, en el **servidores complemento**, **propiedades de sincronización de contraseña** ficha, seleccione **Permitir sincronización de contraseñas desde MIIS.**</span><span class="sxs-lookup"><span data-stu-id="4892a-123">To allow Windows password changes from MIIS, in the **Servers Snap-In**, **Password Sync Properties** tab, select **Allow Password Sync from MIIS.**</span></span>  
  
 <span data-ttu-id="4892a-124">Para obtener más información, consulte [cómo usar el complemento de servidores](../core/how-to-use-the-servers-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="4892a-124">For more information, see [How to Use the Servers Snap-in](../core/how-to-use-the-servers-snap-in.md).</span></span>