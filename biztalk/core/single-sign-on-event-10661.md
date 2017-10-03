---
title: "Inicio de sesión único: Evento 10661 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c3418f37-770d-4021-9341-5dbe99689da6
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6fdc655a87975a89387d84e2aefdd07a603c0ed3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10661"></a><span data-ttu-id="32db2-102">Inicio de sesión único: Evento 10661</span><span class="sxs-lookup"><span data-stu-id="32db2-102">Single Sign-On: Event 10661</span></span>
## <a name="details"></a><span data-ttu-id="32db2-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="32db2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="32db2-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="32db2-104">Product Name</span></span>|<span data-ttu-id="32db2-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="32db2-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="32db2-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="32db2-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="32db2-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="32db2-107">Event ID</span></span>|<span data-ttu-id="32db2-108">10661</span><span class="sxs-lookup"><span data-stu-id="32db2-108">10661</span></span>|  
|<span data-ttu-id="32db2-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="32db2-109">Event Source</span></span>|<span data-ttu-id="32db2-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="32db2-110">ENTSSO</span></span>|  
|<span data-ttu-id="32db2-111">Componente</span><span class="sxs-lookup"><span data-stu-id="32db2-111">Component</span></span>|<span data-ttu-id="32db2-112">N\D</span><span class="sxs-lookup"><span data-stu-id="32db2-112">N\A</span></span>|  
|<span data-ttu-id="32db2-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="32db2-113">Symbolic Name</span></span>|<span data-ttu-id="32db2-114">SSO_ERROR_PASSWORD_SYNC_WINDOWS_START_FAILED</span><span class="sxs-lookup"><span data-stu-id="32db2-114">SSO_ERROR_PASSWORD_SYNC_WINDOWS_START_FAILED</span></span>|  
|<span data-ttu-id="32db2-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="32db2-115">Message Text</span></span>|<span data-ttu-id="32db2-116">No se pudo iniciar la sincronización de contraseñas de Windows (desde PCNS).%r</span><span class="sxs-lookup"><span data-stu-id="32db2-116">Password sync for Windows (from PCNS) failed to start.%r</span></span><br /><br /> <span data-ttu-id="32db2-117">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="32db2-117">Error Code: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="32db2-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="32db2-118">Explanation</span></span>  
 <span data-ttu-id="32db2-119">Este evento de error indica que no se pudo iniciar la sincronización de contraseñas para Windows.</span><span class="sxs-lookup"><span data-stu-id="32db2-119">This Error event indicates that password sync for Windows failed to start.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="32db2-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="32db2-120">User Action</span></span>  
 <span data-ttu-id="32db2-121">Para resolver este error, realice una o varias de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="32db2-121">To resolve this error, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="32db2-122">Compruebe si en los registros de eventos del sistema y la aplicación existen eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="32db2-122">Check the application and system event logs for associated events.</span></span>  
  
-   <span data-ttu-id="32db2-123">Compruebe las propiedades de configuración del adaptador.</span><span class="sxs-lookup"><span data-stu-id="32db2-123">Verify adapter configuration properties.</span></span>  
  
## <a name="more-info"></a><span data-ttu-id="32db2-124">Más información</span><span class="sxs-lookup"><span data-stu-id="32db2-124">More info</span></span>
  
-   [<span data-ttu-id="32db2-125">Cómo administrar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="32db2-125">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)  
  
-   <span data-ttu-id="32db2-126">**Ayuda UI de inicio de sesión único empresarial**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="32db2-126">**Enterprise Single Sign-On UI Help** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>