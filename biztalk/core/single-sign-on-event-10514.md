---
title: "Inicio de sesión único: Evento 10514 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b527841-a2e2-44c7-a9cb-6e9a8eea2fba
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40077ead4157b4cc6c91a2c44b4a19569d76ebc1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10514"></a><span data-ttu-id="82217-102">Inicio de sesión único: Evento 10514</span><span class="sxs-lookup"><span data-stu-id="82217-102">Single Sign-On: Event 10514</span></span>
## <a name="details"></a><span data-ttu-id="82217-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="82217-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="82217-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="82217-104">Product Name</span></span>|<span data-ttu-id="82217-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="82217-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="82217-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="82217-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="82217-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="82217-107">Event ID</span></span>|<span data-ttu-id="82217-108">10514</span><span class="sxs-lookup"><span data-stu-id="82217-108">10514</span></span>|  
|<span data-ttu-id="82217-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="82217-109">Event Source</span></span>|<span data-ttu-id="82217-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="82217-110">ENTSSO</span></span>|  
|<span data-ttu-id="82217-111">Componente</span><span class="sxs-lookup"><span data-stu-id="82217-111">Component</span></span>|<span data-ttu-id="82217-112">N\D</span><span class="sxs-lookup"><span data-stu-id="82217-112">N\A</span></span>|  
|<span data-ttu-id="82217-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="82217-113">Symbolic Name</span></span>|<span data-ttu-id="82217-114">SSO_ERROR_DB_ACCESS</span><span class="sxs-lookup"><span data-stu-id="82217-114">SSO_ERROR_DB_ACCESS</span></span>|  
|<span data-ttu-id="82217-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="82217-115">Message Text</span></span>|<span data-ttu-id="82217-116">Error al intentar obtener acceso a la base de datos de SSO.%r</span><span class="sxs-lookup"><span data-stu-id="82217-116">An error occurred while attempting to access the SSO database.%r</span></span><br /><br /> <span data-ttu-id="82217-117">Función: %1 %r</span><span class="sxs-lookup"><span data-stu-id="82217-117">Function: %1%r</span></span><br /><br /> <span data-ttu-id="82217-118">Archivo: %2 %r</span><span class="sxs-lookup"><span data-stu-id="82217-118">File: %2%r</span></span><br /><br /> <span data-ttu-id="82217-119">%3.%r</span><span class="sxs-lookup"><span data-stu-id="82217-119">%3.%r</span></span><br /><br /> <span data-ttu-id="82217-120">Código de Error SQL: %4 %r</span><span class="sxs-lookup"><span data-stu-id="82217-120">SQL Error code: %4%r</span></span><br /><br /> <span data-ttu-id="82217-121">Código de error: %5</span><span class="sxs-lookup"><span data-stu-id="82217-121">Error code: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="82217-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="82217-122">Explanation</span></span>  
 <span data-ttu-id="82217-123">Este evento de error indica que se recibió un error de SQL Server al intentar obtener acceso a la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="82217-123">This Error event indicates that an error was received from SQL Server when attempting to access the SSO database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="82217-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="82217-124">User Action</span></span>  
 <span data-ttu-id="82217-125">Para resolver este error, realice una o varias de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="82217-125">To resolve this error, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="82217-126">Compruebe que se está ejecutando el servicio SQL Server (MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="82217-126">Verify that the SQL Server (MSSQLSERVER) service is running.</span></span>  
  
-   <span data-ttu-id="82217-127">Compruebe el código de error de SQL Server mediante los eventos y Errors Message Center en [http://go.microsoft.com/fwlink/?LinkID=20869](http://go.microsoft.com/fwlink/?LinkID=20869).</span><span class="sxs-lookup"><span data-stu-id="82217-127">Check the SQL Server error code using the Events and Errors Message Center at [http://go.microsoft.com/fwlink/?LinkID=20869](http://go.microsoft.com/fwlink/?LinkID=20869).</span></span>  
  
 <span data-ttu-id="82217-128">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="82217-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="82217-129">Implementación de Enterprise Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="82217-129">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)  
  
-   [<span data-ttu-id="82217-130">Cómo mostrar la información de la base de datos SSO</span><span class="sxs-lookup"><span data-stu-id="82217-130">How to Display the SSO Database Information</span></span>](../core/how-to-display-the-sso-database-information.md)  
  
 <span data-ttu-id="82217-131">Consulte, también, Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="82217-131">See also SQL Server Books Online.</span></span>