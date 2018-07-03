---
title: 'De sesión único: Evento 10843 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 847e464e-5733-4703-905f-d44a4c4f5cc3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40b7e03f54d4c4ac2b7074d2aa13d771ce20a9e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013005"
---
# <a name="single-sign-on-event-10843"></a><span data-ttu-id="b0002-102">De sesión único: Evento 10843</span><span class="sxs-lookup"><span data-stu-id="b0002-102">Single Sign-On: Event 10843</span></span>
## <a name="details"></a><span data-ttu-id="b0002-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="b0002-103">Details</span></span>  
  
|                 |                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b0002-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="b0002-104">Product Name</span></span>   |                                                                      <span data-ttu-id="b0002-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="b0002-105">Enterprise Single Sign-On</span></span>                                                                      |
| <span data-ttu-id="b0002-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="b0002-106">Product Version</span></span> |                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                      |
|    <span data-ttu-id="b0002-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="b0002-107">Event ID</span></span>     |                                                                                <span data-ttu-id="b0002-108">10843</span><span class="sxs-lookup"><span data-stu-id="b0002-108">10843</span></span>                                                                                |
|  <span data-ttu-id="b0002-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="b0002-109">Event Source</span></span>   |                                                                               <span data-ttu-id="b0002-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b0002-110">ENTSSO</span></span>                                                                                |
|    <span data-ttu-id="b0002-111">Componente</span><span class="sxs-lookup"><span data-stu-id="b0002-111">Component</span></span>    |                                                                                 <span data-ttu-id="b0002-112">N/D</span><span class="sxs-lookup"><span data-stu-id="b0002-112">N/A</span></span>                                                                                 |
|  <span data-ttu-id="b0002-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b0002-113">Symbolic Name</span></span>  |                                                                         <span data-ttu-id="b0002-114">ENTSSO_E_NO_SECRET2</span><span class="sxs-lookup"><span data-stu-id="b0002-114">ENTSSO_E_NO_SECRET2</span></span>                                                                         |
|  <span data-ttu-id="b0002-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b0002-115">Message Text</span></span>   | <span data-ttu-id="b0002-116">No se puede realizar la tarea de cifrado o descifrado porque el secreto no está disponible en el servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="b0002-116">Cannot perform encryption or decryption because the secret is not available from the master secret server.</span></span> <span data-ttu-id="b0002-117">Consulte el registro de eventos (en el equipo "%1") para ver los errores relacionados.</span><span class="sxs-lookup"><span data-stu-id="b0002-117">See the event log (on computer ‘%1’) for related errors.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="b0002-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="b0002-118">Explanation</span></span>  
 <span data-ttu-id="b0002-119">Acceso denegado.</span><span class="sxs-lookup"><span data-stu-id="b0002-119">Access is denied.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b0002-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b0002-120">User Action</span></span>  
 <span data-ttu-id="b0002-121">El servidor secreto principal está desconectado o le falta el secreto principal necesario.</span><span class="sxs-lookup"><span data-stu-id="b0002-121">Either the master secret server is off-line, or the master secret server is missing the required master secret.</span></span> <span data-ttu-id="b0002-122">Consulte el registro de eventos en el equipo especificado para ver los errores relacionados.</span><span class="sxs-lookup"><span data-stu-id="b0002-122">See the event log on the specified computer for related errors.</span></span>