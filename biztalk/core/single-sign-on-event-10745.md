---
title: 'De sesión único: Evento 10745 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed630e40-d876-4e90-937e-4d2d54fe9f1a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bb3afa69e4a959b189347ac20b71acfc58208f4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984757"
---
# <a name="single-sign-on-event-10745"></a><span data-ttu-id="d98d5-102">De sesión único: Evento 10745</span><span class="sxs-lookup"><span data-stu-id="d98d5-102">Single Sign-On: Event 10745</span></span>
## <a name="details"></a><span data-ttu-id="d98d5-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="d98d5-103">Details</span></span>  

|                 |                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d98d5-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="d98d5-104">Product Name</span></span>   |                                                          <span data-ttu-id="d98d5-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="d98d5-105">Enterprise Single Sign-On</span></span>                                                           |
| <span data-ttu-id="d98d5-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="d98d5-106">Product Version</span></span> |                                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                          |
|    <span data-ttu-id="d98d5-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="d98d5-107">Event ID</span></span>     |                                                                    <span data-ttu-id="d98d5-108">10745</span><span class="sxs-lookup"><span data-stu-id="d98d5-108">10745</span></span>                                                                     |
|  <span data-ttu-id="d98d5-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="d98d5-109">Event Source</span></span>   |                                                                    <span data-ttu-id="d98d5-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d98d5-110">ENTSSO</span></span>                                                                    |
|    <span data-ttu-id="d98d5-111">Componente</span><span class="sxs-lookup"><span data-stu-id="d98d5-111">Component</span></span>    |                                                                     <span data-ttu-id="d98d5-112">N\D</span><span class="sxs-lookup"><span data-stu-id="d98d5-112">N\A</span></span>                                                                      |
|  <span data-ttu-id="d98d5-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d98d5-113">Symbolic Name</span></span>  |                                                          <span data-ttu-id="d98d5-114">SSO_ERROR_ADAPTER_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="d98d5-114">SSO_ERROR_ADAPTER_OFFLINE</span></span>                                                           |
|  <span data-ttu-id="d98d5-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d98d5-115">Message Text</span></span>   | <span data-ttu-id="d98d5-116">Adaptador desconectado.%r</span><span class="sxs-lookup"><span data-stu-id="d98d5-116">The adapter is offline.%r</span></span><br /><br /> <span data-ttu-id="d98d5-117">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="d98d5-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="d98d5-118">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="d98d5-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="d98d5-119">Mensaje de error: %3 %r</span><span class="sxs-lookup"><span data-stu-id="d98d5-119">Error Message: %3%r</span></span><br /><br /> <span data-ttu-id="d98d5-120">Código de error: %4</span><span class="sxs-lookup"><span data-stu-id="d98d5-120">Error Code: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="d98d5-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="d98d5-121">Explanation</span></span>  
 <span data-ttu-id="d98d5-122">Este evento de error indica que el adaptador especificado está desconectado.</span><span class="sxs-lookup"><span data-stu-id="d98d5-122">This Error event indicates that the specified adapter is offline.</span></span>  

## <a name="user-action"></a><span data-ttu-id="d98d5-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d98d5-123">User Action</span></span>  
 <span data-ttu-id="d98d5-124">Para resolver este error, realice una o varias de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="d98d5-124">To resolve this error, do one or more of the following:</span></span>  

- <span data-ttu-id="d98d5-125">Compruebe si en los registros de eventos del sistema y la aplicación existen errores asociados.</span><span class="sxs-lookup"><span data-stu-id="d98d5-125">Check the system and application event logs for associated errors.</span></span>  

- <span data-ttu-id="d98d5-126">Compruebe si el adaptador externo presenta errores.</span><span class="sxs-lookup"><span data-stu-id="d98d5-126">Check the external adapter for errors.</span></span>  

  <span data-ttu-id="d98d5-127">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d98d5-127">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="d98d5-128">Cómo administrar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="d98d5-128">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)
