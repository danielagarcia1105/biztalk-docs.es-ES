---
title: 'De sesión único: Evento 10746 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8189120b-923a-4c88-937e-f06565bcac56
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3f4fa77909ba53e16d3dffd31073ff93e233ed5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998869"
---
# <a name="single-sign-on-event-10746"></a><span data-ttu-id="83970-102">De sesión único: Evento 10746</span><span class="sxs-lookup"><span data-stu-id="83970-102">Single Sign-On: Event 10746</span></span>
## <a name="details"></a><span data-ttu-id="83970-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="83970-103">Details</span></span>  

|                 |                                                                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="83970-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="83970-104">Product Name</span></span>   |                                                           <span data-ttu-id="83970-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="83970-105">Enterprise Single Sign-On</span></span>                                                           |
| <span data-ttu-id="83970-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="83970-106">Product Version</span></span> |                                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                           |
|    <span data-ttu-id="83970-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="83970-107">Event ID</span></span>     |                                                                     <span data-ttu-id="83970-108">10746</span><span class="sxs-lookup"><span data-stu-id="83970-108">10746</span></span>                                                                     |
|  <span data-ttu-id="83970-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="83970-109">Event Source</span></span>   |                                                                    <span data-ttu-id="83970-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="83970-110">ENTSSO</span></span>                                                                     |
|    <span data-ttu-id="83970-111">Componente</span><span class="sxs-lookup"><span data-stu-id="83970-111">Component</span></span>    |                                                                      <span data-ttu-id="83970-112">N\D</span><span class="sxs-lookup"><span data-stu-id="83970-112">N\A</span></span>                                                                      |
|  <span data-ttu-id="83970-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="83970-113">Symbolic Name</span></span>  |                                                           <span data-ttu-id="83970-114">SSO_WARN_PASSWORD_EXPIRED</span><span class="sxs-lookup"><span data-stu-id="83970-114">SSO_WARN_PASSWORD_EXPIRED</span></span>                                                           |
|  <span data-ttu-id="83970-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="83970-115">Message Text</span></span>   | <span data-ttu-id="83970-116">La contraseña de la cuenta externa caducó.%r</span><span class="sxs-lookup"><span data-stu-id="83970-116">The password for the external account has expired.%r</span></span><br /><br /> <span data-ttu-id="83970-117">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="83970-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="83970-118">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="83970-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="83970-119">Cuenta externa: %3</span><span class="sxs-lookup"><span data-stu-id="83970-119">External Account: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="83970-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="83970-120">Explanation</span></span>  
 <span data-ttu-id="83970-121">Este evento de advertencia indica que caducó la contraseña de la cuenta externa.</span><span class="sxs-lookup"><span data-stu-id="83970-121">This Warning event indicates that the password for the external account has expired.</span></span>  

## <a name="user-action"></a><span data-ttu-id="83970-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="83970-122">User Action</span></span>  
 <span data-ttu-id="83970-123">Para resolver esta advertencia, compruebe los registros de eventos de aplicación y del sistema para los errores asociados.</span><span class="sxs-lookup"><span data-stu-id="83970-123">To resolve this warning, check the system and application event logs for associated errors.</span></span>    

## <a name="more-info"></a><span data-ttu-id="83970-124">Más información</span><span class="sxs-lookup"><span data-stu-id="83970-124">More info</span></span>
<span data-ttu-id="83970-125">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="83970-125">For more information, see the following resources:</span></span>  

- <span data-ttu-id="83970-126">**Propiedades del adaptador de sincronización de contraseñas: opciones** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="83970-126">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>  

- [<span data-ttu-id="83970-127">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="83970-127">Password Synchronization</span></span>](../core/password-synchronization2.md)
