---
title: 'De sesión único: Evento 10851 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 582b92bf-2833-47cd-b685-1245e870d81d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15121c1d7829f04bd9c106ed71da391d401ae564
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987237"
---
# <a name="single-sign-on-event-10851"></a><span data-ttu-id="c6a91-102">De sesión único: Evento 10851</span><span class="sxs-lookup"><span data-stu-id="c6a91-102">Single Sign-On: Event 10851</span></span>
## <a name="details"></a><span data-ttu-id="c6a91-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="c6a91-103">Details</span></span>  
  
|                 |                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="c6a91-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="c6a91-104">Product Name</span></span>   |                                             <span data-ttu-id="c6a91-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="c6a91-105">Enterprise Single Sign-On</span></span>                                             |
| <span data-ttu-id="c6a91-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="c6a91-106">Product Version</span></span> |                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                             |
|    <span data-ttu-id="c6a91-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="c6a91-107">Event ID</span></span>     |                                                       <span data-ttu-id="c6a91-108">10851</span><span class="sxs-lookup"><span data-stu-id="c6a91-108">10851</span></span>                                                       |
|  <span data-ttu-id="c6a91-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="c6a91-109">Event Source</span></span>   |                                                      <span data-ttu-id="c6a91-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c6a91-110">ENTSSO</span></span>                                                       |
|    <span data-ttu-id="c6a91-111">Componente</span><span class="sxs-lookup"><span data-stu-id="c6a91-111">Component</span></span>    |                                                        <span data-ttu-id="c6a91-112">N/D</span><span class="sxs-lookup"><span data-stu-id="c6a91-112">N/A</span></span>                                                        |
|  <span data-ttu-id="c6a91-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="c6a91-113">Symbolic Name</span></span>  |                                     <span data-ttu-id="c6a91-114">ENTSSO_E_PSADMIN_NO_DIRECT_PASSWORD_SYNC</span><span class="sxs-lookup"><span data-stu-id="c6a91-114">ENTSSO_E_PSADMIN_NO_DIRECT_PASSWORD_SYNC</span></span>                                      |
|  <span data-ttu-id="c6a91-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="c6a91-115">Message Text</span></span>   | <span data-ttu-id="c6a91-116">No se puede asignar la aplicación a un adaptador de sincronización de contraseñas porque tiene establecido el marcador "sincronización directa de contraseñas".</span><span class="sxs-lookup"><span data-stu-id="c6a91-116">The application cannot be assigned to a password sync adapter because it has the 'direct password sync' flag set.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="c6a91-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="c6a91-117">Explanation</span></span>  
 <span data-ttu-id="c6a91-118">Una aplicación no puede usar al mismo tiempo la sincronización directa de contraseñas y un adaptador de sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="c6a91-118">An application cannot use both direct password sync and a password sync adapter.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c6a91-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="c6a91-119">User Action</span></span>  
 <span data-ttu-id="c6a91-120">Revise la aplicación y decida si debe o no tener sincronización directa de contraseñas. Si es así, deje el marcador establecido tal como está y no intente asignar la aplicación a un adaptador de sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="c6a91-120">Review your application and decide whether or not it should have direct password sync. If it should, leave the flag set as it is and do not attempt to assign the application to a password sync adapter.</span></span> <span data-ttu-id="c6a91-121">De lo contrario, desactive el marcador y asigne la aplicación a un adaptador de sincronización de contraseñas según corresponda.</span><span class="sxs-lookup"><span data-stu-id="c6a91-121">If it should not, then turn the flag off and assign the application to a password sync adapter as appropriate.</span></span>