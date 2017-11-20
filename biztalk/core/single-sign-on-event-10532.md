---
title: "Inicio de sesión único: Evento 10532 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae2112bc-b53c-4d99-9dc1-a2f55dda4665
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7a9d477ec54a3c959f2afdf4c687c65b88523ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10532"></a><span data-ttu-id="9594c-102">Inicio de sesión único: Evento 10532</span><span class="sxs-lookup"><span data-stu-id="9594c-102">Single Sign-On: Event 10532</span></span>
## <a name="details"></a><span data-ttu-id="9594c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="9594c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9594c-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="9594c-104">Product Name</span></span>|<span data-ttu-id="9594c-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="9594c-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="9594c-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="9594c-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="9594c-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="9594c-107">Event ID</span></span>|<span data-ttu-id="9594c-108">10532</span><span class="sxs-lookup"><span data-stu-id="9594c-108">10532</span></span>|  
|<span data-ttu-id="9594c-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="9594c-109">Event Source</span></span>|<span data-ttu-id="9594c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="9594c-110">ENTSSO</span></span>|  
|<span data-ttu-id="9594c-111">Componente</span><span class="sxs-lookup"><span data-stu-id="9594c-111">Component</span></span>|<span data-ttu-id="9594c-112">CO</span><span class="sxs-lookup"><span data-stu-id="9594c-112">CO</span></span>|  
|<span data-ttu-id="9594c-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="9594c-113">Symbolic Name</span></span>|<span data-ttu-id="9594c-114">SSO_WARN_LOST_SECRET_SERVER</span><span class="sxs-lookup"><span data-stu-id="9594c-114">SSO_WARN_LOST_SECRET_SERVER</span></span>|  
|<span data-ttu-id="9594c-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="9594c-115">Message Text</span></span>|<span data-ttu-id="9594c-116">No se pudieron recuperar los secretos principales.</span><span class="sxs-lookup"><span data-stu-id="9594c-116">Failed to retrieve master secrets.</span></span> <span data-ttu-id="9594c-117">Compruebe si el nombre del servidor secreto principal es correcto y está disponible.%r</span><span class="sxs-lookup"><span data-stu-id="9594c-117">Verify that the master secret server name is correct and that it is available.%r</span></span><br /><br /> <span data-ttu-id="9594c-118">Nombre del servidor secreto: %1 %r</span><span class="sxs-lookup"><span data-stu-id="9594c-118">Secret Server Name: %1%r</span></span><br /><br /> <span data-ttu-id="9594c-119">Código de error: %2</span><span class="sxs-lookup"><span data-stu-id="9594c-119">Error Code: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9594c-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="9594c-120">Explanation</span></span>  
 <span data-ttu-id="9594c-121">Este evento de advertencia indica que la solicitud de obtención del secreto principal generó un error.</span><span class="sxs-lookup"><span data-stu-id="9594c-121">This Warning event indicates that a request to get the master secret has failed.</span></span> <span data-ttu-id="9594c-122">Es posible que esto se deba a que el servicio Inicio de sesión único empresarial no está en ejecución en el servidor.</span><span class="sxs-lookup"><span data-stu-id="9594c-122">This might be because the Enterprise Single Sign-On service is not running on the server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9594c-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="9594c-123">User Action</span></span>  
 <span data-ttu-id="9594c-124">Para solucionar la advertencia, realice una o varias de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="9594c-124">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="9594c-125">Compruebe si el registro de eventos de la aplicación contiene eventos o errores asociados.</span><span class="sxs-lookup"><span data-stu-id="9594c-125">Check the Application event log for associated events or errors.</span></span>  
  
-   <span data-ttu-id="9594c-126">Compruebe si el nombre de servidor secreto principal es correcto.</span><span class="sxs-lookup"><span data-stu-id="9594c-126">Verify the master secret server name is correct.</span></span>  
  
-   <span data-ttu-id="9594c-127">Compruebe si el servidor secreto principal está desconectado y si el servicio Inicio de sesión único empresarial está en ejecución.</span><span class="sxs-lookup"><span data-stu-id="9594c-127">Verify the master secret server is online and that the Enterprise Single Sign-On service is running.</span></span>  
  
 <span data-ttu-id="9594c-128">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="9594c-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="9594c-129">Cómo generar el secreto principal</span><span class="sxs-lookup"><span data-stu-id="9594c-129">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  
  
-   [<span data-ttu-id="9594c-130">Administrar el secreto principal</span><span class="sxs-lookup"><span data-stu-id="9594c-130">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)