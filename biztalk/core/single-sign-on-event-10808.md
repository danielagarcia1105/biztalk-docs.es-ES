---
title: 'De sesión único: Evento 10808 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b4efc1d-f163-4440-a78e-53065c6af36c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49d4e6ab0f6a9ea10ef28440f5b8399778fbc93b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971405"
---
# <a name="single-sign-on-event-10808"></a><span data-ttu-id="11135-102">De sesión único: Evento 10808</span><span class="sxs-lookup"><span data-stu-id="11135-102">Single Sign-On: Event 10808</span></span>
## <a name="details"></a><span data-ttu-id="11135-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="11135-103">Details</span></span>  
  
|                 |                                                                  |
|-----------------|------------------------------------------------------------------|
|  <span data-ttu-id="11135-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="11135-104">Product Name</span></span>   |                    <span data-ttu-id="11135-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="11135-105">Enterprise Single Sign-On</span></span>                     |
| <span data-ttu-id="11135-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="11135-106">Product Version</span></span> |    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]    |
|    <span data-ttu-id="11135-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="11135-107">Event ID</span></span>     |                              <span data-ttu-id="11135-108">10808</span><span class="sxs-lookup"><span data-stu-id="11135-108">10808</span></span>                               |
|  <span data-ttu-id="11135-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="11135-109">Event Source</span></span>   |                              <span data-ttu-id="11135-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="11135-110">ENTSSO</span></span>                              |
|    <span data-ttu-id="11135-111">Componente</span><span class="sxs-lookup"><span data-stu-id="11135-111">Component</span></span>    |                               <span data-ttu-id="11135-112">N/D</span><span class="sxs-lookup"><span data-stu-id="11135-112">N/A</span></span>                                |
|  <span data-ttu-id="11135-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="11135-113">Symbolic Name</span></span>  |                <span data-ttu-id="11135-114">ENTSSO_E_HISSO_SYSTEM_NOT_ENABLED</span><span class="sxs-lookup"><span data-stu-id="11135-114">ENTSSO_E_HISSO_SYSTEM_NOT_ENABLED</span></span>                 |
|  <span data-ttu-id="11135-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="11135-115">Message Text</span></span>   | <span data-ttu-id="11135-116">El sistema SSO no está habilitado para Inicio de sesión único iniciado por host.</span><span class="sxs-lookup"><span data-stu-id="11135-116">The SSO system is not enabled for Host Initiated Single Sign-On.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="11135-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="11135-117">Explanation</span></span>  
 <span data-ttu-id="11135-118">El sistema SSO no está habilitado para Inicio de sesión único iniciado por host.</span><span class="sxs-lookup"><span data-stu-id="11135-118">The SSO system is not enabled for Host Initiated Single Sign-On.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="11135-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="11135-119">User Action</span></span>  
 <span data-ttu-id="11135-120">Use las herramientas administrativas para configurar el inicio de sesión único iniciado por host.</span><span class="sxs-lookup"><span data-stu-id="11135-120">Use the administrative tools to configure Host Initiated Single Sign-On.</span></span> <span data-ttu-id="11135-121">Esto establecerá el marcador</span><span class="sxs-lookup"><span data-stu-id="11135-121">This will set the</span></span>  
  
 <span data-ttu-id="11135-122">SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS en la información global.</span><span class="sxs-lookup"><span data-stu-id="11135-122">SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS flag on the global information.</span></span>