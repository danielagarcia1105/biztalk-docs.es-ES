---
title: "Inicio de sesión único: Evento 10564 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e523c97a-608e-4bf4-8747-cfa0cce10acf
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7268b877a59fcd4e993a2c9009d48d73e5db9ac8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10564"></a><span data-ttu-id="41cf0-102">Inicio de sesión único: Evento 10564</span><span class="sxs-lookup"><span data-stu-id="41cf0-102">Single Sign-On: Event 10564</span></span>
## <a name="details"></a><span data-ttu-id="41cf0-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="41cf0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="41cf0-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="41cf0-104">Product Name</span></span>|<span data-ttu-id="41cf0-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="41cf0-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="41cf0-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="41cf0-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="41cf0-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="41cf0-107">Event ID</span></span>|<span data-ttu-id="41cf0-108">10564</span><span class="sxs-lookup"><span data-stu-id="41cf0-108">10564</span></span>|  
|<span data-ttu-id="41cf0-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="41cf0-109">Event Source</span></span>|<span data-ttu-id="41cf0-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="41cf0-110">ENTSSO</span></span>|  
|<span data-ttu-id="41cf0-111">Componente</span><span class="sxs-lookup"><span data-stu-id="41cf0-111">Component</span></span>|<span data-ttu-id="41cf0-112">N/D</span><span class="sxs-lookup"><span data-stu-id="41cf0-112">N/A</span></span>|  
|<span data-ttu-id="41cf0-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="41cf0-113">Symbolic Name</span></span>|<span data-ttu-id="41cf0-114">SSO_ERROR_BACKUP_FILE_INCORRECT_FORMAT</span><span class="sxs-lookup"><span data-stu-id="41cf0-114">SSO_ERROR_BACKUP_FILE_INCORRECT_FORMAT</span></span>|  
|<span data-ttu-id="41cf0-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="41cf0-115">Message Text</span></span>|<span data-ttu-id="41cf0-116">Formato incorrecto de archivo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="41cf0-116">The backup file does not have the correct format.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="41cf0-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="41cf0-117">Explanation</span></span>  
 <span data-ttu-id="41cf0-118">Formato incorrecto de archivo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="41cf0-118">The backup file does not have the correct format.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="41cf0-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="41cf0-119">User Action</span></span>  
 <span data-ttu-id="41cf0-120">Compruebe si tiene el archivo y la ubicación correctos.</span><span class="sxs-lookup"><span data-stu-id="41cf0-120">Check that you have the correct file and location.</span></span> <span data-ttu-id="41cf0-121">Además, debe confirmar que no existen otros archivos en esa carpeta con la extensión .BAK, dado que el sistema ENTSSO puede confundirlos con el archivo de copia de seguridad real.</span><span class="sxs-lookup"><span data-stu-id="41cf0-121">You should also confirm that there are no other files in that folder with the .BAK extension, as the ENTSSO system may confuse them with the actual backup file.</span></span>