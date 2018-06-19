---
title: 'Inicio de sesión único: Evento 10817 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f1668b81-e7f4-46d2-aebe-47007f70372b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c94f677ccd14dd821886210f9e4c55efd754a404
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276748"
---
# <a name="single-sign-on-event-10817"></a><span data-ttu-id="9014f-102">Inicio de sesión único: Evento 10817</span><span class="sxs-lookup"><span data-stu-id="9014f-102">Single Sign-On: Event 10817</span></span>
## <a name="details"></a><span data-ttu-id="9014f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="9014f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9014f-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="9014f-104">Product Name</span></span>|<span data-ttu-id="9014f-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="9014f-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="9014f-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="9014f-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="9014f-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="9014f-107">Event ID</span></span>|<span data-ttu-id="9014f-108">10817</span><span class="sxs-lookup"><span data-stu-id="9014f-108">10817</span></span>|  
|<span data-ttu-id="9014f-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="9014f-109">Event Source</span></span>|<span data-ttu-id="9014f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="9014f-110">ENTSSO</span></span>|  
|<span data-ttu-id="9014f-111">Componente</span><span class="sxs-lookup"><span data-stu-id="9014f-111">Component</span></span>|<span data-ttu-id="9014f-112">N/D</span><span class="sxs-lookup"><span data-stu-id="9014f-112">N/A</span></span>|  
|<span data-ttu-id="9014f-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="9014f-113">Symbolic Name</span></span>|<span data-ttu-id="9014f-114">ENTSSO_E_NOTIFICATION_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="9014f-114">ENTSSO_E_NOTIFICATION_NOT_FOUND</span></span>|  
|<span data-ttu-id="9014f-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="9014f-115">Message Text</span></span>|<span data-ttu-id="9014f-116">No se encuentra la notificación especificada.</span><span class="sxs-lookup"><span data-stu-id="9014f-116">The specified notification was not found.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9014f-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="9014f-117">Explanation</span></span>  
 <span data-ttu-id="9014f-118">El cambio de contraseña especificó un GUID de notificación que no se puede encontrar.</span><span class="sxs-lookup"><span data-stu-id="9014f-118">The password change specified a notification GUID which cannot be found.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9014f-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="9014f-119">User Action</span></span>  
 <span data-ttu-id="9014f-120">Para determinar el GUID adecuado de la notificación, consulte la configuración del adaptador de sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="9014f-120">See the configuration for this password sync adapter to determine the proper GUID of the notification.</span></span>