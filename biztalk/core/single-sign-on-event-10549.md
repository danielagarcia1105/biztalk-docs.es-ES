---
title: 'De sesión único: Evento 10549 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a18eb63-700c-4f49-acc4-890abe2a00ff
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18a3b92192c7e7e4a0906bfd35e4069dd3481d45
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993445"
---
# <a name="single-sign-on-event-10549"></a><span data-ttu-id="81aaa-102">De sesión único: Evento 10549</span><span class="sxs-lookup"><span data-stu-id="81aaa-102">Single Sign-On: Event 10549</span></span>
## <a name="details"></a><span data-ttu-id="81aaa-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="81aaa-103">Details</span></span>  

|                 |                                                                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="81aaa-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="81aaa-104">Product Name</span></span>   |                                                                                <span data-ttu-id="81aaa-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="81aaa-105">Enterprise Single Sign-On</span></span>                                                                                 |
| <span data-ttu-id="81aaa-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="81aaa-106">Product Version</span></span> |                                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                |
|    <span data-ttu-id="81aaa-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="81aaa-107">Event ID</span></span>     |                                                                                          <span data-ttu-id="81aaa-108">10549</span><span class="sxs-lookup"><span data-stu-id="81aaa-108">10549</span></span>                                                                                           |
|  <span data-ttu-id="81aaa-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="81aaa-109">Event Source</span></span>   |                                                                                          <span data-ttu-id="81aaa-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="81aaa-110">ENTSSO</span></span>                                                                                          |
|    <span data-ttu-id="81aaa-111">Componente</span><span class="sxs-lookup"><span data-stu-id="81aaa-111">Component</span></span>    |                                                                                            <span data-ttu-id="81aaa-112">CO</span><span class="sxs-lookup"><span data-stu-id="81aaa-112">CO</span></span>                                                                                            |
|  <span data-ttu-id="81aaa-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="81aaa-113">Symbolic Name</span></span>  |                                                                             <span data-ttu-id="81aaa-114">SSO_ERROR_CREATE_DATABASE_FAILED</span><span class="sxs-lookup"><span data-stu-id="81aaa-114">SSO_ERROR_CREATE_DATABASE_FAILED</span></span>                                                                             |
|  <span data-ttu-id="81aaa-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="81aaa-115">Message Text</span></span>   | <span data-ttu-id="81aaa-116">Error al crear e inicializar la base de datos de SSO.%r</span><span class="sxs-lookup"><span data-stu-id="81aaa-116">Creation and initialization of the SSO database failed.%r</span></span><br /><br /> <span data-ttu-id="81aaa-117">Nombre de SQL Server: %1 %r</span><span class="sxs-lookup"><span data-stu-id="81aaa-117">SQL Server Name: %1%r</span></span><br /><br /> <span data-ttu-id="81aaa-118">Nombre de la base de datos SSO: %2 %r</span><span class="sxs-lookup"><span data-stu-id="81aaa-118">SSO Database Name: %2%r</span></span><br /><br /> <span data-ttu-id="81aaa-119">Usuario cliente: %3 %r</span><span class="sxs-lookup"><span data-stu-id="81aaa-119">Client User: %3%r</span></span><br /><br /> <span data-ttu-id="81aaa-120">Código de error: %4</span><span class="sxs-lookup"><span data-stu-id="81aaa-120">Error Code: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="81aaa-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="81aaa-121">Explanation</span></span>  
 <span data-ttu-id="81aaa-122">Este error indica que no se pudo crear e inicializar la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="81aaa-122">This Error indicates that creation and initialization of the SSO database failed.</span></span>  

## <a name="user-action"></a><span data-ttu-id="81aaa-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="81aaa-123">User Action</span></span>  
 <span data-ttu-id="81aaa-124">Para solucionar el error, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="81aaa-124">To resolve this error do the following:</span></span>  

- <span data-ttu-id="81aaa-125">Compruebe si en los registros de eventos del sistema y la aplicación existen mensajes asociados.</span><span class="sxs-lookup"><span data-stu-id="81aaa-125">Check the system and application event logs for associated messages.</span></span>  

- <span data-ttu-id="81aaa-126">Vuelva a ejecutar el programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="81aaa-126">Run Setup again.</span></span>  

  <span data-ttu-id="81aaa-127">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="81aaa-127">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="81aaa-128">Instalación de SSO</span><span class="sxs-lookup"><span data-stu-id="81aaa-128">Installing SSO</span></span>](../core/installing-sso.md)
