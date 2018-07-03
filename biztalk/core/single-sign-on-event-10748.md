---
title: 'De sesión único: Evento 10748 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b4b18ea-6565-4c0b-89f8-30a8c67601ba
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f36c031e7ee84179c82a70cc8bbaaeca95df773
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013893"
---
# <a name="single-sign-on-event-10748"></a><span data-ttu-id="c25c4-102">De sesión único: Evento 10748</span><span class="sxs-lookup"><span data-stu-id="c25c4-102">Single Sign-On: Event 10748</span></span>
## <a name="details"></a><span data-ttu-id="c25c4-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="c25c4-103">Details</span></span>  

|                 |                                                                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="c25c4-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="c25c4-104">Product Name</span></span>   |                                                                                              <span data-ttu-id="c25c4-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="c25c4-105">Enterprise Single Sign-On</span></span>                                                                                              |
| <span data-ttu-id="c25c4-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="c25c4-106">Product Version</span></span> |                                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                              |
|    <span data-ttu-id="c25c4-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="c25c4-107">Event ID</span></span>     |                                                                                                        <span data-ttu-id="c25c4-108">10748</span><span class="sxs-lookup"><span data-stu-id="c25c4-108">10748</span></span>                                                                                                        |
|  <span data-ttu-id="c25c4-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="c25c4-109">Event Source</span></span>   |                                                                                                       <span data-ttu-id="c25c4-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c25c4-110">ENTSSO</span></span>                                                                                                        |
|    <span data-ttu-id="c25c4-111">Componente</span><span class="sxs-lookup"><span data-stu-id="c25c4-111">Component</span></span>    |                                                                                                         <span data-ttu-id="c25c4-112">N\D</span><span class="sxs-lookup"><span data-stu-id="c25c4-112">N\A</span></span>                                                                                                         |
|  <span data-ttu-id="c25c4-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="c25c4-113">Symbolic Name</span></span>  |                                                                                           <span data-ttu-id="c25c4-114">SSO_WARN_PS_ADAPTER_NOT_RUNNING</span><span class="sxs-lookup"><span data-stu-id="c25c4-114">SSO_WARN_PS_ADAPTER_NOT_RUNNING</span></span>                                                                                           |
|  <span data-ttu-id="c25c4-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="c25c4-115">Message Text</span></span>   | <span data-ttu-id="c25c4-116">No se pudo establecer la comunicación con el adaptador de destino.</span><span class="sxs-lookup"><span data-stu-id="c25c4-116">Could not contact the destination adapter.</span></span><br /><br /> <span data-ttu-id="c25c4-117">Es posible que no esté en ejecución o que no se haya inicializado.%r</span><span class="sxs-lookup"><span data-stu-id="c25c4-117">It may not be running or initialized.%r</span></span><br /><br /> <span data-ttu-id="c25c4-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="c25c4-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="c25c4-119">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="c25c4-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="c25c4-120">Nombre del servidor SSO: %3 %r</span><span class="sxs-lookup"><span data-stu-id="c25c4-120">SSO Server Name: %3%r</span></span><br /><br /> <span data-ttu-id="c25c4-121">Código de error: %4</span><span class="sxs-lookup"><span data-stu-id="c25c4-121">Error Code: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="c25c4-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="c25c4-122">Explanation</span></span>  
 <span data-ttu-id="c25c4-123">Este evento de advertencia indica que la sincronización de contraseñas no pudo comunicarse con el adaptador de sincronización de contraseñas especificado.</span><span class="sxs-lookup"><span data-stu-id="c25c4-123">This Warning event indicates that Password Synchronization could not contact the specified password sync adapter.</span></span>  

## <a name="user-action"></a><span data-ttu-id="c25c4-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="c25c4-124">User Action</span></span>  
 <span data-ttu-id="c25c4-125">Para solucionar la advertencia, realice una o varias de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="c25c4-125">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="c25c4-126">Compruebe el adaptador externo.</span><span class="sxs-lookup"><span data-stu-id="c25c4-126">Check the external adapter.</span></span>  

- <span data-ttu-id="c25c4-127">Use las herramientas del complemento MMC o de la línea de comandos para habilitar el adaptador.</span><span class="sxs-lookup"><span data-stu-id="c25c4-127">Use the MMC Snap-In or command line tools to enable the adapter.</span></span>  

- <span data-ttu-id="c25c4-128">Compruebe si en los registros de eventos del sistema y la aplicación existen errores asociados.</span><span class="sxs-lookup"><span data-stu-id="c25c4-128">Check the system and application event logs for associated errors.</span></span>  

  <span data-ttu-id="c25c4-129">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c25c4-129">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="c25c4-130">Cómo administrar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="c25c4-130">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)
