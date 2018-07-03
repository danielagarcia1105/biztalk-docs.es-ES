---
title: 'De sesión único: Evento 10765 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e28fe42e-aa2b-4be4-b757-bc9c5c37526b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd49ead3fc30d3b98ea804a98a5882696ea749d7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975109"
---
# <a name="single-sign-on-event-10765"></a><span data-ttu-id="97751-102">De sesión único: Evento 10765</span><span class="sxs-lookup"><span data-stu-id="97751-102">Single Sign-On: Event 10765</span></span>
## <a name="details"></a><span data-ttu-id="97751-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="97751-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="97751-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="97751-104">Product Name</span></span>   |                 <span data-ttu-id="97751-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="97751-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="97751-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="97751-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="97751-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="97751-107">Event ID</span></span>     |                           <span data-ttu-id="97751-108">10765</span><span class="sxs-lookup"><span data-stu-id="97751-108">10765</span></span>                            |
|  <span data-ttu-id="97751-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="97751-109">Event Source</span></span>   |                           <span data-ttu-id="97751-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="97751-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="97751-111">Componente</span><span class="sxs-lookup"><span data-stu-id="97751-111">Component</span></span>    |                            <span data-ttu-id="97751-112">N/D</span><span class="sxs-lookup"><span data-stu-id="97751-112">N/A</span></span>                             |
|  <span data-ttu-id="97751-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="97751-113">Symbolic Name</span></span>  |                  <span data-ttu-id="97751-114">ENTSSO_E_NO_CREDENTIALS</span><span class="sxs-lookup"><span data-stu-id="97751-114">ENTSSO_E_NO_CREDENTIALS</span></span>                   |
|  <span data-ttu-id="97751-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="97751-115">Message Text</span></span>   |       <span data-ttu-id="97751-116">No se establecieron credenciales para la asignación.</span><span class="sxs-lookup"><span data-stu-id="97751-116">No credentials have been set for the mapping.</span></span>        |
  
## <a name="explanation"></a><span data-ttu-id="97751-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="97751-117">Explanation</span></span>  
 <span data-ttu-id="97751-118">Se solicitó GetCredentials en una asignación, pero la asignación especificada no tiene credenciales.</span><span class="sxs-lookup"><span data-stu-id="97751-118">You have requested a GetCredentials on a mapping, and the mapping specified has no credentials.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="97751-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="97751-119">User Action</span></span>  
 <span data-ttu-id="97751-120">Use la línea de comandos o el complemento MMC para establecer las credenciales de la asignación.</span><span class="sxs-lookup"><span data-stu-id="97751-120">Use the command line or the MMC Snap-in to set credentials for the mapping.</span></span>