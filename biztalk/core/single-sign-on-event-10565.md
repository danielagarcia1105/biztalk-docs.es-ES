---
title: 'De sesión único: Evento 10565 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d279491-dc0d-44c4-a77e-a67498a3481d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d31b639853b845169c3360ec6367aee120a266d1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008005"
---
# <a name="single-sign-on-event-10565"></a><span data-ttu-id="c36dd-102">De sesión único: Evento 10565</span><span class="sxs-lookup"><span data-stu-id="c36dd-102">Single Sign-On: Event 10565</span></span>
## <a name="details"></a><span data-ttu-id="c36dd-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="c36dd-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="c36dd-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="c36dd-104">Product Name</span></span>   |                                                                                           <span data-ttu-id="c36dd-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="c36dd-105">Enterprise Single Sign-On</span></span>                                                                                           |
| <span data-ttu-id="c36dd-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="c36dd-106">Product Version</span></span> |                                                                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                           |
|    <span data-ttu-id="c36dd-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="c36dd-107">Event ID</span></span>     |                                                                                                     <span data-ttu-id="c36dd-108">10565</span><span class="sxs-lookup"><span data-stu-id="c36dd-108">10565</span></span>                                                                                                     |
|  <span data-ttu-id="c36dd-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="c36dd-109">Event Source</span></span>   |                                                                                                    <span data-ttu-id="c36dd-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c36dd-110">ENTSSO</span></span>                                                                                                     |
|    <span data-ttu-id="c36dd-111">Componente</span><span class="sxs-lookup"><span data-stu-id="c36dd-111">Component</span></span>    |                                                                                                      <span data-ttu-id="c36dd-112">N/D</span><span class="sxs-lookup"><span data-stu-id="c36dd-112">N/A</span></span>                                                                                                      |
|  <span data-ttu-id="c36dd-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="c36dd-113">Symbolic Name</span></span>  |                                                                                       <span data-ttu-id="c36dd-114">SSO_ERROR_SECRET_VALIDATE_FAILED</span><span class="sxs-lookup"><span data-stu-id="c36dd-114">SSO_ERROR_SECRET_VALIDATE_FAILED</span></span>                                                                                        |
|  <span data-ttu-id="c36dd-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="c36dd-115">Message Text</span></span>   | <span data-ttu-id="c36dd-116">No se pudo cargar el secreto desde el Registro.</span><span class="sxs-lookup"><span data-stu-id="c36dd-116">The secret could not be loaded from the registry.</span></span> <span data-ttu-id="c36dd-117">Es posible que se haya cambiado la cuenta de servicio para el servicio SSO o que el secreto esté dañado.</span><span class="sxs-lookup"><span data-stu-id="c36dd-117">The service account for the SSO service may have been changed or the secret may be corrupted.</span></span> <span data-ttu-id="c36dd-118">Restaure el secreto desde el archivo de copia de seguridad.%r</span><span class="sxs-lookup"><span data-stu-id="c36dd-118">Restore the secret from a backup file.%r</span></span><br /><br /> <span data-ttu-id="c36dd-119">MSID: %1</span><span class="sxs-lookup"><span data-stu-id="c36dd-119">MSID: %1</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="c36dd-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="c36dd-120">Explanation</span></span>  
 <span data-ttu-id="c36dd-121">Es probable que un administrador del sistema haya cambiado la cuenta del servicio SSO, lo que imposibilita el descifrado.</span><span class="sxs-lookup"><span data-stu-id="c36dd-121">It is likely that an administrator in the system has changed the SSO Service account, making decryption impossible.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c36dd-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="c36dd-122">User Action</span></span>  
 <span data-ttu-id="c36dd-123">Busque a la persona que cambió la cuenta del servicio SSO y, después, restaure el secreto desde el archivo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c36dd-123">Find the person who changed the SSO Service account, and then restore the secret from a backup file.</span></span> <span data-ttu-id="c36dd-124">Para obtener más información acerca de cómo restaurar el secreto, consulte [administrar el secreto principal](../core/managing-the-master-secret.md).</span><span class="sxs-lookup"><span data-stu-id="c36dd-124">For more information on restoring the secret, see [Managing the Master Secret](../core/managing-the-master-secret.md).</span></span>