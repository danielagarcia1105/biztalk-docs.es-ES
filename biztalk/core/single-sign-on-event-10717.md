---
title: 'De sesión único: Evento 10717 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14691e0f-a399-4b4d-9dd5-516bf8d3a167
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7beabfc76ce1c5ab72ac577be2dfbe549b35a4a7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004533"
---
# <a name="single-sign-on-event-10717"></a><span data-ttu-id="b9717-102">De sesión único: Evento 10717</span><span class="sxs-lookup"><span data-stu-id="b9717-102">Single Sign-On: Event 10717</span></span>
## <a name="details"></a><span data-ttu-id="b9717-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="b9717-103">Details</span></span>  

|                 |                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b9717-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="b9717-104">Product Name</span></span>   |                                                            <span data-ttu-id="b9717-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="b9717-105">Enterprise Single Sign-On</span></span>                                                             |
| <span data-ttu-id="b9717-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="b9717-106">Product Version</span></span> |                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                            |
|    <span data-ttu-id="b9717-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="b9717-107">Event ID</span></span>     |                                                                      <span data-ttu-id="b9717-108">10717</span><span class="sxs-lookup"><span data-stu-id="b9717-108">10717</span></span>                                                                       |
|  <span data-ttu-id="b9717-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="b9717-109">Event Source</span></span>   |                                                                      <span data-ttu-id="b9717-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b9717-110">ENTSSO</span></span>                                                                      |
|    <span data-ttu-id="b9717-111">Componente</span><span class="sxs-lookup"><span data-stu-id="b9717-111">Component</span></span>    |                                                                       <span data-ttu-id="b9717-112">N\D</span><span class="sxs-lookup"><span data-stu-id="b9717-112">N\A</span></span>                                                                        |
|  <span data-ttu-id="b9717-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b9717-113">Symbolic Name</span></span>  |                                                         <span data-ttu-id="b9717-114">SSO_ERROR_NEW_REPLAY_DIR_FAILED</span><span class="sxs-lookup"><span data-stu-id="b9717-114">SSO_ERROR_NEW_REPLAY_DIR_FAILED</span></span>                                                          |
|  <span data-ttu-id="b9717-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b9717-115">Message Text</span></span>   | <span data-ttu-id="b9717-116">No se pudo crear el directorio de archivos de reproducción.%r</span><span class="sxs-lookup"><span data-stu-id="b9717-116">Failed to create the replay files directory.%r</span></span><br /><br /> <span data-ttu-id="b9717-117">Usuario cliente: %1 %r</span><span class="sxs-lookup"><span data-stu-id="b9717-117">Client User: %1%r</span></span><br /><br /> <span data-ttu-id="b9717-118">Directorio de archivos de reproducción: %2 %r</span><span class="sxs-lookup"><span data-stu-id="b9717-118">Replay Files Directory: %2%r</span></span><br /><br /> <span data-ttu-id="b9717-119">Código de error: %3</span><span class="sxs-lookup"><span data-stu-id="b9717-119">Error Code: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="b9717-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="b9717-120">Explanation</span></span>  
 <span data-ttu-id="b9717-121">Este evento de error indica que no se pudo crear el directorio de archivos de reproducción.</span><span class="sxs-lookup"><span data-stu-id="b9717-121">This Error event indicates that a replay files directory could not be created.</span></span>  

 <span data-ttu-id="b9717-122">Cuando el servicio SSO recibe cambios de contraseña provenientes de un adaptador de sincronización de contraseñas, tales cambios se almacenan en la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="b9717-122">When password changes are received by the SSO service from a password sync adapter, they are stored in the SSO database.</span></span> <span data-ttu-id="b9717-123">Si esta base de datos no está disponible temporalmente, los cambios de contraseña se almacenan de forma local en archivos de reproducción.</span><span class="sxs-lookup"><span data-stu-id="b9717-123">If the SSO database is temporarily unavailable, the password changes are stored locally in replay files.</span></span> <span data-ttu-id="b9717-124">Los archivos de reproducción se almacenan en el directorio de archivos de reproducción.</span><span class="sxs-lookup"><span data-stu-id="b9717-124">Replay files are stored in the replay files directory.</span></span>  

## <a name="user-action"></a><span data-ttu-id="b9717-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b9717-125">User Action</span></span>  
 <span data-ttu-id="b9717-126">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b9717-126">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="b9717-127">Compruebe el directorio de archivos de reproducción. Si no existe uno, intente crearlo de forma manual mediante la misma cuenta de servicio que el servicio SSO.</span><span class="sxs-lookup"><span data-stu-id="b9717-127">Check the replay files directory, if one does not exist, attempt to create it manually using the same service account as the SSO service.</span></span> <span data-ttu-id="b9717-128">Si no puede crear un directorio de archivos de reproducción mediante la misma cuenta que el servicio SSO, compruebe los permisos de esa cuenta.</span><span class="sxs-lookup"><span data-stu-id="b9717-128">If you cannot create a replay files directory using the same account as the SSO service, check permissions for that account.</span></span>  

  <span data-ttu-id="b9717-129">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b9717-129">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="b9717-130">Cómo configurar la sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="b9717-130">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="b9717-131">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="b9717-131">Password Synchronization</span></span>](../core/password-synchronization2.md)
