---
title: 'De sesión único: Evento 10665 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d0de9d0-9b46-4f3a-b796-1ce3de01cf4c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e820b5d682a3ea5947d4811038d4a9bc5eaa38c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013925"
---
# <a name="single-sign-on-event-10665"></a><span data-ttu-id="d367b-102">De sesión único: Evento 10665</span><span class="sxs-lookup"><span data-stu-id="d367b-102">Single Sign-On: Event 10665</span></span>
## <a name="details"></a><span data-ttu-id="d367b-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="d367b-103">Details</span></span>  

|                 |                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d367b-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="d367b-104">Product Name</span></span>   |                                               <span data-ttu-id="d367b-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="d367b-105">Enterprise Single Sign-On</span></span>                                                |
| <span data-ttu-id="d367b-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="d367b-106">Product Version</span></span> |                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                               |
|    <span data-ttu-id="d367b-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="d367b-107">Event ID</span></span>     |                                                         <span data-ttu-id="d367b-108">10665</span><span class="sxs-lookup"><span data-stu-id="d367b-108">10665</span></span>                                                          |
|  <span data-ttu-id="d367b-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="d367b-109">Event Source</span></span>   |                                                         <span data-ttu-id="d367b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d367b-110">ENTSSO</span></span>                                                         |
|    <span data-ttu-id="d367b-111">Componente</span><span class="sxs-lookup"><span data-stu-id="d367b-111">Component</span></span>    |                                                          <span data-ttu-id="d367b-112">N\D</span><span class="sxs-lookup"><span data-stu-id="d367b-112">N\A</span></span>                                                           |
|  <span data-ttu-id="d367b-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d367b-113">Symbolic Name</span></span>  |                                                 <span data-ttu-id="d367b-114">SSO_WARN_NO_PROPERTIES</span><span class="sxs-lookup"><span data-stu-id="d367b-114">SSO_WARN_NO_PROPERTIES</span></span>                                                 |
|  <span data-ttu-id="d367b-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d367b-115">Message Text</span></span>   | <span data-ttu-id="d367b-116">Error al leer las propiedades del adaptador de sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="d367b-116">Error reading password sync adapter properties.</span></span> <span data-ttu-id="d367b-117">Se usan los valores predeterminados.%r</span><span class="sxs-lookup"><span data-stu-id="d367b-117">Using defaults.%r</span></span><br /><br /> <span data-ttu-id="d367b-118">Adaptador: %1 %r</span><span class="sxs-lookup"><span data-stu-id="d367b-118">Adapter: %1%r</span></span><br /><br /> <span data-ttu-id="d367b-119">Código de error: %2</span><span class="sxs-lookup"><span data-stu-id="d367b-119">Error Code: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="d367b-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="d367b-120">Explanation</span></span>  
 <span data-ttu-id="d367b-121">Este evento de advertencia indica que se produjo un error al leer las propiedades predeterminadas del adaptador de sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="d367b-121">This Warning event indicates that there was an error reading the default password sync adapter properties.</span></span> <span data-ttu-id="d367b-122">Cada adaptador de sincronización de contraseñas tiene propiedades de configuración asociadas a él.</span><span class="sxs-lookup"><span data-stu-id="d367b-122">Each password sync adapter has configuration properties associated with it.</span></span> <span data-ttu-id="d367b-123">Estas propiedades se guardan en el almacén de configuración de SSO y se crean mediante las herramientas de línea de comandos o la MMC de administración de SSO cuando se crea el adaptador de sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="d367b-123">These properties are stored in the SSO config store and are created by the SSO command line tools or the SSO Admin MMC when the password sync adapter is created.</span></span>  <span data-ttu-id="d367b-124">Si dicho adaptador se creó a través de otro medio, es posible que falten propiedades y, por lo tanto, puede emitirse este error.</span><span class="sxs-lookup"><span data-stu-id="d367b-124">There can be missing properties if the password sync adapter was created by any other means, then this error can be issued.</span></span>  

## <a name="user-action"></a><span data-ttu-id="d367b-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d367b-125">User Action</span></span>  
 <span data-ttu-id="d367b-126">Para solucionar la advertencia, realice una o varias de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="d367b-126">To resolve this warning, do one or more of the following:</span></span>  

-   <span data-ttu-id="d367b-127">Compruebe las propiedades del adaptador de sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="d367b-127">Verify password sync adapter properties.</span></span>  

-   <span data-ttu-id="d367b-128">Vuelva a crear el adaptador de sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="d367b-128">Recreate the password sync adapter</span></span>  

## <a name="more-info"></a><span data-ttu-id="d367b-129">Más información</span><span class="sxs-lookup"><span data-stu-id="d367b-129">More info</span></span>

- <span data-ttu-id="d367b-130">**Propiedades del adaptador de sincronización de contraseñas: opciones** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="d367b-130">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>

- [<span data-ttu-id="d367b-131">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="d367b-131">Password Synchronization</span></span>](../core/password-synchronization2.md)
