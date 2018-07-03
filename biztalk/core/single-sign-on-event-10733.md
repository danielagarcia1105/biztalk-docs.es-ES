---
title: 'De sesión único: Evento 10733 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 01520ae4-f692-4697-82ce-53a8a63b5bd9
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd392f2a00d3010039501b99f731f1d9c350cdda
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023490"
---
# <a name="single-sign-on-event-10733"></a><span data-ttu-id="0bc61-102">De sesión único: Evento 10733</span><span class="sxs-lookup"><span data-stu-id="0bc61-102">Single Sign-On: Event 10733</span></span>
## <a name="details"></a><span data-ttu-id="0bc61-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="0bc61-103">Details</span></span>  

|                 |                                                                                                                                                             |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="0bc61-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="0bc61-104">Product Name</span></span>   |                                                                  <span data-ttu-id="0bc61-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="0bc61-105">Enterprise Single Sign-On</span></span>                                                                  |
| <span data-ttu-id="0bc61-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="0bc61-106">Product Version</span></span> |                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                  |
|    <span data-ttu-id="0bc61-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="0bc61-107">Event ID</span></span>     |                                                                            <span data-ttu-id="0bc61-108">10733</span><span class="sxs-lookup"><span data-stu-id="0bc61-108">10733</span></span>                                                                            |
|  <span data-ttu-id="0bc61-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="0bc61-109">Event Source</span></span>   |                                                                           <span data-ttu-id="0bc61-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0bc61-110">ENTSSO</span></span>                                                                            |
|    <span data-ttu-id="0bc61-111">Componente</span><span class="sxs-lookup"><span data-stu-id="0bc61-111">Component</span></span>    |                                                                             <span data-ttu-id="0bc61-112">N\D</span><span class="sxs-lookup"><span data-stu-id="0bc61-112">N\A</span></span>                                                                             |
|  <span data-ttu-id="0bc61-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="0bc61-113">Symbolic Name</span></span>  |                                                              <span data-ttu-id="0bc61-114">SSO_WARN_PS_SET_WINDOWS_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="0bc61-114">SSO_WARN_PS_SET_WINDOWS_PASSWORD</span></span>                                                               |
|  <span data-ttu-id="0bc61-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="0bc61-115">Message Text</span></span>   | <span data-ttu-id="0bc61-116">No se pudo actualizar la contraseña de Windows en la base de datos de SSO.%r</span><span class="sxs-lookup"><span data-stu-id="0bc61-116">Failed to update the Windows password in the SSO database.%r</span></span><br /><br /> <span data-ttu-id="0bc61-117">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="0bc61-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="0bc61-118">Cuenta de Windows: %2\\%3 %r</span><span class="sxs-lookup"><span data-stu-id="0bc61-118">Windows Account: %2\\%3%r</span></span><br /><br /> <span data-ttu-id="0bc61-119">Código de error: %4</span><span class="sxs-lookup"><span data-stu-id="0bc61-119">Error Code: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="0bc61-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="0bc61-120">Explanation</span></span>  
 <span data-ttu-id="0bc61-121">Este evento de advertencia indica que Sincronización de contraseñas no pudo actualizar la contraseña de cuenta de Windows especificada en la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="0bc61-121">This Warning event indicates that Password Sync failed to update the specified Windows account password in the SSO database.</span></span>  

## <a name="user-action"></a><span data-ttu-id="0bc61-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="0bc61-122">User Action</span></span>  
 <span data-ttu-id="0bc61-123">Para solucionar la advertencia, realice una o varias de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="0bc61-123">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="0bc61-124">Compruebe si en los registros de eventos del sistema y la aplicación existen errores asociados.</span><span class="sxs-lookup"><span data-stu-id="0bc61-124">Check the system and application event logs for associated errors.</span></span>  

- <span data-ttu-id="0bc61-125">Compruebe si la contraseña de la cuenta especificada es una contraseña de Windows válida.</span><span class="sxs-lookup"><span data-stu-id="0bc61-125">Verify the password for the specified account is a valid Windows password.</span></span>  

  <span data-ttu-id="0bc61-126">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0bc61-126">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="0bc61-127">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="0bc61-127">Password Synchronization</span></span>](../core/password-synchronization2.md)
