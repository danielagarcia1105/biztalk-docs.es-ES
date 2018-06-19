---
title: 'Inicio de sesión único: Evento 10652 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae7fe452-bcec-4722-8ec6-78d4fe462a0a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62066b2fbbc47d07fa57f047313ed5ed8cda47d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270916"
---
# <a name="single-sign-on-event-10652"></a><span data-ttu-id="92fa0-102">Inicio de sesión único: Evento 10652</span><span class="sxs-lookup"><span data-stu-id="92fa0-102">Single Sign-On: Event 10652</span></span>
## <a name="details"></a><span data-ttu-id="92fa0-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="92fa0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="92fa0-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="92fa0-104">Product Name</span></span>|<span data-ttu-id="92fa0-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="92fa0-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="92fa0-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="92fa0-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="92fa0-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="92fa0-107">Event ID</span></span>|<span data-ttu-id="92fa0-108">10652</span><span class="sxs-lookup"><span data-stu-id="92fa0-108">10652</span></span>|  
|<span data-ttu-id="92fa0-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="92fa0-109">Event Source</span></span>|<span data-ttu-id="92fa0-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="92fa0-110">ENTSSO</span></span>|  
|<span data-ttu-id="92fa0-111">Componente</span><span class="sxs-lookup"><span data-stu-id="92fa0-111">Component</span></span>|<span data-ttu-id="92fa0-112">N\D</span><span class="sxs-lookup"><span data-stu-id="92fa0-112">N\A</span></span>|  
|<span data-ttu-id="92fa0-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="92fa0-113">Symbolic Name</span></span>|<span data-ttu-id="92fa0-114">SSO_ERROR_PASSWORD_SYNC_START_FAILED</span><span class="sxs-lookup"><span data-stu-id="92fa0-114">SSO_ERROR_PASSWORD_SYNC_START_FAILED</span></span>|  
|<span data-ttu-id="92fa0-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="92fa0-115">Message Text</span></span>|<span data-ttu-id="92fa0-116">No se pudieron inicializar los servicios de sincronización de contraseñas.%r</span><span class="sxs-lookup"><span data-stu-id="92fa0-116">Password sync services failed to initialize.%r</span></span><br /><br /> <span data-ttu-id="92fa0-117">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="92fa0-117">Error Code: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="92fa0-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="92fa0-118">Explanation</span></span>  
 <span data-ttu-id="92fa0-119">Este evento de error indica que el servicio de sincronización de contraseñas no pudo iniciarse debido a una excepción.</span><span class="sxs-lookup"><span data-stu-id="92fa0-119">This Error event indicates that the Password Sync Service could not start due to an exception.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="92fa0-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="92fa0-120">User Action</span></span>  
 <span data-ttu-id="92fa0-121">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="92fa0-121">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="92fa0-122">Compruebe si en los registros de eventos del sistema y la aplicación existen errores relacionados de ENTSSO u otros servicios.</span><span class="sxs-lookup"><span data-stu-id="92fa0-122">Check both the Application and System event logs for related errors from ENTSSO or other services.</span></span>  
  
 <span data-ttu-id="92fa0-123">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="92fa0-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="92fa0-124">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="92fa0-124">Password Synchronization</span></span>](../core/password-synchronization2.md)