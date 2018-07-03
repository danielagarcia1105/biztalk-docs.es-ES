---
title: 'De sesión único: Evento 10718 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de075c59-8396-48d1-be55-79303f83f984
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 958753d50d15662cd138ea5460c121eefcac8a98
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004989"
---
# <a name="single-sign-on-event-10718"></a><span data-ttu-id="f7bec-102">De sesión único: Evento 10718</span><span class="sxs-lookup"><span data-stu-id="f7bec-102">Single Sign-On: Event 10718</span></span>
## <a name="details"></a><span data-ttu-id="f7bec-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="f7bec-103">Details</span></span>  

|                 |                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="f7bec-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="f7bec-104">Product Name</span></span>   |                                                                     <span data-ttu-id="f7bec-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="f7bec-105">Enterprise Single Sign-On</span></span>                                                                     |
| <span data-ttu-id="f7bec-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="f7bec-106">Product Version</span></span> |                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                     |
|    <span data-ttu-id="f7bec-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="f7bec-107">Event ID</span></span>     |                                                                               <span data-ttu-id="f7bec-108">10718</span><span class="sxs-lookup"><span data-stu-id="f7bec-108">10718</span></span>                                                                               |
|  <span data-ttu-id="f7bec-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="f7bec-109">Event Source</span></span>   |                                                                              <span data-ttu-id="f7bec-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f7bec-110">ENTSSO</span></span>                                                                               |
|    <span data-ttu-id="f7bec-111">Componente</span><span class="sxs-lookup"><span data-stu-id="f7bec-111">Component</span></span>    |                                                                                <span data-ttu-id="f7bec-112">N\D</span><span class="sxs-lookup"><span data-stu-id="f7bec-112">N\A</span></span>                                                                                |
|  <span data-ttu-id="f7bec-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="f7bec-113">Symbolic Name</span></span>  |                                                                <span data-ttu-id="f7bec-114">SSO_ERROR_REPLAY_INCORRECT_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="f7bec-114">SSO_ERROR_REPLAY_INCORRECT_ADAPTER</span></span>                                                                 |
|  <span data-ttu-id="f7bec-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="f7bec-115">Message Text</span></span>   | <span data-ttu-id="f7bec-116">El archivo de reproducción o progreso está dañado.%r</span><span class="sxs-lookup"><span data-stu-id="f7bec-116">Corruption was detected in the replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="f7bec-117">Nombre de archivo: %1 %r</span><span class="sxs-lookup"><span data-stu-id="f7bec-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="f7bec-118">Borrar el nombre de adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="f7bec-118">Clear Adapter Name: %2%r</span></span><br /><br /> <span data-ttu-id="f7bec-119">Nombre del adaptador puede descifrar: %3</span><span class="sxs-lookup"><span data-stu-id="f7bec-119">Decrypted Adapter Name: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="f7bec-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="f7bec-120">Explanation</span></span>  
 <span data-ttu-id="f7bec-121">Este evento de error indica que se detectó que el archivo de reproducción o progreso está dañado.</span><span class="sxs-lookup"><span data-stu-id="f7bec-121">This Error event indicates that corruption was detected in the replay or progress file.</span></span>  

 <span data-ttu-id="f7bec-122">El archivo de reproducción se almacena para un determinado adaptador de sincronización de contraseñas, de manera que puede reproducirse en ese adaptador específico.</span><span class="sxs-lookup"><span data-stu-id="f7bec-122">A replay file is stored for a particular password sync adapter so it can be played back as that particular adapter.</span></span> <span data-ttu-id="f7bec-123">El nombre de adaptador se almacena tanto sin cifrado como cifrado.</span><span class="sxs-lookup"><span data-stu-id="f7bec-123">The adapter name is stored in both clear and encrypted forms.</span></span> <span data-ttu-id="f7bec-124">El mensaje indica que cuando se descifró el archivo de reproducción para su reproducción, el nombre de adaptador descifrado no coincidió con el nombre de adaptador.</span><span class="sxs-lookup"><span data-stu-id="f7bec-124">This message indicates that when the replay file was decrypted for playback the decrypted adapter name did not match the adapter name.</span></span> <span data-ttu-id="f7bec-125">Esto puede indicar que el archivo de reproducción está dañado o que sufrió algún tipo de alteración.</span><span class="sxs-lookup"><span data-stu-id="f7bec-125">This can suggest that there has been some corruption or possible tampering with the replay file.</span></span>  

## <a name="user-action"></a><span data-ttu-id="f7bec-126">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="f7bec-126">User Action</span></span>  
 <span data-ttu-id="f7bec-127">Para resolver este error, realice una o varias de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="f7bec-127">To resolve this error, do one or more of the following:</span></span>  

- <span data-ttu-id="f7bec-128">Determine por qué el contenido del archivo de reproducción podría haberse modificado y consulte si existe una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f7bec-128">Determine why the contents of the replay file might have been modified, see if a backup exists.</span></span>  

- <span data-ttu-id="f7bec-129">Compruebe si se cambió el secreto principal de SSO o la cuenta de servicio SSO, esto podría afectar el comportamiento de cifrado.</span><span class="sxs-lookup"><span data-stu-id="f7bec-129">Check if the SSO master secret was changed or the SSO service account was changed, this could affect encryption behavior.</span></span>  

- <span data-ttu-id="f7bec-130">Elimine el archivo de reproducción.</span><span class="sxs-lookup"><span data-stu-id="f7bec-130">Delete the replay file.</span></span>  

  <span data-ttu-id="f7bec-131">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f7bec-131">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="f7bec-132">Cómo configurar la sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="f7bec-132">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="f7bec-133">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="f7bec-133">Password Synchronization</span></span>](../core/password-synchronization2.md)
