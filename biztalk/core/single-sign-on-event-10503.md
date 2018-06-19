---
title: 'Inicio de sesión único: Evento 10503 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04292ae8-8daf-4f5a-837e-fe5dfcd02b10
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53c02388304fa9fab0b518517ba51b2db94412f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271116"
---
# <a name="single-sign-on-event-10503"></a><span data-ttu-id="10bb7-102">Inicio de sesión único: Evento 10503</span><span class="sxs-lookup"><span data-stu-id="10bb7-102">Single Sign-On: Event 10503</span></span>
## <a name="details"></a><span data-ttu-id="10bb7-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="10bb7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="10bb7-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="10bb7-104">Product Name</span></span>|<span data-ttu-id="10bb7-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="10bb7-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="10bb7-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="10bb7-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="10bb7-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="10bb7-107">Event ID</span></span>|<span data-ttu-id="10bb7-108">10503</span><span class="sxs-lookup"><span data-stu-id="10bb7-108">10503</span></span>|  
|<span data-ttu-id="10bb7-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="10bb7-109">Event Source</span></span>|<span data-ttu-id="10bb7-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="10bb7-110">ENTSSO</span></span>|  
|<span data-ttu-id="10bb7-111">Componente</span><span class="sxs-lookup"><span data-stu-id="10bb7-111">Component</span></span>|<span data-ttu-id="10bb7-112">N\D</span><span class="sxs-lookup"><span data-stu-id="10bb7-112">N\A</span></span>|  
|<span data-ttu-id="10bb7-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="10bb7-113">Symbolic Name</span></span>|<span data-ttu-id="10bb7-114">SSO_ERROR_SERVICE_START_FAILED</span><span class="sxs-lookup"><span data-stu-id="10bb7-114">SSO_ERROR_SERVICE_START_FAILED</span></span>|  
|<span data-ttu-id="10bb7-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="10bb7-115">Message Text</span></span>|<span data-ttu-id="10bb7-116">Error al iniciar el servicio SSO.%r</span><span class="sxs-lookup"><span data-stu-id="10bb7-116">The SSO service failed to start.%r</span></span><br /><br /> <span data-ttu-id="10bb7-117">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="10bb7-117">Error Code: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="10bb7-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="10bb7-118">Explanation</span></span>  
 <span data-ttu-id="10bb7-119">Este evento de error indica que el servicio ENTSSO no pudo iniciarse debido a una excepción.</span><span class="sxs-lookup"><span data-stu-id="10bb7-119">This Error event indicates that the ENTSSO Service could not start due to an exception.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="10bb7-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="10bb7-120">User Action</span></span>  
 <span data-ttu-id="10bb7-121">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="10bb7-121">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="10bb7-122">Compruebe si en los registros de eventos del sistema y la aplicación existen errores relacionados de ENTSSO u otros servicios.</span><span class="sxs-lookup"><span data-stu-id="10bb7-122">Check both the Application and System event logs for related errors from ENTSSO or other services.</span></span>  
  
 <span data-ttu-id="10bb7-123">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="10bb7-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="10bb7-124">Uso de SSO</span><span class="sxs-lookup"><span data-stu-id="10bb7-124">Using SSO</span></span>](../core/using-sso.md)