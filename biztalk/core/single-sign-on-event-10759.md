---
title: 'De sesión único: Evento 10759 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5347f3d6-d31a-4c00-a64c-c0b0f680de88
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 177b5d1383a583ddc33a67a7290bff98b1d13364
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967589"
---
# <a name="single-sign-on-event-10759"></a><span data-ttu-id="fd795-102">De sesión único: Evento 10759</span><span class="sxs-lookup"><span data-stu-id="fd795-102">Single Sign-On: Event 10759</span></span>
## <a name="details"></a><span data-ttu-id="fd795-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="fd795-103">Details</span></span>  
  
|                 |                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="fd795-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="fd795-104">Product Name</span></span>   |                                             <span data-ttu-id="fd795-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="fd795-105">Enterprise Single Sign-On</span></span>                                             |
| <span data-ttu-id="fd795-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="fd795-106">Product Version</span></span> |                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                             |
|    <span data-ttu-id="fd795-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="fd795-107">Event ID</span></span>     |                                                       <span data-ttu-id="fd795-108">10759</span><span class="sxs-lookup"><span data-stu-id="fd795-108">10759</span></span>                                                       |
|  <span data-ttu-id="fd795-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="fd795-109">Event Source</span></span>   |                                                      <span data-ttu-id="fd795-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="fd795-110">ENTSSO</span></span>                                                       |
|    <span data-ttu-id="fd795-111">Componente</span><span class="sxs-lookup"><span data-stu-id="fd795-111">Component</span></span>    |                                                        <span data-ttu-id="fd795-112">N/D</span><span class="sxs-lookup"><span data-stu-id="fd795-112">N/A</span></span>                                                        |
|  <span data-ttu-id="fd795-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="fd795-113">Symbolic Name</span></span>  |                                       <span data-ttu-id="fd795-114">ENTSSO_E_BACKUP_RESTORE_FAILED_MEDIA</span><span class="sxs-lookup"><span data-stu-id="fd795-114">ENTSSO_E_BACKUP_RESTORE_FAILED_MEDIA</span></span>                                        |
|  <span data-ttu-id="fd795-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="fd795-115">Message Text</span></span>   | <span data-ttu-id="fd795-116">El archivo especificado para copia de seguridad o restauración de secretos principales debe estar en un sistema de archivos NTFS o en un medio extraíble.</span><span class="sxs-lookup"><span data-stu-id="fd795-116">The file specified for backup or restore of the master secrets must be on an NTFS file system or removable media.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="fd795-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="fd795-117">Explanation</span></span>  
 <span data-ttu-id="fd795-118">Sólo se pueden proteger los sistemas de archivos NTFS o los medios extraíbles.</span><span class="sxs-lookup"><span data-stu-id="fd795-118">Only NTFS file systems or removable media can be secured.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fd795-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="fd795-119">User Action</span></span>  
 <span data-ttu-id="fd795-120">Para realizar la copia de seguridad del secreto principal, cambie a un sistema de archivos NTFS o a un medio extraíble.</span><span class="sxs-lookup"><span data-stu-id="fd795-120">Switch to either an NTFS file system of removable media to back up the master secret.</span></span>