---
title: 'De sesión único: Evento 10515 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41edc008-b6d3-401d-97af-80b36ab0ba55
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1c3d7498bcd6a045936103d682d3643761a182c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980821"
---
# <a name="single-sign-on-event-10515"></a><span data-ttu-id="cadd1-102">De sesión único: Evento 10515</span><span class="sxs-lookup"><span data-stu-id="cadd1-102">Single Sign-On: Event 10515</span></span>
## <a name="details"></a><span data-ttu-id="cadd1-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="cadd1-103">Details</span></span>  
  
|                 |                                                                               |
|-----------------|-------------------------------------------------------------------------------|
|  <span data-ttu-id="cadd1-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="cadd1-104">Product Name</span></span>   |                           <span data-ttu-id="cadd1-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="cadd1-105">Enterprise Single Sign-On</span></span>                           |
| <span data-ttu-id="cadd1-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="cadd1-106">Product Version</span></span> |          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]           |
|    <span data-ttu-id="cadd1-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="cadd1-107">Event ID</span></span>     |                                     <span data-ttu-id="cadd1-108">10515</span><span class="sxs-lookup"><span data-stu-id="cadd1-108">10515</span></span>                                     |
|  <span data-ttu-id="cadd1-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="cadd1-109">Event Source</span></span>   |                                    <span data-ttu-id="cadd1-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="cadd1-110">ENTSSO</span></span>                                     |
|    <span data-ttu-id="cadd1-111">Componente</span><span class="sxs-lookup"><span data-stu-id="cadd1-111">Component</span></span>    |                                      <span data-ttu-id="cadd1-112">N\D</span><span class="sxs-lookup"><span data-stu-id="cadd1-112">N\A</span></span>                                      |
|  <span data-ttu-id="cadd1-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="cadd1-113">Symbolic Name</span></span>  |                            <span data-ttu-id="cadd1-114">SSO_ERROR_POLL_DATABASE</span><span class="sxs-lookup"><span data-stu-id="cadd1-114">SSO_ERROR_POLL_DATABASE</span></span>                            |
|  <span data-ttu-id="cadd1-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="cadd1-115">Message Text</span></span>   | <span data-ttu-id="cadd1-116">Se interrumpió la comunicación con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="cadd1-116">Lost contact with the SSO database.</span></span> <span data-ttu-id="cadd1-117">Compruebe si la base de datos de SSO está disponible.</span><span class="sxs-lookup"><span data-stu-id="cadd1-117">Check that the SSO database is available.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="cadd1-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="cadd1-118">Explanation</span></span>  
 <span data-ttu-id="cadd1-119">Este evento de error indica que se interrumpió la comunicación entre el servicio SSO y la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="cadd1-119">This Error event indicates that the SSO Service has lost contact with the SSO database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cadd1-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="cadd1-120">User Action</span></span>  
 <span data-ttu-id="cadd1-121">Para resolver este error, realice una o varias de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="cadd1-121">To resolve this error, do one or more of the following:</span></span>  
  
- <span data-ttu-id="cadd1-122">Compruebe que se está ejecutando el servicio SQL Server (MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="cadd1-122">Verify that the SQL Server (MSSQLSERVER) service is running.</span></span>  
  
- <span data-ttu-id="cadd1-123">Compruebe la conectividad de red con SQL Server si se encuentra en un servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="cadd1-123">Verify network connectivity to SQL Server if on a remote server.</span></span>  
  
  <span data-ttu-id="cadd1-124">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="cadd1-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
- [<span data-ttu-id="cadd1-125">Implementación de Enterprise Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="cadd1-125">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)  
  
- [<span data-ttu-id="cadd1-126">Cómo mostrar la información de la base de datos SSO</span><span class="sxs-lookup"><span data-stu-id="cadd1-126">How to Display the SSO Database Information</span></span>](../core/how-to-display-the-sso-database-information.md)  
  
- [<span data-ttu-id="cadd1-127">Configuración de SSO</span><span class="sxs-lookup"><span data-stu-id="cadd1-127">Configuring SSO</span></span>](../core/configuring-sso.md)  
  
  <span data-ttu-id="cadd1-128">También vea Libros en pantalla de SQL Server</span><span class="sxs-lookup"><span data-stu-id="cadd1-128">See also SQL Server Books Online</span></span>