---
title: 'De sesión único: Evento 10820 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2da93a2c-d00d-4ca0-a0cf-453cee4bf3c3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78b566c4dfe4437017b743228c9bae2631c79a00
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011661"
---
# <a name="single-sign-on-event-10820"></a><span data-ttu-id="1b77d-102">De sesión único: Evento 10820</span><span class="sxs-lookup"><span data-stu-id="1b77d-102">Single Sign-On: Event 10820</span></span>
## <a name="details"></a><span data-ttu-id="1b77d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="1b77d-103">Details</span></span>  
  
|                 |                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------|
|  <span data-ttu-id="1b77d-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="1b77d-104">Product Name</span></span>   |                                  <span data-ttu-id="1b77d-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="1b77d-105">Enterprise Single Sign-On</span></span>                                   |
| <span data-ttu-id="1b77d-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="1b77d-106">Product Version</span></span> |                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                  |
|    <span data-ttu-id="1b77d-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="1b77d-107">Event ID</span></span>     |                                            <span data-ttu-id="1b77d-108">10820</span><span class="sxs-lookup"><span data-stu-id="1b77d-108">10820</span></span>                                             |
|  <span data-ttu-id="1b77d-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="1b77d-109">Event Source</span></span>   |                                            <span data-ttu-id="1b77d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1b77d-110">ENTSSO</span></span>                                            |
|    <span data-ttu-id="1b77d-111">Componente</span><span class="sxs-lookup"><span data-stu-id="1b77d-111">Component</span></span>    |                                             <span data-ttu-id="1b77d-112">N/D</span><span class="sxs-lookup"><span data-stu-id="1b77d-112">N/A</span></span>                                              |
|  <span data-ttu-id="1b77d-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="1b77d-113">Symbolic Name</span></span>  |                                <span data-ttu-id="1b77d-114">ENTSSO_E_REQUIRE_OLD_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="1b77d-114">ENTSSO_E_REQUIRE_OLD_PASSWORD</span></span>                                 |
|  <span data-ttu-id="1b77d-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="1b77d-115">Message Text</span></span>   | <span data-ttu-id="1b77d-116">Al cambiar la contraseña de una cuenta externa, el adaptador debe proporcionar la contraseña anterior.</span><span class="sxs-lookup"><span data-stu-id="1b77d-116">When changing the password for an external account the adapter must supply the old password.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="1b77d-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="1b77d-117">Explanation</span></span>  
 <span data-ttu-id="1b77d-118">Esta aplicación está configurada para que el adaptador de sincronización de contraseñas deba proporcionar la contraseña anterior.</span><span class="sxs-lookup"><span data-stu-id="1b77d-118">This application is configured in such a way that the password sync adapter is required to supply the old password.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1b77d-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="1b77d-119">User Action</span></span>  
 <span data-ttu-id="1b77d-120">Compruebe la configuración del adaptador de sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="1b77d-120">Check the configuration of your password sync adapter.</span></span>