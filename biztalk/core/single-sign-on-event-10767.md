---
title: 'De sesión único: Evento 10767 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef5efc04-a0b5-4fc7-9d0e-f7aa9a9c413d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a14733abb624207704b304ef9718608c9df1c4bf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977341"
---
# <a name="single-sign-on-event-10767"></a><span data-ttu-id="dd2ba-102">De sesión único: Evento 10767</span><span class="sxs-lookup"><span data-stu-id="dd2ba-102">Single Sign-On: Event 10767</span></span>
## <a name="details"></a><span data-ttu-id="dd2ba-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="dd2ba-103">Details</span></span>  
  
|                 |                                                                                                                         |
|-----------------|-------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="dd2ba-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="dd2ba-104">Product Name</span></span>   |                                                <span data-ttu-id="dd2ba-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="dd2ba-105">Enterprise Single Sign-On</span></span>                                                |
| <span data-ttu-id="dd2ba-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="dd2ba-106">Product Version</span></span> |                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                |
|    <span data-ttu-id="dd2ba-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="dd2ba-107">Event ID</span></span>     |                                                          <span data-ttu-id="dd2ba-108">10767</span><span class="sxs-lookup"><span data-stu-id="dd2ba-108">10767</span></span>                                                          |
|  <span data-ttu-id="dd2ba-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="dd2ba-109">Event Source</span></span>   |                                                         <span data-ttu-id="dd2ba-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="dd2ba-110">ENTSSO</span></span>                                                          |
|    <span data-ttu-id="dd2ba-111">Componente</span><span class="sxs-lookup"><span data-stu-id="dd2ba-111">Component</span></span>    |                                                           <span data-ttu-id="dd2ba-112">N/D</span><span class="sxs-lookup"><span data-stu-id="dd2ba-112">N/A</span></span>                                                           |
|  <span data-ttu-id="dd2ba-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="dd2ba-113">Symbolic Name</span></span>  |                                                 <span data-ttu-id="dd2ba-114">ENTSSO_E_NO_SSO_SERVER</span><span class="sxs-lookup"><span data-stu-id="dd2ba-114">ENTSSO_E_NO_SSO_SERVER</span></span>                                                  |
|  <span data-ttu-id="dd2ba-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="dd2ba-115">Message Text</span></span>   | <span data-ttu-id="dd2ba-116">No se pudo establecer la conexión con el servidor de SSO ‘%1’.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-116">Could not contact the SSO server ‘%1’.</span></span> <span data-ttu-id="dd2ba-117">Compruebe si SSO está configurado y si el servicio SSO está en ejecución en ese servidor.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-117">Check that SSO is configured and that the SSO service is running on that server.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="dd2ba-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="dd2ba-118">Explanation</span></span>  
 <span data-ttu-id="dd2ba-119">El cliente de ENTSSO no puede establecer la conexión con el servidor de ENTSSO.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-119">The ENTSSO client is unable to contact the ENTSSO server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dd2ba-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="dd2ba-120">User Action</span></span>  
 <span data-ttu-id="dd2ba-121">Compruebe la conectividad de red y asegúrese de que el nombre de servidor esté escrito correctamente.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-121">Check network connectivity and make sure you spelled the server name correctly.</span></span>