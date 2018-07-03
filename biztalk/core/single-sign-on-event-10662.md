---
title: 'De sesión único: Evento 10662 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe707f23-ad54-4adb-a755-8d706a75efa4
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f33d106f7c272f74f99ef537e5083d9bdb015ecb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984709"
---
# <a name="single-sign-on-event-10662"></a><span data-ttu-id="0818d-102">De sesión único: Evento 10662</span><span class="sxs-lookup"><span data-stu-id="0818d-102">Single Sign-On: Event 10662</span></span>
## <a name="details"></a><span data-ttu-id="0818d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="0818d-103">Details</span></span>  

|                 |                                                                                                                                                                                   |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="0818d-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="0818d-104">Product Name</span></span>   |                                                                             <span data-ttu-id="0818d-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="0818d-105">Enterprise Single Sign-On</span></span>                                                                             |
| <span data-ttu-id="0818d-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="0818d-106">Product Version</span></span> |                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                             |
|    <span data-ttu-id="0818d-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="0818d-107">Event ID</span></span>     |                                                                                       <span data-ttu-id="0818d-108">10662</span><span class="sxs-lookup"><span data-stu-id="0818d-108">10662</span></span>                                                                                       |
|  <span data-ttu-id="0818d-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="0818d-109">Event Source</span></span>   |                                                                                      <span data-ttu-id="0818d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0818d-110">ENTSSO</span></span>                                                                                       |
|    <span data-ttu-id="0818d-111">Componente</span><span class="sxs-lookup"><span data-stu-id="0818d-111">Component</span></span>    |                                                                                        <span data-ttu-id="0818d-112">N\D</span><span class="sxs-lookup"><span data-stu-id="0818d-112">N\A</span></span>                                                                                        |
|  <span data-ttu-id="0818d-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="0818d-113">Symbolic Name</span></span>  |                                                                     <span data-ttu-id="0818d-114">SSO_INFO_WINDOWS_PASSWORD_CHANGE_RECEIVED</span><span class="sxs-lookup"><span data-stu-id="0818d-114">SSO_INFO_WINDOWS_PASSWORD_CHANGE_RECEIVED</span></span>                                                                     |
|  <span data-ttu-id="0818d-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="0818d-115">Message Text</span></span>   | <span data-ttu-id="0818d-116">Se recibió un cambio de contraseña de Windows desde PCNS.%r</span><span class="sxs-lookup"><span data-stu-id="0818d-116">A Windows password change was received from PCNS.%r</span></span><br /><br /> <span data-ttu-id="0818d-117">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="0818d-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="0818d-118">Cuenta de Windows: %2 %r</span><span class="sxs-lookup"><span data-stu-id="0818d-118">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="0818d-119">Datos adicionales: %3 %r</span><span class="sxs-lookup"><span data-stu-id="0818d-119">Additional Data: %3%r</span></span><br /><br /> <span data-ttu-id="0818d-120">Usuario cliente: %4</span><span class="sxs-lookup"><span data-stu-id="0818d-120">Client User: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="0818d-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="0818d-121">Explanation</span></span>  
 <span data-ttu-id="0818d-122">Este evento de información indica que se recibió un cambio de contraseña de Windows proveniente del servicio de notificación de cambio de contraseña (PCNS).</span><span class="sxs-lookup"><span data-stu-id="0818d-122">This Information event indicates that a Windows password change was received from Password Change Notification Services.</span></span>  

## <a name="user-action"></a><span data-ttu-id="0818d-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="0818d-123">User Action</span></span>  

-   <span data-ttu-id="0818d-124">No es necesario que el usuario realice ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="0818d-124">No user action is necessary.</span></span>  

## <a name="more-info"></a><span data-ttu-id="0818d-125">Más información</span><span class="sxs-lookup"><span data-stu-id="0818d-125">More info</span></span>

- [<span data-ttu-id="0818d-126">Cómo administrar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="0818d-126">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)  

- <span data-ttu-id="0818d-127">**Propiedades del adaptador de sincronización de contraseñas: opciones** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="0818d-127">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
