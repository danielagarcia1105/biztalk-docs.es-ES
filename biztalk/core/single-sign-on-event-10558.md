---
title: 'De sesión único: Evento 10558 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 84637b67-09df-4c1e-b9f2-85a738ba0d7a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d9a281d6a6ca20a274db4b3ffe5b2697ff812c2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974875"
---
# <a name="single-sign-on-event-10558"></a><span data-ttu-id="99d04-102">De sesión único: Evento 10558</span><span class="sxs-lookup"><span data-stu-id="99d04-102">Single Sign-On: Event 10558</span></span>
## <a name="details"></a><span data-ttu-id="99d04-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="99d04-103">Details</span></span>  
  
|                 |                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="99d04-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="99d04-104">Product Name</span></span>   |                                                                                  <span data-ttu-id="99d04-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="99d04-105">Enterprise Single Sign-On</span></span>                                                                                   |
| <span data-ttu-id="99d04-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="99d04-106">Product Version</span></span> |                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    <span data-ttu-id="99d04-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="99d04-107">Event ID</span></span>     |                                                                                            <span data-ttu-id="99d04-108">10558</span><span class="sxs-lookup"><span data-stu-id="99d04-108">10558</span></span>                                                                                             |
|  <span data-ttu-id="99d04-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="99d04-109">Event Source</span></span>   |                                                                                            <span data-ttu-id="99d04-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="99d04-110">ENTSSO</span></span>                                                                                            |
|    <span data-ttu-id="99d04-111">Componente</span><span class="sxs-lookup"><span data-stu-id="99d04-111">Component</span></span>    |                                                                                             <span data-ttu-id="99d04-112">N/D</span><span class="sxs-lookup"><span data-stu-id="99d04-112">N/A</span></span>                                                                                              |
|  <span data-ttu-id="99d04-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="99d04-113">Symbolic Name</span></span>  |                                                                                  <span data-ttu-id="99d04-114">SSO_WARN_USER_OWN_MAPPINGS</span><span class="sxs-lookup"><span data-stu-id="99d04-114">SSO_WARN_USER_OWN_MAPPINGS</span></span>                                                                                  |
|  <span data-ttu-id="99d04-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="99d04-115">Message Text</span></span>   | <span data-ttu-id="99d04-116">Sólo se permiten usuarios de aplicación para controlar sus propias asignaciones.%r</span><span class="sxs-lookup"><span data-stu-id="99d04-116">Application Users are only allowed to control their own mappings.%r</span></span><br /><br /> <span data-ttu-id="99d04-117">Nombre de dominio: %1 %r</span><span class="sxs-lookup"><span data-stu-id="99d04-117">Domain Name: %1%r</span></span><br /><br /> <span data-ttu-id="99d04-118">Nombre de usuario: %2 %r</span><span class="sxs-lookup"><span data-stu-id="99d04-118">User Name: %2%r</span></span><br /><br /> <span data-ttu-id="99d04-119">Nombre de la aplicación: %3 %r</span><span class="sxs-lookup"><span data-stu-id="99d04-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="99d04-120">Usuario cliente: %4</span><span class="sxs-lookup"><span data-stu-id="99d04-120">Client User: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="99d04-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="99d04-121">Explanation</span></span>  
 <span data-ttu-id="99d04-122">Un usuario de aplicación intentó controlar las asignaciones de otro usuario.</span><span class="sxs-lookup"><span data-stu-id="99d04-122">An attempt was made by an Application User to control the mappings of a different user.</span></span> <span data-ttu-id="99d04-123">Esto no está permitido.</span><span class="sxs-lookup"><span data-stu-id="99d04-123">This is not allowed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="99d04-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="99d04-124">User Action</span></span>  
 <span data-ttu-id="99d04-125">Las asignaciones sólo pueden ser controladas por los usuarios de aplicación de esas asignaciones específicas.</span><span class="sxs-lookup"><span data-stu-id="99d04-125">Mappings can only be controlled by the Application Users for those specific mappings.</span></span>