---
title: 'De sesión único: Evento 11061 | Microsoft Docs'
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
ms.openlocfilehash: 1733e444ecdfdaf54b20beb2de6894ade3466f4c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011333"
---
# <a name="single-sign-on-event-11061"></a><span data-ttu-id="62d1f-102">De sesión único: Evento 11061</span><span class="sxs-lookup"><span data-stu-id="62d1f-102">Single Sign-On: Event 11061</span></span>
## <a name="details"></a><span data-ttu-id="62d1f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="62d1f-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="62d1f-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="62d1f-104">Product Name</span></span>   |                                                                                                                     <span data-ttu-id="62d1f-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="62d1f-105">Enterprise Single Sign-On</span></span>                                                                                                                     |
| <span data-ttu-id="62d1f-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="62d1f-106">Product Version</span></span> |                                                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                     |
|    <span data-ttu-id="62d1f-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="62d1f-107">Event ID</span></span>     |                                                                                                                               <span data-ttu-id="62d1f-108">11061</span><span class="sxs-lookup"><span data-stu-id="62d1f-108">11061</span></span>                                                                                                                               |
|  <span data-ttu-id="62d1f-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="62d1f-109">Event Source</span></span>   |                                                                                                                              <span data-ttu-id="62d1f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="62d1f-110">ENTSSO</span></span>                                                                                                                               |
|    <span data-ttu-id="62d1f-111">Componente</span><span class="sxs-lookup"><span data-stu-id="62d1f-111">Component</span></span>    |                                                                                                                                <span data-ttu-id="62d1f-112">N/D</span><span class="sxs-lookup"><span data-stu-id="62d1f-112">N/A</span></span>                                                                                                                                |
|  <span data-ttu-id="62d1f-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="62d1f-113">Symbolic Name</span></span>  |                                                                                                                   <span data-ttu-id="62d1f-114">SSO_WARN_BAD_PASSWORD_FILTER</span><span class="sxs-lookup"><span data-stu-id="62d1f-114">SSO_WARN_BAD_PASSWORD_FILTER</span></span>                                                                                                                    |
|  <span data-ttu-id="62d1f-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="62d1f-115">Message Text</span></span>   | <span data-ttu-id="62d1f-116">Cadena de filtro de contraseña no válida.</span><span class="sxs-lookup"><span data-stu-id="62d1f-116">The password filter string is not valid.</span></span> <span data-ttu-id="62d1f-117">No se usará filtro de contraseña.%r</span><span class="sxs-lookup"><span data-stu-id="62d1f-117">No password filter will be used.%r</span></span><br /><br /> <span data-ttu-id="62d1f-118">Nombre de la aplicación: %1 %r</span><span class="sxs-lookup"><span data-stu-id="62d1f-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="62d1f-119">Cadena de filtro de contraseña: %2 %r</span><span class="sxs-lookup"><span data-stu-id="62d1f-119">Password Filter String: %2%r</span></span><br /><br /> <span data-ttu-id="62d1f-120">Número de Tokens procesados: %3 %r</span><span class="sxs-lookup"><span data-stu-id="62d1f-120">Number Of Tokens Processed: %3%r</span></span><br /><br /> <span data-ttu-id="62d1f-121">Datos adicionales: %4 %r</span><span class="sxs-lookup"><span data-stu-id="62d1f-121">Additional Data: %4%r</span></span><br /><br /> <span data-ttu-id="62d1f-122">Código de error: %5</span><span class="sxs-lookup"><span data-stu-id="62d1f-122">Error Code: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="62d1f-123">Explicación</span><span class="sxs-lookup"><span data-stu-id="62d1f-123">Explanation</span></span>  
 <span data-ttu-id="62d1f-124">Se creó manualmente un filtro de contraseña no válido.</span><span class="sxs-lookup"><span data-stu-id="62d1f-124">An invalid password filter has been created manually.</span></span> <span data-ttu-id="62d1f-125">En algún momento de este proceso se generó un error (consulte la cadena de filtro de contraseña en el texto de la advertencia para conocer la ubicación del error).</span><span class="sxs-lookup"><span data-stu-id="62d1f-125">At some point in this process an error was introduced (see Password Filter String in the warning text for the location of the error).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="62d1f-126">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="62d1f-126">User Action</span></span>  
 <span data-ttu-id="62d1f-127">Para crear el filtro de contraseña mediante el Asistente para crear un filtro de contraseña, consulte [cómo usar filtros de contraseña](../core/how-to-use-password-filters.md).</span><span class="sxs-lookup"><span data-stu-id="62d1f-127">To create the Password Filter using the Create Password Filter Wizard, see [How to Use Password Filters](../core/how-to-use-password-filters.md).</span></span>