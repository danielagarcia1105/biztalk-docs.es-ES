---
title: 'De sesión único: Evento 10848 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 61888420-29a6-4c64-a884-1b074b586f21
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59a324ff0a5de2ac6d2292692f2132c10aaabc5b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991037"
---
# <a name="single-sign-on-event-10848"></a><span data-ttu-id="008f9-102">De sesión único: Evento 10848</span><span class="sxs-lookup"><span data-stu-id="008f9-102">Single Sign-On: Event 10848</span></span>
## <a name="details"></a><span data-ttu-id="008f9-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="008f9-103">Details</span></span>  
  
|                 |                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------|
|  <span data-ttu-id="008f9-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="008f9-104">Product Name</span></span>   |                                 <span data-ttu-id="008f9-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="008f9-105">Enterprise Single Sign-On</span></span>                                  |
| <span data-ttu-id="008f9-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="008f9-106">Product Version</span></span> |                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                 |
|    <span data-ttu-id="008f9-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="008f9-107">Event ID</span></span>     |                                           <span data-ttu-id="008f9-108">10848</span><span class="sxs-lookup"><span data-stu-id="008f9-108">10848</span></span>                                            |
|  <span data-ttu-id="008f9-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="008f9-109">Event Source</span></span>   |                                           <span data-ttu-id="008f9-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="008f9-110">ENTSSO</span></span>                                           |
|    <span data-ttu-id="008f9-111">Componente</span><span class="sxs-lookup"><span data-stu-id="008f9-111">Component</span></span>    |                                            <span data-ttu-id="008f9-112">N/D</span><span class="sxs-lookup"><span data-stu-id="008f9-112">N/A</span></span>                                             |
|  <span data-ttu-id="008f9-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="008f9-113">Symbolic Name</span></span>  |                         <span data-ttu-id="008f9-114">ENTSSO_E_DIRECT_SYNC_NOT_ALLOWED_AMBIGUOUS</span><span class="sxs-lookup"><span data-stu-id="008f9-114">ENTSSO_E_DIRECT_SYNC_NOT_ALLOWED_AMBIGUOUS</span></span>                         |
|  <span data-ttu-id="008f9-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="008f9-115">Message Text</span></span>   | <span data-ttu-id="008f9-116">No se permite la sincronización directa de contraseñas de la aplicación porque sus campos son ambiguos.</span><span class="sxs-lookup"><span data-stu-id="008f9-116">Direct password sync is not allowed for this application because its fields are ambiguous.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="008f9-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="008f9-117">Explanation</span></span>  
 <span data-ttu-id="008f9-118">Si existen dos campos, sólo uno de ellos debe marcarse para sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="008f9-118">If there are more than two fields, then one and only one must be marked for password sync.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="008f9-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="008f9-119">User Action</span></span>  
 <span data-ttu-id="008f9-120">Para solucionar este problema, debe eliminar la aplicación y crearla nuevamente para que respete estas pautas.</span><span class="sxs-lookup"><span data-stu-id="008f9-120">To remedy this situation, you must delete the application and recreate it so that it follows these guidelines.</span></span>