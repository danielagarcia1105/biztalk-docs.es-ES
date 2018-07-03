---
title: 'De sesión único: Evento 10561 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 770e6fc1-0854-4555-8f2a-5f199e3aaca7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 053b17fcb940383d58110378710aeb6bc8d3fbe6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992503"
---
# <a name="single-sign-on-event-10561"></a><span data-ttu-id="8d52b-102">De sesión único: Evento 10561</span><span class="sxs-lookup"><span data-stu-id="8d52b-102">Single Sign-On: Event 10561</span></span>
## <a name="details"></a><span data-ttu-id="8d52b-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="8d52b-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                 |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="8d52b-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="8d52b-104">Product Name</span></span>   |                                                                                                    <span data-ttu-id="8d52b-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="8d52b-105">Enterprise Single Sign-On</span></span>                                                                                                    |
| <span data-ttu-id="8d52b-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="8d52b-106">Product Version</span></span> |                                                                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                    |
|    <span data-ttu-id="8d52b-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="8d52b-107">Event ID</span></span>     |                                                                                                              <span data-ttu-id="8d52b-108">10561</span><span class="sxs-lookup"><span data-stu-id="8d52b-108">10561</span></span>                                                                                                              |
|  <span data-ttu-id="8d52b-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="8d52b-109">Event Source</span></span>   |                                                                                                             <span data-ttu-id="8d52b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="8d52b-110">ENTSSO</span></span>                                                                                                              |
|    <span data-ttu-id="8d52b-111">Componente</span><span class="sxs-lookup"><span data-stu-id="8d52b-111">Component</span></span>    |                                                                                                               <span data-ttu-id="8d52b-112">N/D</span><span class="sxs-lookup"><span data-stu-id="8d52b-112">N/A</span></span>                                                                                                               |
|  <span data-ttu-id="8d52b-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="8d52b-113">Symbolic Name</span></span>  |                                                                                                  <span data-ttu-id="8d52b-114">SSO_ERROR_BACKUP_FAILED_MEDIA</span><span class="sxs-lookup"><span data-stu-id="8d52b-114">SSO_ERROR_BACKUP_FAILED_MEDIA</span></span>                                                                                                  |
|  <span data-ttu-id="8d52b-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="8d52b-115">Message Text</span></span>   | <span data-ttu-id="8d52b-116">El archivo especificado para copia de seguridad de secretos principales debe estar en un sistema de archivos NTFS o en un medio extraíble.%r</span><span class="sxs-lookup"><span data-stu-id="8d52b-116">The file specified for backup of the master secrets must be on an NTFS file system or removable media.%r</span></span><br /><br /> <span data-ttu-id="8d52b-117">Nombre de archivo: %1 %r</span><span class="sxs-lookup"><span data-stu-id="8d52b-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="8d52b-118">Usuario cliente: %2 %r</span><span class="sxs-lookup"><span data-stu-id="8d52b-118">Client User: %2%r</span></span><br /><br /> <span data-ttu-id="8d52b-119">Equipo cliente: %3 %r</span><span class="sxs-lookup"><span data-stu-id="8d52b-119">Client Computer: %3%r</span></span><br /><br /> <span data-ttu-id="8d52b-120">Código de error: %4</span><span class="sxs-lookup"><span data-stu-id="8d52b-120">Error Code: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="8d52b-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="8d52b-121">Explanation</span></span>  
 <span data-ttu-id="8d52b-122">Se intentó realizar una copia de seguridad mediante un medio no válido, como un archivo FAT.</span><span class="sxs-lookup"><span data-stu-id="8d52b-122">A backup was attempted using an invalid media, such as a FAT file.</span></span> <span data-ttu-id="8d52b-123">El archivo especificado para copia de seguridad de secretos principales debe estar en un sistema de archivos NTFS o en un medio extraíble.</span><span class="sxs-lookup"><span data-stu-id="8d52b-123">The file specified for backup of the master secrets must be on an NTFS file system or removable media.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8d52b-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="8d52b-124">User Action</span></span>  
 <span data-ttu-id="8d52b-125">Compruebe el formato de medio y asegúrese de que sea NTFS o extraíble.</span><span class="sxs-lookup"><span data-stu-id="8d52b-125">Check the media format and make sure it is NTFS or removable.</span></span>