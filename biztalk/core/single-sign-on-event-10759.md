---
title: "Inicio de sesión único: Evento 10759 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5347f3d6-d31a-4c00-a64c-c0b0f680de88
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81ff42b71499df5848a55848b3dc1067adb830bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10759"></a><span data-ttu-id="888fa-102">Inicio de sesión único: Evento 10759</span><span class="sxs-lookup"><span data-stu-id="888fa-102">Single Sign-On: Event 10759</span></span>
## <a name="details"></a><span data-ttu-id="888fa-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="888fa-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="888fa-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="888fa-104">Product Name</span></span>|<span data-ttu-id="888fa-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="888fa-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="888fa-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="888fa-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="888fa-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="888fa-107">Event ID</span></span>|<span data-ttu-id="888fa-108">10759</span><span class="sxs-lookup"><span data-stu-id="888fa-108">10759</span></span>|  
|<span data-ttu-id="888fa-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="888fa-109">Event Source</span></span>|<span data-ttu-id="888fa-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="888fa-110">ENTSSO</span></span>|  
|<span data-ttu-id="888fa-111">Componente</span><span class="sxs-lookup"><span data-stu-id="888fa-111">Component</span></span>|<span data-ttu-id="888fa-112">N/D</span><span class="sxs-lookup"><span data-stu-id="888fa-112">N/A</span></span>|  
|<span data-ttu-id="888fa-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="888fa-113">Symbolic Name</span></span>|<span data-ttu-id="888fa-114">ENTSSO_E_BACKUP_RESTORE_FAILED_MEDIA</span><span class="sxs-lookup"><span data-stu-id="888fa-114">ENTSSO_E_BACKUP_RESTORE_FAILED_MEDIA</span></span>|  
|<span data-ttu-id="888fa-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="888fa-115">Message Text</span></span>|<span data-ttu-id="888fa-116">El archivo especificado para copia de seguridad o restauración de secretos principales debe estar en un sistema de archivos NTFS o en un medio extraíble.</span><span class="sxs-lookup"><span data-stu-id="888fa-116">The file specified for backup or restore of the master secrets must be on an NTFS file system or removable media.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="888fa-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="888fa-117">Explanation</span></span>  
 <span data-ttu-id="888fa-118">Sólo se pueden proteger los sistemas de archivos NTFS o los medios extraíbles.</span><span class="sxs-lookup"><span data-stu-id="888fa-118">Only NTFS file systems or removable media can be secured.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="888fa-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="888fa-119">User Action</span></span>  
 <span data-ttu-id="888fa-120">Para realizar la copia de seguridad del secreto principal, cambie a un sistema de archivos NTFS o a un medio extraíble.</span><span class="sxs-lookup"><span data-stu-id="888fa-120">Switch to either an NTFS file system of removable media to back up the master secret.</span></span>