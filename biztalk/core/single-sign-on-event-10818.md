---
title: 'De sesión único: Evento 10818 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6ad54646-4285-42e5-a270-d56935742a95
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 328e4286ed024923ab66e147e806ef5db5065b77
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972437"
---
# <a name="single-sign-on-event-10818"></a><span data-ttu-id="0c6c1-102">De sesión único: Evento 10818</span><span class="sxs-lookup"><span data-stu-id="0c6c1-102">Single Sign-On: Event 10818</span></span>
## <a name="details"></a><span data-ttu-id="0c6c1-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="0c6c1-103">Details</span></span>  
  
|                 |                                                                                 |
|-----------------|---------------------------------------------------------------------------------|
|  <span data-ttu-id="0c6c1-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="0c6c1-104">Product Name</span></span>   |                            <span data-ttu-id="0c6c1-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="0c6c1-105">Enterprise Single Sign-On</span></span>                            |
| <span data-ttu-id="0c6c1-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="0c6c1-106">Product Version</span></span> |           [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]            |
|    <span data-ttu-id="0c6c1-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="0c6c1-107">Event ID</span></span>     |                                      <span data-ttu-id="0c6c1-108">10818</span><span class="sxs-lookup"><span data-stu-id="0c6c1-108">10818</span></span>                                      |
|  <span data-ttu-id="0c6c1-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="0c6c1-109">Event Source</span></span>   |                                     <span data-ttu-id="0c6c1-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0c6c1-110">ENTSSO</span></span>                                      |
|    <span data-ttu-id="0c6c1-111">Componente</span><span class="sxs-lookup"><span data-stu-id="0c6c1-111">Component</span></span>    |                                       <span data-ttu-id="0c6c1-112">N/D</span><span class="sxs-lookup"><span data-stu-id="0c6c1-112">N/A</span></span>                                       |
|  <span data-ttu-id="0c6c1-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="0c6c1-113">Symbolic Name</span></span>  |                         <span data-ttu-id="0c6c1-114">ENTSSO_E_AMBIGUOUS_SYNC_FIELDS</span><span class="sxs-lookup"><span data-stu-id="0c6c1-114">ENTSSO_E_AMBIGUOUS_SYNC_FIELDS</span></span>                          |
|  <span data-ttu-id="0c6c1-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="0c6c1-115">Message Text</span></span>   | <span data-ttu-id="0c6c1-116">La aplicación debe tener dos campo o se debe marcar un solo campo para sincronización.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-116">The application must have two fields or only one field must be marked for sync.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="0c6c1-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="0c6c1-117">Explanation</span></span>  
 <span data-ttu-id="0c6c1-118">Si existen dos campos, sólo uno de ellos debe marcarse para sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-118">If there are more than two fields, then one and only one must be marked for password sync.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0c6c1-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="0c6c1-119">User Action</span></span>  
 <span data-ttu-id="0c6c1-120">Para solucionar este problema, debe eliminar la aplicación y crearla nuevamente para que respete estas pautas.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-120">To remedy this situation, you must delete the application and recreate it so that it follows these guidelines.</span></span>