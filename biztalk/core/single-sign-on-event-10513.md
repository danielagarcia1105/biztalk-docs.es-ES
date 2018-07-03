---
title: 'De sesión único: Evento 10513 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3306223-111f-4abf-ae65-be839b355216
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c61b1b861cb14ec0d16dce27fd26360df7fcdc98
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981629"
---
# <a name="single-sign-on-event-10513"></a><span data-ttu-id="9ca00-102">De sesión único: Evento 10513</span><span class="sxs-lookup"><span data-stu-id="9ca00-102">Single Sign-On: Event 10513</span></span>
## <a name="details"></a><span data-ttu-id="9ca00-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="9ca00-103">Details</span></span>  

|                 |                                                                                      |
|-----------------|--------------------------------------------------------------------------------------|
|  <span data-ttu-id="9ca00-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="9ca00-104">Product Name</span></span>   |                              <span data-ttu-id="9ca00-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="9ca00-105">Enterprise Single Sign-On</span></span>                               |
| <span data-ttu-id="9ca00-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="9ca00-106">Product Version</span></span> |              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]              |
|    <span data-ttu-id="9ca00-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="9ca00-107">Event ID</span></span>     |                                        <span data-ttu-id="9ca00-108">10513</span><span class="sxs-lookup"><span data-stu-id="9ca00-108">10513</span></span>                                         |
|  <span data-ttu-id="9ca00-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="9ca00-109">Event Source</span></span>   |                                        <span data-ttu-id="9ca00-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="9ca00-110">ENTSSO</span></span>                                        |
|    <span data-ttu-id="9ca00-111">Componente</span><span class="sxs-lookup"><span data-stu-id="9ca00-111">Component</span></span>    |                                         <span data-ttu-id="9ca00-112">N\D</span><span class="sxs-lookup"><span data-stu-id="9ca00-112">N\A</span></span>                                          |
|  <span data-ttu-id="9ca00-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="9ca00-113">Symbolic Name</span></span>  |                              <span data-ttu-id="9ca00-114">SSO_ERROR_DB_FIRST_ACCESS</span><span class="sxs-lookup"><span data-stu-id="9ca00-114">SSO_ERROR_DB_FIRST_ACCESS</span></span>                               |
|  <span data-ttu-id="9ca00-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="9ca00-115">Message Text</span></span>   | <span data-ttu-id="9ca00-116">No se pudo ponerse en contacto con la base de datos SSO: %1 %r</span><span class="sxs-lookup"><span data-stu-id="9ca00-116">Failed to contact the SSO database: %1%r</span></span><br /><br /> <span data-ttu-id="9ca00-117">%2 %r</span><span class="sxs-lookup"><span data-stu-id="9ca00-117">%2%r</span></span><br /><br /> <span data-ttu-id="9ca00-118">Código de error: %3</span><span class="sxs-lookup"><span data-stu-id="9ca00-118">Error code: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="9ca00-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="9ca00-119">Explanation</span></span>  
 <span data-ttu-id="9ca00-120">Este evento de error indica que el servicio SSO no puede conectarse con la base de datos de SSO cuando se inicia.</span><span class="sxs-lookup"><span data-stu-id="9ca00-120">This Error event indicates that the SSO Service cannot connect to the SSO database when it starts.</span></span> <span data-ttu-id="9ca00-121">El mensaje de evento contiene la cadena de nombre de origen de datos (DSN) que indica los nombres de servidor SQL Server y de base de datos especificados, además del mensaje de error que se devolvió de las bibliotecas de conexión de SQL.</span><span class="sxs-lookup"><span data-stu-id="9ca00-121">The event message contains the Data Source Name (DSN) string indicating the specified SQL Server and database names as well as the error message that was returned from the SQL connection libraries.</span></span>  

 <span data-ttu-id="9ca00-122">Cuando se inicie el servicio SSO, intentará conectarse con la base de datos de SSO mediante los nombres de servidor SQL Server y de base de datos especificados en el Registro.</span><span class="sxs-lookup"><span data-stu-id="9ca00-122">When the SSO Service starts, it will attempt to connect to the SSO database using the SQL Server and SSO database names specified in the registry.</span></span> <span data-ttu-id="9ca00-123">El servicio SSO intentará conectarse 12 veces, con cinco (5) segundos de espera entre cada intento con error, durante un total de un (1) minuto.</span><span class="sxs-lookup"><span data-stu-id="9ca00-123">The SSO Service will attempt to connect 12 times, waiting 5 seconds between each failed attempt, for a total of 1 minute.</span></span>  

## <a name="user-action"></a><span data-ttu-id="9ca00-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="9ca00-124">User Action</span></span>  
 <span data-ttu-id="9ca00-125">Para resolver este error, realice una o varias de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="9ca00-125">To resolve this error, do one or more of the following:</span></span>  

- <span data-ttu-id="9ca00-126">Compruebe que se está ejecutando el servicio SQL Server (MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="9ca00-126">Verify the SQL Server (MSSQLSERVER) service is running.</span></span>  

- <span data-ttu-id="9ca00-127">Compruebe si es correcta la cadena de nombre de origen de datos (DSN) indicada en el mensaje de error y si contiene los nombres de servidor SQL Server y de base de datos.</span><span class="sxs-lookup"><span data-stu-id="9ca00-127">Verify the Data Source Name (DSN) string indicated in the error message is correct and contains the correct SQL Server and database names.</span></span>  

  <span data-ttu-id="9ca00-128">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="9ca00-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="9ca00-129">Implementación de Enterprise Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="9ca00-129">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)  

- [<span data-ttu-id="9ca00-130">Cómo mostrar la información de la base de datos SSO</span><span class="sxs-lookup"><span data-stu-id="9ca00-130">How to Display the SSO Database Information</span></span>](../core/how-to-display-the-sso-database-information.md)  

- [<span data-ttu-id="9ca00-131">Configuración de SSO</span><span class="sxs-lookup"><span data-stu-id="9ca00-131">Configuring SSO</span></span>](../core/configuring-sso.md)  

- <span data-ttu-id="9ca00-132">SQL Server, Libros en pantalla</span><span class="sxs-lookup"><span data-stu-id="9ca00-132">SQL Server Books Online</span></span>
