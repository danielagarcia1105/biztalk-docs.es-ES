---
title: 'De sesión único: Evento 10584 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8af9377d-b4fd-48a6-961a-3629b3db644a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0188f09ab94bd14df0dbe3fee0b91341cd9eb087
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996725"
---
# <a name="single-sign-on-event-10584"></a><span data-ttu-id="32e6d-102">De sesión único: Evento 10584</span><span class="sxs-lookup"><span data-stu-id="32e6d-102">Single Sign-On: Event 10584</span></span>
## <a name="details"></a><span data-ttu-id="32e6d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="32e6d-103">Details</span></span>  
  
|                 |                                                                |
|-----------------|----------------------------------------------------------------|
|  <span data-ttu-id="32e6d-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="32e6d-104">Product Name</span></span>   |                   <span data-ttu-id="32e6d-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="32e6d-105">Enterprise Single Sign-On</span></span>                    |
| <span data-ttu-id="32e6d-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="32e6d-106">Product Version</span></span> |   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    <span data-ttu-id="32e6d-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="32e6d-107">Event ID</span></span>     |                             <span data-ttu-id="32e6d-108">10584</span><span class="sxs-lookup"><span data-stu-id="32e6d-108">10584</span></span>                              |
|  <span data-ttu-id="32e6d-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="32e6d-109">Event Source</span></span>   |                             <span data-ttu-id="32e6d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="32e6d-110">ENTSSO</span></span>                             |
|    <span data-ttu-id="32e6d-111">Componente</span><span class="sxs-lookup"><span data-stu-id="32e6d-111">Component</span></span>    |                              <span data-ttu-id="32e6d-112">N/D</span><span class="sxs-lookup"><span data-stu-id="32e6d-112">N/A</span></span>                               |
|  <span data-ttu-id="32e6d-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="32e6d-113">Symbolic Name</span></span>  |                   <span data-ttu-id="32e6d-114">SSO_WARN_NO_IMPERSONATION</span><span class="sxs-lookup"><span data-stu-id="32e6d-114">SSO_WARN_NO_IMPERSONATION</span></span>                    |
|  <span data-ttu-id="32e6d-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="32e6d-115">Message Text</span></span>   | <span data-ttu-id="32e6d-116">No se pudo suplantar al cliente.%r</span><span class="sxs-lookup"><span data-stu-id="32e6d-116">Could not impersonate the client.%r</span></span><br /><br /> <span data-ttu-id="32e6d-117">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="32e6d-117">Error Code: %1</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="32e6d-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="32e6d-118">Explanation</span></span>  
 <span data-ttu-id="32e6d-119">El sistema ENTSSO no verifica la identidad del cliente durante su suplantación.</span><span class="sxs-lookup"><span data-stu-id="32e6d-119">Impersonating the client is something the ENTSSO System does to verify the client’s identity.</span></span> <span data-ttu-id="32e6d-120">Si el sistema no puede suplantar un cliente, puede deberse a una de las tres causas siguientes:</span><span class="sxs-lookup"><span data-stu-id="32e6d-120">When the system is unable to impersonate a client, one of three things may have occurred.</span></span> <span data-ttu-id="32e6d-121">el cliente puede estar intentando realizar una actividad habitual, el cliente puede estar intentando infiltrarse en la seguridad del sistema o la aplicación cliente pude estar diseñada para bloquear la suplantación.</span><span class="sxs-lookup"><span data-stu-id="32e6d-121">The client may be attempting to perform an usual activity, the client may be attempting to infiltrate system security, or the client application may have been designed to block impersonation.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="32e6d-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="32e6d-122">User Action</span></span>  
 <span data-ttu-id="32e6d-123">Busque la aplicación cliente, determine qué está intentando realizar y si está o no bloqueando la suplantación.</span><span class="sxs-lookup"><span data-stu-id="32e6d-123">Locate the client application and determine what it is attempting to do, and whether or not it is blocking impersonation.</span></span>