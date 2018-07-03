---
title: 'De sesión único: Evento 10806 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 23650d6b-b6a4-4c41-96cd-476e5b0f7f63
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be61b0a48dde7b1c8de9ec716f4f9426c39fa0cd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002701"
---
# <a name="single-sign-on-event-10806"></a><span data-ttu-id="e871b-102">De sesión único: Evento 10806</span><span class="sxs-lookup"><span data-stu-id="e871b-102">Single Sign-On: Event 10806</span></span>
## <a name="details"></a><span data-ttu-id="e871b-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="e871b-103">Details</span></span>  
  
|                 |                                                                                   |
|-----------------|-----------------------------------------------------------------------------------|
|  <span data-ttu-id="e871b-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="e871b-104">Product Name</span></span>   |                             <span data-ttu-id="e871b-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="e871b-105">Enterprise Single Sign-On</span></span>                             |
| <span data-ttu-id="e871b-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="e871b-106">Product Version</span></span> |            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]             |
|    <span data-ttu-id="e871b-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="e871b-107">Event ID</span></span>     |                                       <span data-ttu-id="e871b-108">10806</span><span class="sxs-lookup"><span data-stu-id="e871b-108">10806</span></span>                                       |
|  <span data-ttu-id="e871b-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="e871b-109">Event Source</span></span>   |                                      <span data-ttu-id="e871b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e871b-110">ENTSSO</span></span>                                       |
|    <span data-ttu-id="e871b-111">Componente</span><span class="sxs-lookup"><span data-stu-id="e871b-111">Component</span></span>    |                                        <span data-ttu-id="e871b-112">N/D</span><span class="sxs-lookup"><span data-stu-id="e871b-112">N/A</span></span>                                        |
|  <span data-ttu-id="e871b-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e871b-113">Symbolic Name</span></span>  |                         <span data-ttu-id="e871b-114">ENTSSO_E_APP_ASSIGNED_TO_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="e871b-114">ENTSSO_E_APP_ASSIGNED_TO_ADAPTER</span></span>                          |
|  <span data-ttu-id="e871b-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e871b-115">Message Text</span></span>   | <span data-ttu-id="e871b-116">No se puede eliminar la aplicación porque actualmente está asignada a un adaptador.</span><span class="sxs-lookup"><span data-stu-id="e871b-116">The application cannot be deleted because it is currently assigned to an adapter.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="e871b-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="e871b-117">Explanation</span></span>  
 <span data-ttu-id="e871b-118">No se puede eliminar una aplicación si está asignada a un adaptador.</span><span class="sxs-lookup"><span data-stu-id="e871b-118">An application cannot be deleted when it is assigned to an adapter.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e871b-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e871b-119">User Action</span></span>  
 <span data-ttu-id="e871b-120">Quite la asignación de la aplicación del adaptador y, a continuación, elimínela.</span><span class="sxs-lookup"><span data-stu-id="e871b-120">Unassign the application from the adapter, and then delete it.</span></span>