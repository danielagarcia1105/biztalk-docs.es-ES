---
title: 'De sesión único: Evento 10538 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1211ac33-9149-4dd3-85a2-d46eb24d1060
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f4b7fba63d26fde664e14470eb95b41a1580ae7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975781"
---
# <a name="single-sign-on-event-10538"></a><span data-ttu-id="98fc6-102">De sesión único: Evento 10538</span><span class="sxs-lookup"><span data-stu-id="98fc6-102">Single Sign-On: Event 10538</span></span>
## <a name="details"></a><span data-ttu-id="98fc6-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="98fc6-103">Details</span></span>  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  <span data-ttu-id="98fc6-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="98fc6-104">Product Name</span></span>   |                         <span data-ttu-id="98fc6-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="98fc6-105">Enterprise Single Sign-On</span></span>                         |
| <span data-ttu-id="98fc6-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="98fc6-106">Product Version</span></span> |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    <span data-ttu-id="98fc6-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="98fc6-107">Event ID</span></span>     |                                   <span data-ttu-id="98fc6-108">10538</span><span class="sxs-lookup"><span data-stu-id="98fc6-108">10538</span></span>                                   |
|  <span data-ttu-id="98fc6-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="98fc6-109">Event Source</span></span>   |                                  <span data-ttu-id="98fc6-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="98fc6-110">ENTSSO</span></span>                                   |
|    <span data-ttu-id="98fc6-111">Componente</span><span class="sxs-lookup"><span data-stu-id="98fc6-111">Component</span></span>    |                                    <span data-ttu-id="98fc6-112">CO</span><span class="sxs-lookup"><span data-stu-id="98fc6-112">CO</span></span>                                     |
|  <span data-ttu-id="98fc6-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="98fc6-113">Symbolic Name</span></span>  |                           <span data-ttu-id="98fc6-114">SSO_WARN_APP_DISABLED</span><span class="sxs-lookup"><span data-stu-id="98fc6-114">SSO_WARN_APP_DISABLED</span></span>                           |
|  <span data-ttu-id="98fc6-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="98fc6-115">Message Text</span></span>   | <span data-ttu-id="98fc6-116">Actualmente la aplicación está deshabilitada.%r</span><span class="sxs-lookup"><span data-stu-id="98fc6-116">The application is currently disabled.%r</span></span><br /><br /> <span data-ttu-id="98fc6-117">Nombre de la aplicación: %1</span><span class="sxs-lookup"><span data-stu-id="98fc6-117">Application Name: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="98fc6-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="98fc6-118">Explanation</span></span>  
 <span data-ttu-id="98fc6-119">Este evento de advertencia indica que el administrador de aplicaciones deshabilitó la aplicación afiliada de SSO.</span><span class="sxs-lookup"><span data-stu-id="98fc6-119">This Warning event indicates that the SSO affiliate application has been disabled by an Application Administrator.</span></span>  

## <a name="user-action"></a><span data-ttu-id="98fc6-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="98fc6-120">User Action</span></span>  
 <span data-ttu-id="98fc6-121">Para solucionar la advertencia, realice una o varias de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="98fc6-121">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="98fc6-122">Póngase en contacto con el administrador de aplicaciones para habilitar la aplicación afiliada de SSO.</span><span class="sxs-lookup"><span data-stu-id="98fc6-122">Contact your Application Administrator to enable the SSO affiliate application.</span></span> <span data-ttu-id="98fc6-123">Esto puede realizarse mediante las herramientas de administración de SSO (GUI o línea de comandos).</span><span class="sxs-lookup"><span data-stu-id="98fc6-123">This can be done using the SSO administration tools (GUI or command line).</span></span>  

  <span data-ttu-id="98fc6-124">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="98fc6-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="98fc6-125">Cómo habilitar una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="98fc6-125">How to Enable an Affiliate Application</span></span>](../core/how-to-enable-an-affiliate-application.md)  

- [<span data-ttu-id="98fc6-126">Cómo deshabilitar una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="98fc6-126">How to Disable an Affiliate Application</span></span>](../core/how-to-disable-an-affiliate-application.md)
