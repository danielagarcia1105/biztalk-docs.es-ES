---
title: 'De sesión único: Evento 10819 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ffa5e977-c8b9-4568-8963-0d4cf44b5637
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f196bb49cd0e5825551bbffe45757c327e2cbcca
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972117"
---
# <a name="single-sign-on-event-10819"></a><span data-ttu-id="fdd0e-102">De sesión único: Evento 10819</span><span class="sxs-lookup"><span data-stu-id="fdd0e-102">Single Sign-On: Event 10819</span></span>
## <a name="details"></a><span data-ttu-id="fdd0e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="fdd0e-103">Details</span></span>  
  
|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  <span data-ttu-id="fdd0e-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="fdd0e-104">Product Name</span></span>   |                         <span data-ttu-id="fdd0e-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="fdd0e-105">Enterprise Single Sign-On</span></span>                         |
| <span data-ttu-id="fdd0e-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="fdd0e-106">Product Version</span></span> |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    <span data-ttu-id="fdd0e-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="fdd0e-107">Event ID</span></span>     |                                   <span data-ttu-id="fdd0e-108">10819</span><span class="sxs-lookup"><span data-stu-id="fdd0e-108">10819</span></span>                                   |
|  <span data-ttu-id="fdd0e-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="fdd0e-109">Event Source</span></span>   |                                  <span data-ttu-id="fdd0e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="fdd0e-110">ENTSSO</span></span>                                   |
|    <span data-ttu-id="fdd0e-111">Componente</span><span class="sxs-lookup"><span data-stu-id="fdd0e-111">Component</span></span>    |                                    <span data-ttu-id="fdd0e-112">N/D</span><span class="sxs-lookup"><span data-stu-id="fdd0e-112">N/A</span></span>                                    |
|  <span data-ttu-id="fdd0e-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="fdd0e-113">Symbolic Name</span></span>  |                         <span data-ttu-id="fdd0e-114">ENTSSO_E_MAPPING_CONFLICT</span><span class="sxs-lookup"><span data-stu-id="fdd0e-114">ENTSSO_E_MAPPING_CONFLICT</span></span>                         |
|  <span data-ttu-id="fdd0e-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="fdd0e-115">Message Text</span></span>   | <span data-ttu-id="fdd0e-116">La cuenta externa no se actualizó debido a un conflicto de asignación.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-116">The external account was not updated because there is a mapping conflict.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="fdd0e-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="fdd0e-117">Explanation</span></span>  
 <span data-ttu-id="fdd0e-118">La cuenta externa no se actualizó debido a un conflicto de asignación.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-118">The external account was not updated because there is a mapping conflict.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fdd0e-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="fdd0e-119">User Action</span></span>  
 <span data-ttu-id="fdd0e-120">Si éste es el comportamiento esperado, no es necesario realizar ninguna acción. El mensaje es solamente informativo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-120">If this is expected behavior then no action is required, this message is informational only.</span></span> <span data-ttu-id="fdd0e-121">Si se deben permitir conflictos de asignación, configure la aplicación adecuadamente.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-121">If mapping conflicts should be allowed then configure the application accordingly.</span></span>  
  
 <span data-ttu-id="fdd0e-122">Para obtener más información sobre los conflictos de asignación, consulte **propiedades del adaptador de sincronización de contraseñas: opciones** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="fdd0e-122">For more information on mapping conflicts, see **Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>