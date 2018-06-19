---
title: 'Inicio de sesión único: Evento 11061 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52fb18e2-4482-4cdb-b8ed-d579a95acd7c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e86ad25248952697e27fc732ddead6732065acf7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277476"
---
# <a name="single-sign-on-event-11061"></a><span data-ttu-id="ffc83-102">Inicio de sesión único: Evento 11061</span><span class="sxs-lookup"><span data-stu-id="ffc83-102">Single Sign-On: Event 11061</span></span>
## <a name="details"></a><span data-ttu-id="ffc83-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ffc83-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ffc83-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ffc83-104">Product Name</span></span>|<span data-ttu-id="ffc83-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="ffc83-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="ffc83-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ffc83-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="ffc83-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ffc83-107">Event ID</span></span>|<span data-ttu-id="ffc83-108">11061</span><span class="sxs-lookup"><span data-stu-id="ffc83-108">11061</span></span>|  
|<span data-ttu-id="ffc83-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ffc83-109">Event Source</span></span>|<span data-ttu-id="ffc83-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ffc83-110">ENTSSO</span></span>|  
|<span data-ttu-id="ffc83-111">Componente</span><span class="sxs-lookup"><span data-stu-id="ffc83-111">Component</span></span>|<span data-ttu-id="ffc83-112">N/D</span><span class="sxs-lookup"><span data-stu-id="ffc83-112">N/A</span></span>|  
|<span data-ttu-id="ffc83-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ffc83-113">Symbolic Name</span></span>|<span data-ttu-id="ffc83-114">SSO_WARN_BAD_PASSWORD_FILTER</span><span class="sxs-lookup"><span data-stu-id="ffc83-114">SSO_WARN_BAD_PASSWORD_FILTER</span></span>|  
|<span data-ttu-id="ffc83-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ffc83-115">Message Text</span></span>|<span data-ttu-id="ffc83-116">Cadena de filtro de contraseña no válida.</span><span class="sxs-lookup"><span data-stu-id="ffc83-116">The password filter string is not valid.</span></span> <span data-ttu-id="ffc83-117">No se usará filtro de contraseña.%r</span><span class="sxs-lookup"><span data-stu-id="ffc83-117">No password filter will be used.%r</span></span><br /><br /> <span data-ttu-id="ffc83-118">Nombre de la aplicación: %1 %r</span><span class="sxs-lookup"><span data-stu-id="ffc83-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="ffc83-119">Cadena de filtro de contraseña: %2 %r</span><span class="sxs-lookup"><span data-stu-id="ffc83-119">Password Filter String: %2%r</span></span><br /><br /> <span data-ttu-id="ffc83-120">Número de Tokens procesados: %3 %r</span><span class="sxs-lookup"><span data-stu-id="ffc83-120">Number Of Tokens Processed: %3%r</span></span><br /><br /> <span data-ttu-id="ffc83-121">Datos adicionales: %4 %r</span><span class="sxs-lookup"><span data-stu-id="ffc83-121">Additional Data: %4%r</span></span><br /><br /> <span data-ttu-id="ffc83-122">Código de error: %5</span><span class="sxs-lookup"><span data-stu-id="ffc83-122">Error Code: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ffc83-123">Explicación</span><span class="sxs-lookup"><span data-stu-id="ffc83-123">Explanation</span></span>  
 <span data-ttu-id="ffc83-124">Se creó manualmente un filtro de contraseña no válido.</span><span class="sxs-lookup"><span data-stu-id="ffc83-124">An invalid password filter has been created manually.</span></span> <span data-ttu-id="ffc83-125">En algún momento de este proceso se generó un error (consulte la cadena de filtro de contraseña en el texto de la advertencia para conocer la ubicación del error).</span><span class="sxs-lookup"><span data-stu-id="ffc83-125">At some point in this process an error was introduced (see Password Filter String in the warning text for the location of the error).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ffc83-126">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ffc83-126">User Action</span></span>  
 <span data-ttu-id="ffc83-127">Para crear el filtro de contraseñas mediante el Asistente para crear un filtro de contraseña, consulte [cómo usar filtros de contraseña](../core/how-to-use-password-filters.md).</span><span class="sxs-lookup"><span data-stu-id="ffc83-127">To create the Password Filter using the Create Password Filter Wizard, see [How to Use Password Filters](../core/how-to-use-password-filters.md).</span></span>