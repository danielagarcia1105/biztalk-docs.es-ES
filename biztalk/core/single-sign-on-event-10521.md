---
title: 'De sesión único: Evento 10521 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00d427ff-74d0-45f5-bb55-ab12b564d767
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8af1b2ac8d2ac3645db6a6a80146832378aececf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008573"
---
# <a name="single-sign-on-event-10521"></a><span data-ttu-id="0c019-102">De sesión único: Evento 10521</span><span class="sxs-lookup"><span data-stu-id="0c019-102">Single Sign-On: Event 10521</span></span>
## <a name="details"></a><span data-ttu-id="0c019-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="0c019-103">Details</span></span>  

|                 |                                                                       |
|-----------------|-----------------------------------------------------------------------|
|  <span data-ttu-id="0c019-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="0c019-104">Product Name</span></span>   |                       <span data-ttu-id="0c019-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="0c019-105">Enterprise Single Sign-On</span></span>                       |
| <span data-ttu-id="0c019-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="0c019-106">Product Version</span></span> |      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]       |
|    <span data-ttu-id="0c019-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="0c019-107">Event ID</span></span>     |                                 <span data-ttu-id="0c019-108">10521</span><span class="sxs-lookup"><span data-stu-id="0c019-108">10521</span></span>                                 |
|  <span data-ttu-id="0c019-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="0c019-109">Event Source</span></span>   |                                <span data-ttu-id="0c019-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0c019-110">ENTSSO</span></span>                                 |
|    <span data-ttu-id="0c019-111">Componente</span><span class="sxs-lookup"><span data-stu-id="0c019-111">Component</span></span>    |                                  <span data-ttu-id="0c019-112">N\D</span><span class="sxs-lookup"><span data-stu-id="0c019-112">N\A</span></span>                                  |
|  <span data-ttu-id="0c019-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="0c019-113">Symbolic Name</span></span>  |                     <span data-ttu-id="0c019-114">SSO_ERROR_SECRETS_NOT_LOADED</span><span class="sxs-lookup"><span data-stu-id="0c019-114">SSO_ERROR_SECRETS_NOT_LOADED</span></span>                      |
|  <span data-ttu-id="0c019-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="0c019-115">Message Text</span></span>   | <span data-ttu-id="0c019-116">No se pudieron cargar secretos desde el Registro del servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="0c019-116">Could not load secrets from the registry of the master secret server.</span></span> |

## <a name="explanation"></a><span data-ttu-id="0c019-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="0c019-117">Explanation</span></span>  
 <span data-ttu-id="0c019-118">Este evento de error se produce en el servidor secreto principal cuando no se pueden obtener los secretos principales del Registro.</span><span class="sxs-lookup"><span data-stu-id="0c019-118">This Error event occurs on the master secret server when the master secrets cannot be obtained from the registry.</span></span> <span data-ttu-id="0c019-119">Es posible que haya mensajes de error relacionados en el registro de eventos con información adicional.</span><span class="sxs-lookup"><span data-stu-id="0c019-119">There may be related errors messages in the event log with further information.</span></span> <span data-ttu-id="0c019-120">La causa más probable es que se haya producido un error de permisos o de cifrado cuando la cuenta de servicio SSO intentó obtener acceso al Registro.</span><span class="sxs-lookup"><span data-stu-id="0c019-120">The most likely cause of this is that there has been a permissions error or an encryption error when the SSO service account attempted to access the registry.</span></span> <span data-ttu-id="0c019-121">Esto puede producirse si se ha cambiado la cuenta de servicio SSO.</span><span class="sxs-lookup"><span data-stu-id="0c019-121">This can occur when the SSO service account has been changed.</span></span> <span data-ttu-id="0c019-122">El secreto principal se cifra con una clave basada en la identidad de dicha cuenta.</span><span class="sxs-lookup"><span data-stu-id="0c019-122">The master secret is encrypted with a key that is based on the identity of the SSO service account.</span></span> <span data-ttu-id="0c019-123">Si se cambia esa cuenta, el secreto principal existente del Registro ya no se puede descifrar.</span><span class="sxs-lookup"><span data-stu-id="0c019-123">If that account is changed, then the existing master secret in the registry can no longer be decrypted.</span></span>  

## <a name="user-action"></a><span data-ttu-id="0c019-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="0c019-124">User Action</span></span>  
 <span data-ttu-id="0c019-125">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0c019-125">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="0c019-126">Cambie la cuenta de servicio SSO. Para ello, haga una copia de seguridad del secreto principal, a continuación, cambie la cuenta de servicio SSO y, por último, restaure el secreto principal.</span><span class="sxs-lookup"><span data-stu-id="0c019-126">Change the SSO service account by backing-up the master secret, then changing the SSO service account, and then restoring the master secret.</span></span> <span data-ttu-id="0c019-127">Este procedimiento puede restaurar el secreto principal y debería solucionar este error.</span><span class="sxs-lookup"><span data-stu-id="0c019-127">This can restore the master secret and should fix this error.</span></span>  

  <span data-ttu-id="0c019-128">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="0c019-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="0c019-129">Servidor de secreto maestro</span><span class="sxs-lookup"><span data-stu-id="0c019-129">Master Secret Server</span></span>](../core/master-secret-server.md)  

- [<span data-ttu-id="0c019-130">Administración del secreto maestro</span><span class="sxs-lookup"><span data-stu-id="0c019-130">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)  

- [<span data-ttu-id="0c019-131">Configuración de SSO</span><span class="sxs-lookup"><span data-stu-id="0c019-131">Configuring SSO</span></span>](../core/configuring-sso.md)  

- [<span data-ttu-id="0c019-132">Recomendaciones de seguridad de SSO</span><span class="sxs-lookup"><span data-stu-id="0c019-132">SSO Security Recommendations</span></span>](../core/sso-security-recommendations.md)
