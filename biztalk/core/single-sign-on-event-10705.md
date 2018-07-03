---
title: 'De sesión único: Evento 10705 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81456bdd-dfd8-4483-aa76-5ec72350cc70
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c74e4ebe0119698348668eb2ca6f78b5697cc5d0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976901"
---
# <a name="single-sign-on-event-10705"></a><span data-ttu-id="8c471-102">De sesión único: Evento 10705</span><span class="sxs-lookup"><span data-stu-id="8c471-102">Single Sign-On: Event 10705</span></span>
## <a name="details"></a><span data-ttu-id="8c471-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="8c471-103">Details</span></span>  

|                 |                                                                                                            |
|-----------------|------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="8c471-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="8c471-104">Product Name</span></span>   |                                         <span data-ttu-id="8c471-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="8c471-105">Enterprise Single Sign-On</span></span>                                          |
| <span data-ttu-id="8c471-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="8c471-106">Product Version</span></span> |                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                         |
|    <span data-ttu-id="8c471-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="8c471-107">Event ID</span></span>     |                                                   <span data-ttu-id="8c471-108">10705</span><span class="sxs-lookup"><span data-stu-id="8c471-108">10705</span></span>                                                    |
|  <span data-ttu-id="8c471-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="8c471-109">Event Source</span></span>   |                                                   <span data-ttu-id="8c471-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="8c471-110">ENTSSO</span></span>                                                   |
|    <span data-ttu-id="8c471-111">Componente</span><span class="sxs-lookup"><span data-stu-id="8c471-111">Component</span></span>    |                                                    <span data-ttu-id="8c471-112">N\D</span><span class="sxs-lookup"><span data-stu-id="8c471-112">N\A</span></span>                                                     |
|  <span data-ttu-id="8c471-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="8c471-113">Symbolic Name</span></span>  |                                          <span data-ttu-id="8c471-114">SSO_WARN_PS_NOT_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="8c471-114">SSO_WARN_PS_NOT_ADAPTER</span></span>                                           |
|  <span data-ttu-id="8c471-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="8c471-115">Message Text</span></span>   | <span data-ttu-id="8c471-116">El adaptador especificado no es una aplicación de adaptador.</span><span class="sxs-lookup"><span data-stu-id="8c471-116">The specified adapter is not an adapter application.</span></span> <span data-ttu-id="8c471-117">Compruebe el tipo de aplicación.%r</span><span class="sxs-lookup"><span data-stu-id="8c471-117">Check the application type.%r</span></span><br /><br /> <span data-ttu-id="8c471-118">Adaptador: %1</span><span class="sxs-lookup"><span data-stu-id="8c471-118">Adapter: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="8c471-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="8c471-119">Explanation</span></span>  
 <span data-ttu-id="8c471-120">Este evento de advertencia indica que el adaptador especificado no es una aplicación de adaptador.</span><span class="sxs-lookup"><span data-stu-id="8c471-120">This Warning event indicates that the specified adapter is not an adapter application.</span></span>  

## <a name="user-action"></a><span data-ttu-id="8c471-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="8c471-121">User Action</span></span>  
 <span data-ttu-id="8c471-122">Para resolver esta advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8c471-122">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="8c471-123">Use el complemento MMC de administración de SSO, haga clic con el botón secundario en el adaptador especificado y, a continuación, haga clic en Propiedades para determinar el tipo de aplicación o bien, use las herramientas de línea de comandos "ssops -list" y "ssops -display" para determinarlo.</span><span class="sxs-lookup"><span data-stu-id="8c471-123">Use the SSO Admin MMC Snap-In, right click the specified adapter, and then click Properties to determine the application type or use the command line tool  ssops -list and ssops -display to determine the application type.</span></span>  

- <span data-ttu-id="8c471-124">Use el complemento MMC de administración de SSO o "ssops -addapp" para establecer la aplicación de adaptador.</span><span class="sxs-lookup"><span data-stu-id="8c471-124">Use the SSO Admin MMC Snap-In or ssops -addapp to set the adapter application.</span></span>  

  <span data-ttu-id="8c471-125">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="8c471-125">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="8c471-126">Cómo administrar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="8c471-126">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)
