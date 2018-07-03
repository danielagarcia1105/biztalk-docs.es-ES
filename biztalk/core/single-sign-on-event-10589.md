---
title: 'De sesión único: Evento 10589 | Microsoft Docs'
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
ms.openlocfilehash: b1f8dd6c8a6045f9e4e1678aa06faec8bb783c1a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986189"
---
# <a name="single-sign-on-event-10589"></a><span data-ttu-id="fa77c-102">De sesión único: Evento 10589</span><span class="sxs-lookup"><span data-stu-id="fa77c-102">Single Sign-On: Event 10589</span></span>
## <a name="details"></a><span data-ttu-id="fa77c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="fa77c-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="fa77c-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="fa77c-104">Product Name</span></span>   |                                                                                                                     <span data-ttu-id="fa77c-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="fa77c-105">Enterprise Single Sign-On</span></span>                                                                                                                     |
| <span data-ttu-id="fa77c-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="fa77c-106">Product Version</span></span> |                                                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                     |
|    <span data-ttu-id="fa77c-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="fa77c-107">Event ID</span></span>     |                                                                                                                               <span data-ttu-id="fa77c-108">10589</span><span class="sxs-lookup"><span data-stu-id="fa77c-108">10589</span></span>                                                                                                                               |
|  <span data-ttu-id="fa77c-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="fa77c-109">Event Source</span></span>   |                                                                                                                              <span data-ttu-id="fa77c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="fa77c-110">ENTSSO</span></span>                                                                                                                               |
|    <span data-ttu-id="fa77c-111">Componente</span><span class="sxs-lookup"><span data-stu-id="fa77c-111">Component</span></span>    |                                                                                                                                <span data-ttu-id="fa77c-112">N/D</span><span class="sxs-lookup"><span data-stu-id="fa77c-112">N/A</span></span>                                                                                                                                |
|  <span data-ttu-id="fa77c-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="fa77c-113">Symbolic Name</span></span>  |                                                                                                                 <span data-ttu-id="fa77c-114">SSO_ERROR_BACKUP_SECRET_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="fa77c-114">SSO_ERROR_BACKUP_SECRET_REQUIRED</span></span>                                                                                                                  |
|  <span data-ttu-id="fa77c-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="fa77c-115">Message Text</span></span>   | <span data-ttu-id="fa77c-116">No se ha realizado la copia de seguridad del secreto principal.</span><span class="sxs-lookup"><span data-stu-id="fa77c-116">The master secret has not been backed up.</span></span> <span data-ttu-id="fa77c-117">Si pierde el secreto principal, toda la información almacenada en el sistema SSO se perderá de forma permanente y es posible que los sistemas no funcionen correctamente.</span><span class="sxs-lookup"><span data-stu-id="fa77c-117">If you lose the master secret all the information stored in the SSO system will be lost permanently and your systems may fail to work correctly.</span></span> <span data-ttu-id="fa77c-118">Use las herramientas administrativas de SSO para realizar la copia de seguridad del secreto principal.</span><span class="sxs-lookup"><span data-stu-id="fa77c-118">Please use the SSO administration tools to back up your master secret.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="fa77c-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="fa77c-119">Explanation</span></span>  
 <span data-ttu-id="fa77c-120">No se ha realizado la copia de seguridad del secreto principal.</span><span class="sxs-lookup"><span data-stu-id="fa77c-120">The master secret has not been backed up.</span></span> <span data-ttu-id="fa77c-121">Si pierde el secreto principal, toda la información almacenada en el sistema SSO se perderá de forma permanente y es posible que los sistemas no funcionen correctamente.</span><span class="sxs-lookup"><span data-stu-id="fa77c-121">If you lose the master secret all the information stored in the SSO system will be lost permanently and your systems may fail to work correctly.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fa77c-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="fa77c-122">User Action</span></span>  
 <span data-ttu-id="fa77c-123">Para obtener información sobre copias de seguridad del secreto principal, consulte [administrar el secreto principal](../core/managing-the-master-secret.md).</span><span class="sxs-lookup"><span data-stu-id="fa77c-123">For information on backing up the master secret, see [Managing the Master Secret](../core/managing-the-master-secret.md).</span></span>