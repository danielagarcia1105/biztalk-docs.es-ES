---
title: 'De sesión único: Evento 10652 | Microsoft Docs'
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
ms.openlocfilehash: a2e27c678f2c031c642107cd770566f92d7ca708
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985749"
---
# <a name="single-sign-on-event-10652"></a><span data-ttu-id="0afc6-102">De sesión único: Evento 10652</span><span class="sxs-lookup"><span data-stu-id="0afc6-102">Single Sign-On: Event 10652</span></span>
## <a name="details"></a><span data-ttu-id="0afc6-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="0afc6-103">Details</span></span>  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  <span data-ttu-id="0afc6-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="0afc6-104">Product Name</span></span>   |                         <span data-ttu-id="0afc6-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="0afc6-105">Enterprise Single Sign-On</span></span>                         |
| <span data-ttu-id="0afc6-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="0afc6-106">Product Version</span></span> |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    <span data-ttu-id="0afc6-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="0afc6-107">Event ID</span></span>     |                                   <span data-ttu-id="0afc6-108">10652</span><span class="sxs-lookup"><span data-stu-id="0afc6-108">10652</span></span>                                   |
|  <span data-ttu-id="0afc6-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="0afc6-109">Event Source</span></span>   |                                  <span data-ttu-id="0afc6-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0afc6-110">ENTSSO</span></span>                                   |
|    <span data-ttu-id="0afc6-111">Componente</span><span class="sxs-lookup"><span data-stu-id="0afc6-111">Component</span></span>    |                                    <span data-ttu-id="0afc6-112">N\D</span><span class="sxs-lookup"><span data-stu-id="0afc6-112">N\A</span></span>                                    |
|  <span data-ttu-id="0afc6-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="0afc6-113">Symbolic Name</span></span>  |                   <span data-ttu-id="0afc6-114">SSO_ERROR_PASSWORD_SYNC_START_FAILED</span><span class="sxs-lookup"><span data-stu-id="0afc6-114">SSO_ERROR_PASSWORD_SYNC_START_FAILED</span></span>                    |
|  <span data-ttu-id="0afc6-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="0afc6-115">Message Text</span></span>   | <span data-ttu-id="0afc6-116">No se pudieron inicializar los servicios de sincronización de contraseñas.%r</span><span class="sxs-lookup"><span data-stu-id="0afc6-116">Password sync services failed to initialize.%r</span></span><br /><br /> <span data-ttu-id="0afc6-117">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="0afc6-117">Error Code: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="0afc6-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="0afc6-118">Explanation</span></span>  
 <span data-ttu-id="0afc6-119">Este evento de error indica que el servicio de sincronización de contraseñas no pudo iniciarse debido a una excepción.</span><span class="sxs-lookup"><span data-stu-id="0afc6-119">This Error event indicates that the Password Sync Service could not start due to an exception.</span></span>  

## <a name="user-action"></a><span data-ttu-id="0afc6-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="0afc6-120">User Action</span></span>  
 <span data-ttu-id="0afc6-121">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0afc6-121">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="0afc6-122">Compruebe si en los registros de eventos del sistema y la aplicación existen errores relacionados de ENTSSO u otros servicios.</span><span class="sxs-lookup"><span data-stu-id="0afc6-122">Check both the Application and System event logs for related errors from ENTSSO or other services.</span></span>  

  <span data-ttu-id="0afc6-123">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="0afc6-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="0afc6-124">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="0afc6-124">Password Synchronization</span></span>](../core/password-synchronization2.md)
