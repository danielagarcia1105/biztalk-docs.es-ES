---
title: 'De sesión único: Evento 10850 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04e2af52-d35b-491a-a983-d80442dd6aef
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0430d5d7ea3ff2a0fabf9c9698acffe15b644f24
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011365"
---
# <a name="single-sign-on-event-10850"></a><span data-ttu-id="a090a-102">De sesión único: Evento 10850</span><span class="sxs-lookup"><span data-stu-id="a090a-102">Single Sign-On: Event 10850</span></span>
## <a name="details"></a><span data-ttu-id="a090a-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a090a-103">Details</span></span>  
  
|                 |                                                                     |
|-----------------|---------------------------------------------------------------------|
|  <span data-ttu-id="a090a-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="a090a-104">Product Name</span></span>   |                      <span data-ttu-id="a090a-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="a090a-105">Enterprise Single Sign-On</span></span>                      |
| <span data-ttu-id="a090a-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="a090a-106">Product Version</span></span> |     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]      |
|    <span data-ttu-id="a090a-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="a090a-107">Event ID</span></span>     |                                <span data-ttu-id="a090a-108">10850</span><span class="sxs-lookup"><span data-stu-id="a090a-108">10850</span></span>                                |
|  <span data-ttu-id="a090a-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="a090a-109">Event Source</span></span>   |                               <span data-ttu-id="a090a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a090a-110">ENTSSO</span></span>                                |
|    <span data-ttu-id="a090a-111">Componente</span><span class="sxs-lookup"><span data-stu-id="a090a-111">Component</span></span>    |                                 <span data-ttu-id="a090a-112">N/D</span><span class="sxs-lookup"><span data-stu-id="a090a-112">N/A</span></span>                                 |
|  <span data-ttu-id="a090a-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a090a-113">Symbolic Name</span></span>  |                 <span data-ttu-id="a090a-114">ENTSSO_E_ENABLED_NOT_ALLOWED_CREATE</span><span class="sxs-lookup"><span data-stu-id="a090a-114">ENTSSO_E_ENABLED_NOT_ALLOWED_CREATE</span></span>                 |
|  <span data-ttu-id="a090a-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a090a-115">Message Text</span></span>   | <span data-ttu-id="a090a-116">No se puede crear una aplicación con el marcador "habilitado" especificado.</span><span class="sxs-lookup"><span data-stu-id="a090a-116">An application cannot be created with the 'enabled' flag specified.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="a090a-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="a090a-117">Explanation</span></span>  
 <span data-ttu-id="a090a-118">Antes de habilitar una aplicación, se debe crear la aplicación y, a continuación, especificar la información de campo de cada uno de sus campos (por ejemplo, Id. de usuario y Contraseña).</span><span class="sxs-lookup"><span data-stu-id="a090a-118">Before enabling an application, it is necessary to both create the application and enter the field information for each of its fields (i.e. UserID and Password).</span></span> <span data-ttu-id="a090a-119">No es posible crear una aplicación con el campo "habilitado" ya establecido.</span><span class="sxs-lookup"><span data-stu-id="a090a-119">It is not possible to create an application with the “enabled” field already set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a090a-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a090a-120">User Action</span></span>  
 <span data-ttu-id="a090a-121">Vuelva a crear la aplicación (mediante la API de creación de aplicaciones o el Asistente para creación de nueva aplicación afiliada).</span><span class="sxs-lookup"><span data-stu-id="a090a-121">Create the application again (using either the Create Application API or the Create New Affiliate Application Wizard).</span></span> <span data-ttu-id="a090a-122">Una vez completada la aplicación y rellenados los campos, habilítela.</span><span class="sxs-lookup"><span data-stu-id="a090a-122">When the application is complete and the fields populated, enable the application.</span></span>