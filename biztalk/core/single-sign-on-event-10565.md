---
title: 'Inicio de sesión único: Evento 10565 | Documentos de Microsoft'
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
ms.openlocfilehash: 9567421210689d8615cf88e7fbd6493ef5749d02
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271036"
---
# <a name="single-sign-on-event-10565"></a><span data-ttu-id="6fc05-102">Inicio de sesión único: Evento 10565</span><span class="sxs-lookup"><span data-stu-id="6fc05-102">Single Sign-On: Event 10565</span></span>
## <a name="details"></a><span data-ttu-id="6fc05-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="6fc05-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6fc05-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="6fc05-104">Product Name</span></span>|<span data-ttu-id="6fc05-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="6fc05-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="6fc05-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="6fc05-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="6fc05-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="6fc05-107">Event ID</span></span>|<span data-ttu-id="6fc05-108">10565</span><span class="sxs-lookup"><span data-stu-id="6fc05-108">10565</span></span>|  
|<span data-ttu-id="6fc05-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="6fc05-109">Event Source</span></span>|<span data-ttu-id="6fc05-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="6fc05-110">ENTSSO</span></span>|  
|<span data-ttu-id="6fc05-111">Componente</span><span class="sxs-lookup"><span data-stu-id="6fc05-111">Component</span></span>|<span data-ttu-id="6fc05-112">N/D</span><span class="sxs-lookup"><span data-stu-id="6fc05-112">N/A</span></span>|  
|<span data-ttu-id="6fc05-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="6fc05-113">Symbolic Name</span></span>|<span data-ttu-id="6fc05-114">SSO_ERROR_SECRET_VALIDATE_FAILED</span><span class="sxs-lookup"><span data-stu-id="6fc05-114">SSO_ERROR_SECRET_VALIDATE_FAILED</span></span>|  
|<span data-ttu-id="6fc05-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="6fc05-115">Message Text</span></span>|<span data-ttu-id="6fc05-116">No se pudo cargar el secreto desde el Registro.</span><span class="sxs-lookup"><span data-stu-id="6fc05-116">The secret could not be loaded from the registry.</span></span> <span data-ttu-id="6fc05-117">Es posible que se haya cambiado la cuenta de servicio para el servicio SSO o que el secreto esté dañado.</span><span class="sxs-lookup"><span data-stu-id="6fc05-117">The service account for the SSO service may have been changed or the secret may be corrupted.</span></span> <span data-ttu-id="6fc05-118">Restaure el secreto desde el archivo de copia de seguridad.%r</span><span class="sxs-lookup"><span data-stu-id="6fc05-118">Restore the secret from a backup file.%r</span></span><br /><br /> <span data-ttu-id="6fc05-119">MSID: %1</span><span class="sxs-lookup"><span data-stu-id="6fc05-119">MSID: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6fc05-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="6fc05-120">Explanation</span></span>  
 <span data-ttu-id="6fc05-121">Es probable que un administrador del sistema haya cambiado la cuenta del servicio SSO, lo que imposibilita el descifrado.</span><span class="sxs-lookup"><span data-stu-id="6fc05-121">It is likely that an administrator in the system has changed the SSO Service account, making decryption impossible.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6fc05-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="6fc05-122">User Action</span></span>  
 <span data-ttu-id="6fc05-123">Busque a la persona que cambió la cuenta del servicio SSO y, después, restaure el secreto desde el archivo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6fc05-123">Find the person who changed the SSO Service account, and then restore the secret from a backup file.</span></span> <span data-ttu-id="6fc05-124">Para obtener más información acerca de cómo restaurar el secreto, consulte [administrar el secreto principal](../core/managing-the-master-secret.md).</span><span class="sxs-lookup"><span data-stu-id="6fc05-124">For more information on restoring the secret, see [Managing the Master Secret](../core/managing-the-master-secret.md).</span></span>