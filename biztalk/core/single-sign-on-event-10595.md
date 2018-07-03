---
title: 'De sesión único: Evento 10595 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1517478c-7217-4e34-a5cb-ff7deea367ed
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0cbc952197971f4e0db0586bc4f1d2d6c37aba44
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995229"
---
# <a name="single-sign-on-event-10595"></a><span data-ttu-id="ce4e5-102">De sesión único: Evento 10595</span><span class="sxs-lookup"><span data-stu-id="ce4e5-102">Single Sign-On: Event 10595</span></span>
## <a name="details"></a><span data-ttu-id="ce4e5-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ce4e5-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ce4e5-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ce4e5-104">Product Name</span></span>   |                                                                                             <span data-ttu-id="ce4e5-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="ce4e5-105">Enterprise Single Sign-On</span></span>                                                                                              |
| <span data-ttu-id="ce4e5-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ce4e5-106">Product Version</span></span> |                                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                             |
|    <span data-ttu-id="ce4e5-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ce4e5-107">Event ID</span></span>     |                                                                                                       <span data-ttu-id="ce4e5-108">10595</span><span class="sxs-lookup"><span data-stu-id="ce4e5-108">10595</span></span>                                                                                                        |
|  <span data-ttu-id="ce4e5-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ce4e5-109">Event Source</span></span>   |                                                                                                       <span data-ttu-id="ce4e5-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ce4e5-110">ENTSSO</span></span>                                                                                                       |
|    <span data-ttu-id="ce4e5-111">Componente</span><span class="sxs-lookup"><span data-stu-id="ce4e5-111">Component</span></span>    |                                                                                                        <span data-ttu-id="ce4e5-112">N/D</span><span class="sxs-lookup"><span data-stu-id="ce4e5-112">N/A</span></span>                                                                                                         |
|  <span data-ttu-id="ce4e5-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ce4e5-113">Symbolic Name</span></span>  |                                                                                           <span data-ttu-id="ce4e5-114">SSO_WARN_APP_INCOMPLETE_FIELDS</span><span class="sxs-lookup"><span data-stu-id="ce4e5-114">SSO_WARN_APP_INCOMPLETE_FIELDS</span></span>                                                                                           |
|  <span data-ttu-id="ce4e5-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ce4e5-115">Message Text</span></span>   | <span data-ttu-id="ce4e5-116">No se puede habilitar la aplicación porque los campos están incompletos para esta aplicación.%r</span><span class="sxs-lookup"><span data-stu-id="ce4e5-116">The application cannot be enabled because the fields are incomplete for this application.%r</span></span><br /><br /> <span data-ttu-id="ce4e5-117">Nombre de la aplicación: %1 %r</span><span class="sxs-lookup"><span data-stu-id="ce4e5-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="ce4e5-118">Número de campos definidos: %2 %r</span><span class="sxs-lookup"><span data-stu-id="ce4e5-118">Number of Fields Defined: %2%r</span></span><br /><br /> <span data-ttu-id="ce4e5-119">Número de campos creados: %3</span><span class="sxs-lookup"><span data-stu-id="ce4e5-119">Number of Fields Created: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="ce4e5-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="ce4e5-120">Explanation</span></span>  
 <span data-ttu-id="ce4e5-121">Al crear una aplicación en el nivel de API, se especificó el número de campos (por ejemplo, Id. de usuario y contraseña) que definiría la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ce4e5-121">When creating an application at the API level, you specified the number of fields (i.e. UserID, Password) the application would define.</span></span> <span data-ttu-id="ce4e5-122">También se debe crear cada campo definido.</span><span class="sxs-lookup"><span data-stu-id="ce4e5-122">Each field that has been defined must also be created.</span></span> <span data-ttu-id="ce4e5-123">Este mensaje de advertencia enumera el nombre, el número de campos definidos y el número de campos creados de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ce4e5-123">This warning message lists the application name, number of fields defined, and number of fields created.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ce4e5-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ce4e5-124">User Action</span></span>  
 <span data-ttu-id="ce4e5-125">Determine los campos que se definieron pero no se crearon y, a continuación, vuelva atrás y créelos.</span><span class="sxs-lookup"><span data-stu-id="ce4e5-125">Determine which fields were defined but not created, and then go back and create them.</span></span>