---
title: 'Inicio de sesión único: Evento 10533 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 31abd828-5f10-43f7-b99e-f3195250130c
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 661c2eb91e0b8886f200319e9595f9d25c7023f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270884"
---
# <a name="single-sign-on-event-10533"></a><span data-ttu-id="43f36-102">Inicio de sesión único: Evento 10533</span><span class="sxs-lookup"><span data-stu-id="43f36-102">Single Sign-On: Event 10533</span></span>
## <a name="details"></a><span data-ttu-id="43f36-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="43f36-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="43f36-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="43f36-104">Product Name</span></span>|<span data-ttu-id="43f36-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="43f36-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="43f36-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="43f36-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="43f36-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="43f36-107">Event ID</span></span>|<span data-ttu-id="43f36-108">10533</span><span class="sxs-lookup"><span data-stu-id="43f36-108">10533</span></span>|  
|<span data-ttu-id="43f36-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="43f36-109">Event Source</span></span>|<span data-ttu-id="43f36-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="43f36-110">ENTSSO</span></span>|  
|<span data-ttu-id="43f36-111">Componente</span><span class="sxs-lookup"><span data-stu-id="43f36-111">Component</span></span>|<span data-ttu-id="43f36-112">N\D</span><span class="sxs-lookup"><span data-stu-id="43f36-112">N\A</span></span>|  
|<span data-ttu-id="43f36-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="43f36-113">Symbolic Name</span></span>|<span data-ttu-id="43f36-114">SSO_INFO_GOT_CURRENT_SECRET</span><span class="sxs-lookup"><span data-stu-id="43f36-114">SSO_INFO_GOT_CURRENT_SECRET</span></span>|  
|<span data-ttu-id="43f36-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="43f36-115">Message Text</span></span>|<span data-ttu-id="43f36-116">Se obtuvo el secreto actual desde el servidor secreto principal.%r</span><span class="sxs-lookup"><span data-stu-id="43f36-116">Got the current secret from the master secret server.%r</span></span><br /><br /> <span data-ttu-id="43f36-117">Nombre del servidor secreto: %1 %r</span><span class="sxs-lookup"><span data-stu-id="43f36-117">Secret Server Name: %1%r</span></span><br /><br /> <span data-ttu-id="43f36-118">MSID: %2</span><span class="sxs-lookup"><span data-stu-id="43f36-118">MSID: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="43f36-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="43f36-119">Explanation</span></span>  
 <span data-ttu-id="43f36-120">Este evento de información indica que SSO cuenta con el secreto principal actual.</span><span class="sxs-lookup"><span data-stu-id="43f36-120">This Information event indicates that SSO has the current master secret.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="43f36-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="43f36-121">User Action</span></span>  
  
-   <span data-ttu-id="43f36-122">No es necesario que el usuario realice ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="43f36-122">No user action is necessary.</span></span>  
  
 <span data-ttu-id="43f36-123">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="43f36-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="43f36-124">Cómo generar el secreto principal</span><span class="sxs-lookup"><span data-stu-id="43f36-124">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  
  
-   [<span data-ttu-id="43f36-125">Administrar el secreto principal</span><span class="sxs-lookup"><span data-stu-id="43f36-125">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)