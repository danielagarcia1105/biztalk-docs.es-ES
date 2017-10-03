---
title: "Inicio de sesión único: Evento 10527 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40995ad8-9f74-4e96-863d-427e23025ba1
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf1785361ad343b3da4c7dc07b6a73a362fa14d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10527"></a><span data-ttu-id="196da-102">Inicio de sesión único: Evento 10527</span><span class="sxs-lookup"><span data-stu-id="196da-102">Single Sign-On: Event 10527</span></span>
## <a name="details"></a><span data-ttu-id="196da-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="196da-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="196da-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="196da-104">Product Name</span></span>|<span data-ttu-id="196da-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="196da-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="196da-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="196da-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="196da-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="196da-107">Event ID</span></span>|<span data-ttu-id="196da-108">10527</span><span class="sxs-lookup"><span data-stu-id="196da-108">10527</span></span>|  
|<span data-ttu-id="196da-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="196da-109">Event Source</span></span>|<span data-ttu-id="196da-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="196da-110">ENTSSO</span></span>|  
|<span data-ttu-id="196da-111">Componente</span><span class="sxs-lookup"><span data-stu-id="196da-111">Component</span></span>|<span data-ttu-id="196da-112">0</span><span class="sxs-lookup"><span data-stu-id="196da-112">0</span></span>|  
|<span data-ttu-id="196da-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="196da-113">Symbolic Name</span></span>|<span data-ttu-id="196da-114">SSO_ERROR_GET_SECRET_FAILED</span><span class="sxs-lookup"><span data-stu-id="196da-114">SSO_ERROR_GET_SECRET_FAILED</span></span>|  
|<span data-ttu-id="196da-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="196da-115">Message Text</span></span>|<span data-ttu-id="196da-116">Error de solicitud de obtención de secreto principal.%r</span><span class="sxs-lookup"><span data-stu-id="196da-116">A request to get a master secret failed.%r</span></span><br /><br /> <span data-ttu-id="196da-117">Número secreto: %1 %r</span><span class="sxs-lookup"><span data-stu-id="196da-117">Secret Number: %1%r</span></span><br /><br /> <span data-ttu-id="196da-118">El usuario cliente: %2 %r</span><span class="sxs-lookup"><span data-stu-id="196da-118">Client User: %2%r</span></span><br /><br /> <span data-ttu-id="196da-119">Equipo cliente: %3 %r</span><span class="sxs-lookup"><span data-stu-id="196da-119">Client Computer: %3%r</span></span><br /><br /> <span data-ttu-id="196da-120">Id. de seguimiento: %4 %r</span><span class="sxs-lookup"><span data-stu-id="196da-120">Tracking ID: %4%r</span></span><br /><br /> <span data-ttu-id="196da-121">Código de error: %5</span><span class="sxs-lookup"><span data-stu-id="196da-121">Error Code: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="196da-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="196da-122">Explanation</span></span>  
 <span data-ttu-id="196da-123">Este evento de error indica que la solicitud de obtención del secreto principal generó un error.</span><span class="sxs-lookup"><span data-stu-id="196da-123">This Error event indicates that a request to get the master secret has failed.</span></span> <span data-ttu-id="196da-124">En estos casos, debería haber mensajes relacionados en el registro de eventos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="196da-124">In these cases there should be related messages in the Application event log.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="196da-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="196da-125">User Action</span></span>  
 <span data-ttu-id="196da-126">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="196da-126">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="196da-127">Compruebe si el registro de eventos de la aplicación contiene eventos o errores asociados.</span><span class="sxs-lookup"><span data-stu-id="196da-127">Check the Application event log for associated events or errors.</span></span>  
  
 <span data-ttu-id="196da-128">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="196da-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="196da-129">Cómo generar el secreto principal</span><span class="sxs-lookup"><span data-stu-id="196da-129">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  
  
-   [<span data-ttu-id="196da-130">Administrar el secreto principal</span><span class="sxs-lookup"><span data-stu-id="196da-130">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)