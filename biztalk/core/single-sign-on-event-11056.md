---
title: 'De sesión único: Evento 11056 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 37e2dd5e-0fa4-4764-8ee1-de2ca2b263d1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 127ff9581779963cc93ff32987cff2549119efe8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010965"
---
# <a name="single-sign-on-event-11056"></a><span data-ttu-id="e455f-102">De sesión único: Evento 11056</span><span class="sxs-lookup"><span data-stu-id="e455f-102">Single Sign-On: Event 11056</span></span>
## <a name="details"></a><span data-ttu-id="e455f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="e455f-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                                                          |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e455f-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="e455f-104">Product Name</span></span>   |                                                                                                                                                <span data-ttu-id="e455f-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="e455f-105">Enterprise Single Sign-On</span></span>                                                                                                                                                 |
| <span data-ttu-id="e455f-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="e455f-106">Product Version</span></span> |                                                                                                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                |
|    <span data-ttu-id="e455f-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="e455f-107">Event ID</span></span>     |                                                                                                                                                          <span data-ttu-id="e455f-108">11056</span><span class="sxs-lookup"><span data-stu-id="e455f-108">11056</span></span>                                                                                                                                                           |
|  <span data-ttu-id="e455f-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="e455f-109">Event Source</span></span>   |                                                                                                                                                          <span data-ttu-id="e455f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e455f-110">ENTSSO</span></span>                                                                                                                                                          |
|    <span data-ttu-id="e455f-111">Componente</span><span class="sxs-lookup"><span data-stu-id="e455f-111">Component</span></span>    |                                                                                                                                                           <span data-ttu-id="e455f-112">N/D</span><span class="sxs-lookup"><span data-stu-id="e455f-112">N/A</span></span>                                                                                                                                                            |
|  <span data-ttu-id="e455f-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e455f-113">Symbolic Name</span></span>  |                                                                                                                                           <span data-ttu-id="e455f-114">SSO_WARN_PS_DIRECT_GET_CREDS_FAILED</span><span class="sxs-lookup"><span data-stu-id="e455f-114">SSO_WARN_PS_DIRECT_GET_CREDS_FAILED</span></span>                                                                                                                                            |
|  <span data-ttu-id="e455f-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e455f-115">Message Text</span></span>   | <span data-ttu-id="e455f-116">No se cambió directamente la contraseña de la cuenta externa porque no se pudieron obtener las credenciales externas existentes de la base de datos de SSO.%r</span><span class="sxs-lookup"><span data-stu-id="e455f-116">The password was not directly changed for the external account because the existing external credentials could not be obtained from the SSO database.%r</span></span><br /><br /> <span data-ttu-id="e455f-117">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="e455f-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="e455f-118">Nombre de la aplicación: %2 %r</span><span class="sxs-lookup"><span data-stu-id="e455f-118">Application Name: %2%r</span></span><br /><br /> <span data-ttu-id="e455f-119">Cuenta de Windows: %3 %r</span><span class="sxs-lookup"><span data-stu-id="e455f-119">Windows Account: %3%r</span></span><br /><br /> <span data-ttu-id="e455f-120">Cuenta externa: %4 %r</span><span class="sxs-lookup"><span data-stu-id="e455f-120">External Account: %4%r</span></span><br /><br /> <span data-ttu-id="e455f-121">Código de error: %5</span><span class="sxs-lookup"><span data-stu-id="e455f-121">Error Code: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="e455f-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="e455f-122">Explanation</span></span>  
 <span data-ttu-id="e455f-123">No se cambió directamente la contraseña de la cuenta externa porque no se pudieron obtener las credenciales externas existentes de la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="e455f-123">The password was not directly changed for the external account because the existing external credentials could not be obtained from the SSO database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e455f-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e455f-124">User Action</span></span>  
 <span data-ttu-id="e455f-125">Use la información proporcionada y póngase en contacto con los Servicios de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e455f-125">Use the information provided and contact Microsoft Product Support Services.</span></span>