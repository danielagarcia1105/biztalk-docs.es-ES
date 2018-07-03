---
title: 'De sesión único: Evento 10540 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce91ff30-3d68-4c5f-a955-5c426e94d917
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1bcd7cc64a79634aa7868791d7e74e92cd1c4a3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990949"
---
# <a name="single-sign-on-event-10540"></a><span data-ttu-id="5f8ac-102">De sesión único: Evento 10540</span><span class="sxs-lookup"><span data-stu-id="5f8ac-102">Single Sign-On: Event 10540</span></span>
## <a name="details"></a><span data-ttu-id="5f8ac-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="5f8ac-103">Details</span></span>  

|                 |                                                                                  |
|-----------------|----------------------------------------------------------------------------------|
|  <span data-ttu-id="5f8ac-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="5f8ac-104">Product Name</span></span>   |                            <span data-ttu-id="5f8ac-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="5f8ac-105">Enterprise Single Sign-On</span></span>                             |
| <span data-ttu-id="5f8ac-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="5f8ac-106">Product Version</span></span> |            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]            |
|    <span data-ttu-id="5f8ac-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="5f8ac-107">Event ID</span></span>     |                                      <span data-ttu-id="5f8ac-108">10540</span><span class="sxs-lookup"><span data-stu-id="5f8ac-108">10540</span></span>                                       |
|  <span data-ttu-id="5f8ac-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="5f8ac-109">Event Source</span></span>   |                                      <span data-ttu-id="5f8ac-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5f8ac-110">ENTSSO</span></span>                                      |
|    <span data-ttu-id="5f8ac-111">Componente</span><span class="sxs-lookup"><span data-stu-id="5f8ac-111">Component</span></span>    |                                        <span data-ttu-id="5f8ac-112">CO</span><span class="sxs-lookup"><span data-stu-id="5f8ac-112">CO</span></span>                                        |
|  <span data-ttu-id="5f8ac-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="5f8ac-113">Symbolic Name</span></span>  |                         <span data-ttu-id="5f8ac-114">SSO_WARN_APP_TICKETS_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="5f8ac-114">SSO_WARN_APP_TICKETS_NOT_ALLOWED</span></span>                         |
|  <span data-ttu-id="5f8ac-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="5f8ac-115">Message Text</span></span>   | <span data-ttu-id="5f8ac-116">No se habilitaron vales para la aplicación.%r</span><span class="sxs-lookup"><span data-stu-id="5f8ac-116">Tickets are not enabled for this application.%r</span></span><br /><br /> <span data-ttu-id="5f8ac-117">Nombre de la aplicación: %1</span><span class="sxs-lookup"><span data-stu-id="5f8ac-117">Application Name: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="5f8ac-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="5f8ac-118">Explanation</span></span>  
 <span data-ttu-id="5f8ac-119">Este evento de advertencia indica que no se habilitó la característica de vales para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5f8ac-119">This Warning event indicates that the tickets feature has not been enabled for this application.</span></span> <span data-ttu-id="5f8ac-120">El uso de vales de SSO es una característica opcional para cada aplicación de SSO.</span><span class="sxs-lookup"><span data-stu-id="5f8ac-120">The use of SSO tickets is an optional feature for each SSO application.</span></span>  

## <a name="user-action"></a><span data-ttu-id="5f8ac-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="5f8ac-121">User Action</span></span>  
 <span data-ttu-id="5f8ac-122">Para resolver esta advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5f8ac-122">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="5f8ac-123">Póngase en contacto con el administrador de aplicaciones para habilitar vales para el sistema SSO.</span><span class="sxs-lookup"><span data-stu-id="5f8ac-123">Contact your Application Administrator to enable tickets for this SSO application.</span></span> <span data-ttu-id="5f8ac-124">Esto puede realizarse mediante las herramientas de administración de SSO (GUI o línea de comandos).</span><span class="sxs-lookup"><span data-stu-id="5f8ac-124">This can be done using the SSO administration tools (GUI or command line).</span></span>  

  <span data-ttu-id="5f8ac-125">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="5f8ac-125">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="5f8ac-126">Vales de SSO</span><span class="sxs-lookup"><span data-stu-id="5f8ac-126">SSO Tickets</span></span>](../core/sso-tickets.md)  

- [<span data-ttu-id="5f8ac-127">Cómo enumerar las propiedades de una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="5f8ac-127">How to List the Properties of an Affiliate Application</span></span>](../core/how-to-list-the-properties-of-an-affiliate-application.md)  

- [<span data-ttu-id="5f8ac-128">Cómo actualizar las propiedades de una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="5f8ac-128">How to Update the Properties of an Affiliate Application</span></span>](../core/how-to-update-the-properties-of-an-affiliate-application.md)
