---
title: 'De sesión único: Evento 10532 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae2112bc-b53c-4d99-9dc1-a2f55dda4665
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 135060013686ff24e4f2692bda0e8829189e1c4a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974853"
---
# <a name="single-sign-on-event-10532"></a><span data-ttu-id="0e34e-102">De sesión único: Evento 10532</span><span class="sxs-lookup"><span data-stu-id="0e34e-102">Single Sign-On: Event 10532</span></span>
## <a name="details"></a><span data-ttu-id="0e34e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="0e34e-103">Details</span></span>  

|                 |                                                                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="0e34e-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="0e34e-104">Product Name</span></span>   |                                                                              <span data-ttu-id="0e34e-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="0e34e-105">Enterprise Single Sign-On</span></span>                                                                              |
| <span data-ttu-id="0e34e-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="0e34e-106">Product Version</span></span> |                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                              |
|    <span data-ttu-id="0e34e-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="0e34e-107">Event ID</span></span>     |                                                                                        <span data-ttu-id="0e34e-108">10532</span><span class="sxs-lookup"><span data-stu-id="0e34e-108">10532</span></span>                                                                                        |
|  <span data-ttu-id="0e34e-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="0e34e-109">Event Source</span></span>   |                                                                                       <span data-ttu-id="0e34e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0e34e-110">ENTSSO</span></span>                                                                                        |
|    <span data-ttu-id="0e34e-111">Componente</span><span class="sxs-lookup"><span data-stu-id="0e34e-111">Component</span></span>    |                                                                                         <span data-ttu-id="0e34e-112">CO</span><span class="sxs-lookup"><span data-stu-id="0e34e-112">CO</span></span>                                                                                          |
|  <span data-ttu-id="0e34e-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="0e34e-113">Symbolic Name</span></span>  |                                                                             <span data-ttu-id="0e34e-114">SSO_WARN_LOST_SECRET_SERVER</span><span class="sxs-lookup"><span data-stu-id="0e34e-114">SSO_WARN_LOST_SECRET_SERVER</span></span>                                                                             |
|  <span data-ttu-id="0e34e-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="0e34e-115">Message Text</span></span>   | <span data-ttu-id="0e34e-116">No se pudieron recuperar los secretos principales.</span><span class="sxs-lookup"><span data-stu-id="0e34e-116">Failed to retrieve master secrets.</span></span> <span data-ttu-id="0e34e-117">Compruebe si el nombre del servidor secreto principal es correcto y está disponible.%r</span><span class="sxs-lookup"><span data-stu-id="0e34e-117">Verify that the master secret server name is correct and that it is available.%r</span></span><br /><br /> <span data-ttu-id="0e34e-118">Nombre del servidor secreto: %1 %r</span><span class="sxs-lookup"><span data-stu-id="0e34e-118">Secret Server Name: %1%r</span></span><br /><br /> <span data-ttu-id="0e34e-119">Código de error: %2</span><span class="sxs-lookup"><span data-stu-id="0e34e-119">Error Code: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="0e34e-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="0e34e-120">Explanation</span></span>  
 <span data-ttu-id="0e34e-121">Este evento de advertencia indica que la solicitud de obtención del secreto principal generó un error.</span><span class="sxs-lookup"><span data-stu-id="0e34e-121">This Warning event indicates that a request to get the master secret has failed.</span></span> <span data-ttu-id="0e34e-122">Es posible que esto se deba a que el servicio Inicio de sesión único empresarial no está en ejecución en el servidor.</span><span class="sxs-lookup"><span data-stu-id="0e34e-122">This might be because the Enterprise Single Sign-On service is not running on the server.</span></span>  

## <a name="user-action"></a><span data-ttu-id="0e34e-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="0e34e-123">User Action</span></span>  
 <span data-ttu-id="0e34e-124">Para solucionar la advertencia, realice una o varias de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="0e34e-124">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="0e34e-125">Compruebe si el registro de eventos de la aplicación contiene eventos o errores asociados.</span><span class="sxs-lookup"><span data-stu-id="0e34e-125">Check the Application event log for associated events or errors.</span></span>  

- <span data-ttu-id="0e34e-126">Compruebe si el nombre de servidor secreto principal es correcto.</span><span class="sxs-lookup"><span data-stu-id="0e34e-126">Verify the master secret server name is correct.</span></span>  

- <span data-ttu-id="0e34e-127">Compruebe si el servidor secreto principal está desconectado y si el servicio Inicio de sesión único empresarial está en ejecución.</span><span class="sxs-lookup"><span data-stu-id="0e34e-127">Verify the master secret server is online and that the Enterprise Single Sign-On service is running.</span></span>  

  <span data-ttu-id="0e34e-128">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="0e34e-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="0e34e-129">Cómo generar el secreto principal</span><span class="sxs-lookup"><span data-stu-id="0e34e-129">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  

- [<span data-ttu-id="0e34e-130">Administración del secreto maestro</span><span class="sxs-lookup"><span data-stu-id="0e34e-130">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)
