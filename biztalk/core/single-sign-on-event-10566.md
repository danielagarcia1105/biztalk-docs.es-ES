---
title: 'De sesión único: Evento 10566 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7bd140b-5503-40f8-bf5d-604fa763989e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4748670e128b5b3a9717e2e430acb976da7bb4d1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015093"
---
# <a name="single-sign-on-event-10566"></a><span data-ttu-id="bfe2c-102">De sesión único: Evento 10566</span><span class="sxs-lookup"><span data-stu-id="bfe2c-102">Single Sign-On: Event 10566</span></span>
## <a name="details"></a><span data-ttu-id="bfe2c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="bfe2c-103">Details</span></span>  
  
|                 |                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="bfe2c-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="bfe2c-104">Product Name</span></span>   |                                                                     <span data-ttu-id="bfe2c-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="bfe2c-105">Enterprise Single Sign-On</span></span>                                                                      |
| <span data-ttu-id="bfe2c-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="bfe2c-106">Product Version</span></span> |                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                     |
|    <span data-ttu-id="bfe2c-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="bfe2c-107">Event ID</span></span>     |                                                                               <span data-ttu-id="bfe2c-108">10566</span><span class="sxs-lookup"><span data-stu-id="bfe2c-108">10566</span></span>                                                                                |
|  <span data-ttu-id="bfe2c-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="bfe2c-109">Event Source</span></span>   |                                                                               <span data-ttu-id="bfe2c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="bfe2c-110">ENTSSO</span></span>                                                                               |
|    <span data-ttu-id="bfe2c-111">Componente</span><span class="sxs-lookup"><span data-stu-id="bfe2c-111">Component</span></span>    |                                                                                <span data-ttu-id="bfe2c-112">N/D</span><span class="sxs-lookup"><span data-stu-id="bfe2c-112">N/A</span></span>                                                                                 |
|  <span data-ttu-id="bfe2c-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="bfe2c-113">Symbolic Name</span></span>  |                                                                  <span data-ttu-id="bfe2c-114">SSO_WARN_CANNOT_UPDATE_APP_FLAGS</span><span class="sxs-lookup"><span data-stu-id="bfe2c-114">SSO_WARN_CANNOT_UPDATE_APP_FLAGS</span></span>                                                                  |
|  <span data-ttu-id="bfe2c-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="bfe2c-115">Message Text</span></span>   | <span data-ttu-id="bfe2c-116">No se pueden actualizar algunos de los marcadores especificados para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bfe2c-116">You cannot update some of the specified flags for this application.</span></span> <span data-ttu-id="bfe2c-117">Se ignorarán.%r</span><span class="sxs-lookup"><span data-stu-id="bfe2c-117">They will be ignored.%r</span></span><br /><br /> <span data-ttu-id="bfe2c-118">Nombre de la aplicación: %1 %r</span><span class="sxs-lookup"><span data-stu-id="bfe2c-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="bfe2c-119">Especifica la máscara de marca: %2</span><span class="sxs-lookup"><span data-stu-id="bfe2c-119">Specified Flag Mask: %2</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="bfe2c-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="bfe2c-120">Explanation</span></span>  
 <span data-ttu-id="bfe2c-121">No se pueden cambiar determinados marcadores en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="bfe2c-121">Certain flags in an application cannot be changed.</span></span> <span data-ttu-id="bfe2c-122">(Por ejemplo, no se permite cambiar el tipo de aplicación de Individual a Grupo). Los marcadores de esta aplicación se especifican en el texto de la advertencia.</span><span class="sxs-lookup"><span data-stu-id="bfe2c-122">(For example, it is not allowed to change an application type from Individual to Group.) The flags for this application are specified in the warning text.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bfe2c-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="bfe2c-123">User Action</span></span>  
 <span data-ttu-id="bfe2c-124">No se requiere ninguna acción del usuario.</span><span class="sxs-lookup"><span data-stu-id="bfe2c-124">No user action is required.</span></span>