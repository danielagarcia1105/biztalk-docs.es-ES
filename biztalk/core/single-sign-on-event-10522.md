---
title: "Inicio de sesión único: Evento 10522 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd634a57-01dc-44bd-bcf9-668689db7b77
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b56999d7898af01d0009a7722d78aed0dbf5dbf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10522"></a><span data-ttu-id="08c49-102">Inicio de sesión único: Evento 10522</span><span class="sxs-lookup"><span data-stu-id="08c49-102">Single Sign-On: Event 10522</span></span>
## <a name="details"></a><span data-ttu-id="08c49-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="08c49-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="08c49-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="08c49-104">Product Name</span></span>|<span data-ttu-id="08c49-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="08c49-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="08c49-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="08c49-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="08c49-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="08c49-107">Event ID</span></span>|<span data-ttu-id="08c49-108">10522</span><span class="sxs-lookup"><span data-stu-id="08c49-108">10522</span></span>|  
|<span data-ttu-id="08c49-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="08c49-109">Event Source</span></span>|<span data-ttu-id="08c49-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="08c49-110">ENTSSO</span></span>|  
|<span data-ttu-id="08c49-111">Componente</span><span class="sxs-lookup"><span data-stu-id="08c49-111">Component</span></span>|<span data-ttu-id="08c49-112">N\D</span><span class="sxs-lookup"><span data-stu-id="08c49-112">N\A</span></span>|  
|<span data-ttu-id="08c49-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="08c49-113">Symbolic Name</span></span>|<span data-ttu-id="08c49-114">SSO_ERROR_REENCRYPT</span><span class="sxs-lookup"><span data-stu-id="08c49-114">SSO_ERROR_REENCRYPT</span></span>|  
|<span data-ttu-id="08c49-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="08c49-115">Message Text</span></span>|<span data-ttu-id="08c49-116">Error al volver a cifrar la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="08c49-116">SSO database re-encryption failed.</span></span> <span data-ttu-id="08c49-117">Vuelva a intentarlo en %1 minutos.%r</span><span class="sxs-lookup"><span data-stu-id="08c49-117">Will try again in %1 minutes.%r</span></span><br /><br /> <span data-ttu-id="08c49-118">Código de error: %2</span><span class="sxs-lookup"><span data-stu-id="08c49-118">Error Code: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="08c49-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="08c49-119">Explanation</span></span>  
 <span data-ttu-id="08c49-120">Este evento de error indica que se produjo un error al volver a cifrar la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="08c49-120">This Error event indicates that the SSO database re-encryption failed.</span></span> <span data-ttu-id="08c49-121">Cuando el servicio SSO se inicia en el servidor secreto principal, lo primero que hace es comprobar si la base de datos de SSO aún contiene información cifrada con el secreto principal anterior.</span><span class="sxs-lookup"><span data-stu-id="08c49-121">When the SSO service starts on the master secret server, the first thing it does is to check if there is anything in the SSO database still encrypted with the previous master secret.</span></span> <span data-ttu-id="08c49-122">Si es así, descifra esa información (mediante el secreto anterior) y vuelva a cifrarla mediante el secreto principal actual.</span><span class="sxs-lookup"><span data-stu-id="08c49-122">If it finds anything, it decrypts that information (using the previous secret) and re-encrypts it using the current master secret.</span></span> <span data-ttu-id="08c49-123">Si, por cualquier motivo, el proceso genera un error, se emite este mensaje de evento.</span><span class="sxs-lookup"><span data-stu-id="08c49-123">If for any reason this process fails, then this event message is issued.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="08c49-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="08c49-124">User Action</span></span>  
 <span data-ttu-id="08c49-125">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="08c49-125">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="08c49-126">Compruebe el código de error para determinar la causa del error.</span><span class="sxs-lookup"><span data-stu-id="08c49-126">Check the error code to determine what the underlying cause of the error might be.</span></span> <span data-ttu-id="08c49-127">Podría ser un problema de red o base de datos.</span><span class="sxs-lookup"><span data-stu-id="08c49-127">This could be a network or database issue.</span></span> <span data-ttu-id="08c49-128">Si se trata de un problema intermitente, no es necesario realizar ninguna acción porque se volverá a intentar el recifrado tras un breve retardo.</span><span class="sxs-lookup"><span data-stu-id="08c49-128">If it is intermittent, then no action is required because re-encryption will be attempted again after a short delay.</span></span> <span data-ttu-id="08c49-129">De lo contrario, detenga el servicio SSO e intente solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="08c49-129">If the issue is not intermittent, stop the SSO service and attempt to resolve the issue.</span></span> <span data-ttu-id="08c49-130">Una vez resuelto el problema, reinicie el servicio SSO, ya que el reinicio realizará el recifrado de forma automática.</span><span class="sxs-lookup"><span data-stu-id="08c49-130">Once the issue is resolved then restart the SSO service, Restarting the SSO service will automatically perform the re-encryption.</span></span>  
  
 <span data-ttu-id="08c49-131">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="08c49-131">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="08c49-132">Cómo mostrar la información de la base de datos SSO</span><span class="sxs-lookup"><span data-stu-id="08c49-132">How to Display the SSO Database Information</span></span>](../core/how-to-display-the-sso-database-information.md)  
  
-   [<span data-ttu-id="08c49-133">Servidor secreto principal</span><span class="sxs-lookup"><span data-stu-id="08c49-133">Master Secret Server</span></span>](../core/master-secret-server.md)