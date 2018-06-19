---
title: 'Inicio de sesión único: Evento 10589 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0fe962bb-e9bb-4107-a5fb-21c180d54e21
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56bb848711a627ceaea70085d770db7b0c759e9a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271580"
---
# <a name="single-sign-on-event-10589"></a><span data-ttu-id="27cf8-102">Inicio de sesión único: Evento 10589</span><span class="sxs-lookup"><span data-stu-id="27cf8-102">Single Sign-On: Event 10589</span></span>
## <a name="details"></a><span data-ttu-id="27cf8-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="27cf8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="27cf8-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="27cf8-104">Product Name</span></span>|<span data-ttu-id="27cf8-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="27cf8-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="27cf8-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="27cf8-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="27cf8-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="27cf8-107">Event ID</span></span>|<span data-ttu-id="27cf8-108">10589</span><span class="sxs-lookup"><span data-stu-id="27cf8-108">10589</span></span>|  
|<span data-ttu-id="27cf8-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="27cf8-109">Event Source</span></span>|<span data-ttu-id="27cf8-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="27cf8-110">ENTSSO</span></span>|  
|<span data-ttu-id="27cf8-111">Componente</span><span class="sxs-lookup"><span data-stu-id="27cf8-111">Component</span></span>|<span data-ttu-id="27cf8-112">N/D</span><span class="sxs-lookup"><span data-stu-id="27cf8-112">N/A</span></span>|  
|<span data-ttu-id="27cf8-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="27cf8-113">Symbolic Name</span></span>|<span data-ttu-id="27cf8-114">SSO_ERROR_BACKUP_SECRET_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="27cf8-114">SSO_ERROR_BACKUP_SECRET_REQUIRED</span></span>|  
|<span data-ttu-id="27cf8-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="27cf8-115">Message Text</span></span>|<span data-ttu-id="27cf8-116">No se ha realizado la copia de seguridad del secreto principal.</span><span class="sxs-lookup"><span data-stu-id="27cf8-116">The master secret has not been backed up.</span></span> <span data-ttu-id="27cf8-117">Si pierde el secreto principal, toda la información almacenada en el sistema SSO se perderá de forma permanente y es posible que los sistemas no funcionen correctamente.</span><span class="sxs-lookup"><span data-stu-id="27cf8-117">If you lose the master secret all the information stored in the SSO system will be lost permanently and your systems may fail to work correctly.</span></span> <span data-ttu-id="27cf8-118">Use las herramientas administrativas de SSO para realizar la copia de seguridad del secreto principal.</span><span class="sxs-lookup"><span data-stu-id="27cf8-118">Please use the SSO administration tools to back up your master secret.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="27cf8-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="27cf8-119">Explanation</span></span>  
 <span data-ttu-id="27cf8-120">No se ha realizado la copia de seguridad del secreto principal.</span><span class="sxs-lookup"><span data-stu-id="27cf8-120">The master secret has not been backed up.</span></span> <span data-ttu-id="27cf8-121">Si pierde el secreto principal, toda la información almacenada en el sistema SSO se perderá de forma permanente y es posible que los sistemas no funcionen correctamente.</span><span class="sxs-lookup"><span data-stu-id="27cf8-121">If you lose the master secret all the information stored in the SSO system will be lost permanently and your systems may fail to work correctly.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="27cf8-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="27cf8-122">User Action</span></span>  
 <span data-ttu-id="27cf8-123">Para obtener información sobre la copia de seguridad del secreto principal, consulte [administrar el secreto principal](../core/managing-the-master-secret.md).</span><span class="sxs-lookup"><span data-stu-id="27cf8-123">For information on backing up the master secret, see [Managing the Master Secret](../core/managing-the-master-secret.md).</span></span>