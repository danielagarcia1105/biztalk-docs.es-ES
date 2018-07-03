---
title: 'De sesión único: Evento 10527 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 40995ad8-9f74-4e96-863d-427e23025ba1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac787d375e8ccc4c578c2450b7cc6128dd427483
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972997"
---
# <a name="single-sign-on-event-10527"></a><span data-ttu-id="ccd63-102">De sesión único: Evento 10527</span><span class="sxs-lookup"><span data-stu-id="ccd63-102">Single Sign-On: Event 10527</span></span>
## <a name="details"></a><span data-ttu-id="ccd63-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ccd63-103">Details</span></span>  

|                 |                                                                                                                                                                                                     |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ccd63-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ccd63-104">Product Name</span></span>   |                                                                                      <span data-ttu-id="ccd63-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="ccd63-105">Enterprise Single Sign-On</span></span>                                                                                      |
| <span data-ttu-id="ccd63-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ccd63-106">Product Version</span></span> |                                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                      |
|    <span data-ttu-id="ccd63-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ccd63-107">Event ID</span></span>     |                                                                                                <span data-ttu-id="ccd63-108">10527</span><span class="sxs-lookup"><span data-stu-id="ccd63-108">10527</span></span>                                                                                                |
|  <span data-ttu-id="ccd63-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ccd63-109">Event Source</span></span>   |                                                                                               <span data-ttu-id="ccd63-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ccd63-110">ENTSSO</span></span>                                                                                                |
|    <span data-ttu-id="ccd63-111">Componente</span><span class="sxs-lookup"><span data-stu-id="ccd63-111">Component</span></span>    |                                                                                                  <span data-ttu-id="ccd63-112">0</span><span class="sxs-lookup"><span data-stu-id="ccd63-112">0</span></span>                                                                                                  |
|  <span data-ttu-id="ccd63-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ccd63-113">Symbolic Name</span></span>  |                                                                                     <span data-ttu-id="ccd63-114">SSO_ERROR_GET_SECRET_FAILED</span><span class="sxs-lookup"><span data-stu-id="ccd63-114">SSO_ERROR_GET_SECRET_FAILED</span></span>                                                                                     |
|  <span data-ttu-id="ccd63-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ccd63-115">Message Text</span></span>   | <span data-ttu-id="ccd63-116">Error de solicitud de obtención de secreto principal.%r</span><span class="sxs-lookup"><span data-stu-id="ccd63-116">A request to get a master secret failed.%r</span></span><br /><br /> <span data-ttu-id="ccd63-117">Número secreto: %1 %r</span><span class="sxs-lookup"><span data-stu-id="ccd63-117">Secret Number: %1%r</span></span><br /><br /> <span data-ttu-id="ccd63-118">Usuario cliente: %2 %r</span><span class="sxs-lookup"><span data-stu-id="ccd63-118">Client User: %2%r</span></span><br /><br /> <span data-ttu-id="ccd63-119">Equipo cliente: %3 %r</span><span class="sxs-lookup"><span data-stu-id="ccd63-119">Client Computer: %3%r</span></span><br /><br /> <span data-ttu-id="ccd63-120">Id. de seguimiento: %4 %r</span><span class="sxs-lookup"><span data-stu-id="ccd63-120">Tracking ID: %4%r</span></span><br /><br /> <span data-ttu-id="ccd63-121">Código de error: %5</span><span class="sxs-lookup"><span data-stu-id="ccd63-121">Error Code: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="ccd63-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="ccd63-122">Explanation</span></span>  
 <span data-ttu-id="ccd63-123">Este evento de error indica que la solicitud de obtención del secreto principal generó un error.</span><span class="sxs-lookup"><span data-stu-id="ccd63-123">This Error event indicates that a request to get the master secret has failed.</span></span> <span data-ttu-id="ccd63-124">En estos casos, debería haber mensajes relacionados en el registro de eventos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ccd63-124">In these cases there should be related messages in the Application event log.</span></span>  

## <a name="user-action"></a><span data-ttu-id="ccd63-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ccd63-125">User Action</span></span>  
 <span data-ttu-id="ccd63-126">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ccd63-126">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="ccd63-127">Compruebe si el registro de eventos de la aplicación contiene eventos o errores asociados.</span><span class="sxs-lookup"><span data-stu-id="ccd63-127">Check the Application event log for associated events or errors.</span></span>  

  <span data-ttu-id="ccd63-128">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ccd63-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="ccd63-129">Cómo generar el secreto principal</span><span class="sxs-lookup"><span data-stu-id="ccd63-129">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  

- [<span data-ttu-id="ccd63-130">Administración del secreto maestro</span><span class="sxs-lookup"><span data-stu-id="ccd63-130">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)
