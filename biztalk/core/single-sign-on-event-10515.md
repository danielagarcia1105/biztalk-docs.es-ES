---
title: "Inicio de sesión único: Evento 10515 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41edc008-b6d3-401d-97af-80b36ab0ba55
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e2b884ae52af96ceaae83f8b092ed15b6b12e3a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10515"></a><span data-ttu-id="00fea-102">Inicio de sesión único: Evento 10515</span><span class="sxs-lookup"><span data-stu-id="00fea-102">Single Sign-On: Event 10515</span></span>
## <a name="details"></a><span data-ttu-id="00fea-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="00fea-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="00fea-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="00fea-104">Product Name</span></span>|<span data-ttu-id="00fea-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="00fea-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="00fea-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="00fea-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="00fea-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="00fea-107">Event ID</span></span>|<span data-ttu-id="00fea-108">10515</span><span class="sxs-lookup"><span data-stu-id="00fea-108">10515</span></span>|  
|<span data-ttu-id="00fea-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="00fea-109">Event Source</span></span>|<span data-ttu-id="00fea-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="00fea-110">ENTSSO</span></span>|  
|<span data-ttu-id="00fea-111">Componente</span><span class="sxs-lookup"><span data-stu-id="00fea-111">Component</span></span>|<span data-ttu-id="00fea-112">N\D</span><span class="sxs-lookup"><span data-stu-id="00fea-112">N\A</span></span>|  
|<span data-ttu-id="00fea-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="00fea-113">Symbolic Name</span></span>|<span data-ttu-id="00fea-114">SSO_ERROR_POLL_DATABASE</span><span class="sxs-lookup"><span data-stu-id="00fea-114">SSO_ERROR_POLL_DATABASE</span></span>|  
|<span data-ttu-id="00fea-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="00fea-115">Message Text</span></span>|<span data-ttu-id="00fea-116">Se interrumpió la comunicación con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="00fea-116">Lost contact with the SSO database.</span></span> <span data-ttu-id="00fea-117">Compruebe si la base de datos de SSO está disponible.</span><span class="sxs-lookup"><span data-stu-id="00fea-117">Check that the SSO database is available.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="00fea-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="00fea-118">Explanation</span></span>  
 <span data-ttu-id="00fea-119">Este evento de error indica que se interrumpió la comunicación entre el servicio SSO y la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="00fea-119">This Error event indicates that the SSO Service has lost contact with the SSO database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="00fea-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="00fea-120">User Action</span></span>  
 <span data-ttu-id="00fea-121">Para resolver este error, realice una o varias de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="00fea-121">To resolve this error, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="00fea-122">Compruebe que se está ejecutando el servicio SQL Server (MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="00fea-122">Verify that the SQL Server (MSSQLSERVER) service is running.</span></span>  
  
-   <span data-ttu-id="00fea-123">Compruebe la conectividad de red con SQL Server si se encuentra en un servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="00fea-123">Verify network connectivity to SQL Server if on a remote server.</span></span>  
  
 <span data-ttu-id="00fea-124">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="00fea-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="00fea-125">Implementación de Enterprise Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="00fea-125">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)  
  
-   [<span data-ttu-id="00fea-126">Cómo mostrar la información de la base de datos SSO</span><span class="sxs-lookup"><span data-stu-id="00fea-126">How to Display the SSO Database Information</span></span>](../core/how-to-display-the-sso-database-information.md)  
  
-   [<span data-ttu-id="00fea-127">Configuración de SSO</span><span class="sxs-lookup"><span data-stu-id="00fea-127">Configuring SSO</span></span>](../core/configuring-sso.md)  
  
 <span data-ttu-id="00fea-128">También consulte Libros en pantalla de SQL Server</span><span class="sxs-lookup"><span data-stu-id="00fea-128">See also SQL Server Books Online</span></span>