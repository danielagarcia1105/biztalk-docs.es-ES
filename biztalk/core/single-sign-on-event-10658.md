---
title: "Inicio de sesión único: Evento 10658 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c5bee12d-502b-4fee-bc84-25807eb0e48e
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9594f2462422190c243d98c165ead37898e33f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10658"></a><span data-ttu-id="1ec50-102">Inicio de sesión único: Evento 10658</span><span class="sxs-lookup"><span data-stu-id="1ec50-102">Single Sign-On: Event 10658</span></span>
## <a name="details"></a><span data-ttu-id="1ec50-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="1ec50-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1ec50-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="1ec50-104">Product Name</span></span>|<span data-ttu-id="1ec50-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="1ec50-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="1ec50-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="1ec50-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="1ec50-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="1ec50-107">Event ID</span></span>|<span data-ttu-id="1ec50-108">10658</span><span class="sxs-lookup"><span data-stu-id="1ec50-108">10658</span></span>|  
|<span data-ttu-id="1ec50-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="1ec50-109">Event Source</span></span>|<span data-ttu-id="1ec50-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1ec50-110">ENTSSO</span></span>|  
|<span data-ttu-id="1ec50-111">Componente</span><span class="sxs-lookup"><span data-stu-id="1ec50-111">Component</span></span>|<span data-ttu-id="1ec50-112">N\D</span><span class="sxs-lookup"><span data-stu-id="1ec50-112">N\A</span></span>|  
|<span data-ttu-id="1ec50-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="1ec50-113">Symbolic Name</span></span>|<span data-ttu-id="1ec50-114">SSO_ERROR_PASSWORD_SYNC_ADAPTERS_START_FAILED</span><span class="sxs-lookup"><span data-stu-id="1ec50-114">SSO_ERROR_PASSWORD_SYNC_ADAPTERS_START_FAILED</span></span>|  
|<span data-ttu-id="1ec50-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="1ec50-115">Message Text</span></span>|<span data-ttu-id="1ec50-116">No se pudo iniciar la sincronización para contraseñas de adaptadores externos.%r</span><span class="sxs-lookup"><span data-stu-id="1ec50-116">Password sync for external adapters failed to start.%r</span></span><br /><br /> <span data-ttu-id="1ec50-117">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="1ec50-117">Error Code: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1ec50-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="1ec50-118">Explanation</span></span>  
 <span data-ttu-id="1ec50-119">Este evento de error indica que no se pudo iniciar la sincronización de contraseñas para adaptadores externos.</span><span class="sxs-lookup"><span data-stu-id="1ec50-119">This Error event indicates that password sync for external adapters failed to start.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1ec50-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="1ec50-120">User Action</span></span>  
 <span data-ttu-id="1ec50-121">Para resolver este error, realice una o varias de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="1ec50-121">To resolve this error, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="1ec50-122">Compruebe si en los registros de eventos del sistema y la aplicación existen eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="1ec50-122">Check the application and system event logs for associated events.</span></span>  
  
-   <span data-ttu-id="1ec50-123">Compruebe las propiedades de configuración del adaptador.</span><span class="sxs-lookup"><span data-stu-id="1ec50-123">Verify adapter configuration properties.</span></span>  

## <a name="more-info"></a><span data-ttu-id="1ec50-124">Más información</span><span class="sxs-lookup"><span data-stu-id="1ec50-124">More info</span></span>  
  
-   [<span data-ttu-id="1ec50-125">Cómo administrar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="1ec50-125">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)  
  
-   <span data-ttu-id="1ec50-126">**Ayuda UI de inicio de sesión único empresarial**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="1ec50-126">**Enterprise Single Sign-On UI Help** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>