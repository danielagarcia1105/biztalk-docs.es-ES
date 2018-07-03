---
title: 'De sesión único: Evento 10809 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7331d12b-1000-4a60-83b3-f092968e0e51
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d4bf5ba006af8c479abc621accdc28296c0eae3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016067"
---
# <a name="single-sign-on-event-10809"></a><span data-ttu-id="e544e-102">De sesión único: Evento 10809</span><span class="sxs-lookup"><span data-stu-id="e544e-102">Single Sign-On: Event 10809</span></span>
## <a name="details"></a><span data-ttu-id="e544e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="e544e-103">Details</span></span>  
  
|                 |                                                                   |
|-----------------|-------------------------------------------------------------------|
|  <span data-ttu-id="e544e-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="e544e-104">Product Name</span></span>   |                     <span data-ttu-id="e544e-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="e544e-105">Enterprise Single Sign-On</span></span>                     |
| <span data-ttu-id="e544e-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="e544e-106">Product Version</span></span> |    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]     |
|    <span data-ttu-id="e544e-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="e544e-107">Event ID</span></span>     |                               <span data-ttu-id="e544e-108">10809</span><span class="sxs-lookup"><span data-stu-id="e544e-108">10809</span></span>                               |
|  <span data-ttu-id="e544e-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="e544e-109">Event Source</span></span>   |                              <span data-ttu-id="e544e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e544e-110">ENTSSO</span></span>                               |
|    <span data-ttu-id="e544e-111">Componente</span><span class="sxs-lookup"><span data-stu-id="e544e-111">Component</span></span>    |                                <span data-ttu-id="e544e-112">N/D</span><span class="sxs-lookup"><span data-stu-id="e544e-112">N/A</span></span>                                |
|  <span data-ttu-id="e544e-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e544e-113">Symbolic Name</span></span>  |                  <span data-ttu-id="e544e-114">ENTSSO_E_HISSO_APP_NOT_ENABLED</span><span class="sxs-lookup"><span data-stu-id="e544e-114">ENTSSO_E_HISSO_APP_NOT_ENABLED</span></span>                   |
|  <span data-ttu-id="e544e-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e544e-115">Message Text</span></span>   | <span data-ttu-id="e544e-116">La aplicación no está habilitada para Inicio de sesión único iniciado por host.</span><span class="sxs-lookup"><span data-stu-id="e544e-116">The application is not enabled for Host Initiated Single Sign-On.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="e544e-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="e544e-117">Explanation</span></span>  
 <span data-ttu-id="e544e-118">La aplicación no está habilitada para Inicio de sesión único iniciado por host.</span><span class="sxs-lookup"><span data-stu-id="e544e-118">The application is not enabled for Host Initiated Single Sign-On.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e544e-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e544e-119">User Action</span></span>  
 <span data-ttu-id="e544e-120">Use las herramientas administrativas para configurar el inicio de sesión único iniciado por host.</span><span class="sxs-lookup"><span data-stu-id="e544e-120">Use the administrative tools to configure Host Initiated Single Sign-On.</span></span> <span data-ttu-id="e544e-121">Esto establecerá el marcador</span><span class="sxs-lookup"><span data-stu-id="e544e-121">This will set the</span></span>  
  
 <span data-ttu-id="e544e-122">SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e544e-122">SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS flag on the application.</span></span>