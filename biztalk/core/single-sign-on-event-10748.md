---
title: 'Inicio de sesión único: Evento 10748 | Documentos de Microsoft'
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
ms.openlocfilehash: 7d83f0bfec0137e0788b55ca6aa5857f3dcfcc50
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276508"
---
# <a name="single-sign-on-event-10748"></a><span data-ttu-id="04401-102">Inicio de sesión único: Evento 10748</span><span class="sxs-lookup"><span data-stu-id="04401-102">Single Sign-On: Event 10748</span></span>
## <a name="details"></a><span data-ttu-id="04401-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="04401-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="04401-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="04401-104">Product Name</span></span>|<span data-ttu-id="04401-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="04401-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="04401-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="04401-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="04401-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="04401-107">Event ID</span></span>|<span data-ttu-id="04401-108">10748</span><span class="sxs-lookup"><span data-stu-id="04401-108">10748</span></span>|  
|<span data-ttu-id="04401-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="04401-109">Event Source</span></span>|<span data-ttu-id="04401-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="04401-110">ENTSSO</span></span>|  
|<span data-ttu-id="04401-111">Componente</span><span class="sxs-lookup"><span data-stu-id="04401-111">Component</span></span>|<span data-ttu-id="04401-112">N\D</span><span class="sxs-lookup"><span data-stu-id="04401-112">N\A</span></span>|  
|<span data-ttu-id="04401-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="04401-113">Symbolic Name</span></span>|<span data-ttu-id="04401-114">SSO_WARN_PS_ADAPTER_NOT_RUNNING</span><span class="sxs-lookup"><span data-stu-id="04401-114">SSO_WARN_PS_ADAPTER_NOT_RUNNING</span></span>|  
|<span data-ttu-id="04401-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="04401-115">Message Text</span></span>|<span data-ttu-id="04401-116">No se pudo establecer la comunicación con el adaptador de destino.</span><span class="sxs-lookup"><span data-stu-id="04401-116">Could not contact the destination adapter.</span></span><br /><br /> <span data-ttu-id="04401-117">Es posible que no esté en ejecución o que no se haya inicializado.%r</span><span class="sxs-lookup"><span data-stu-id="04401-117">It may not be running or initialized.%r</span></span><br /><br /> <span data-ttu-id="04401-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="04401-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="04401-119">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="04401-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="04401-120">Nombre del servidor SSO: %3 %r</span><span class="sxs-lookup"><span data-stu-id="04401-120">SSO Server Name: %3%r</span></span><br /><br /> <span data-ttu-id="04401-121">Código de error: %4</span><span class="sxs-lookup"><span data-stu-id="04401-121">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="04401-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="04401-122">Explanation</span></span>  
 <span data-ttu-id="04401-123">Este evento de advertencia indica que la sincronización de contraseñas no pudo comunicarse con el adaptador de sincronización de contraseñas especificado.</span><span class="sxs-lookup"><span data-stu-id="04401-123">This Warning event indicates that Password Synchronization could not contact the specified password sync adapter.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="04401-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="04401-124">User Action</span></span>  
 <span data-ttu-id="04401-125">Para solucionar la advertencia, realice una o varias de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="04401-125">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="04401-126">Compruebe el adaptador externo.</span><span class="sxs-lookup"><span data-stu-id="04401-126">Check the external adapter.</span></span>  
  
-   <span data-ttu-id="04401-127">Use las herramientas del complemento MMC o de la línea de comandos para habilitar el adaptador.</span><span class="sxs-lookup"><span data-stu-id="04401-127">Use the MMC Snap-In or command line tools to enable the adapter.</span></span>  
  
-   <span data-ttu-id="04401-128">Compruebe si en los registros de eventos del sistema y la aplicación existen errores asociados.</span><span class="sxs-lookup"><span data-stu-id="04401-128">Check the system and application event logs for associated errors.</span></span>  
  
 <span data-ttu-id="04401-129">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="04401-129">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="04401-130">Cómo administrar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="04401-130">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)