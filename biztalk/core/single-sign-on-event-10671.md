---
title: 'De sesión único: Evento 10671 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06c5564f-6412-4e83-9bec-03264e992ebe
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f321a971f89c535da26604c3e03a2b62ebf060e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000077"
---
# <a name="single-sign-on-event-10671"></a><span data-ttu-id="64130-102">De sesión único: Evento 10671</span><span class="sxs-lookup"><span data-stu-id="64130-102">Single Sign-On: Event 10671</span></span>
## <a name="details"></a><span data-ttu-id="64130-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="64130-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="64130-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="64130-104">Product Name</span></span>   |                                                                                                                                                                                  <span data-ttu-id="64130-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="64130-105">Enterprise Single Sign-On</span></span>                                                                                                                                                                                  |
| <span data-ttu-id="64130-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="64130-106">Product Version</span></span> |                                                                                                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                                  |
|    <span data-ttu-id="64130-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="64130-107">Event ID</span></span>     |                                                                                                                                                                                            <span data-ttu-id="64130-108">10671</span><span class="sxs-lookup"><span data-stu-id="64130-108">10671</span></span>                                                                                                                                                                                            |
|  <span data-ttu-id="64130-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="64130-109">Event Source</span></span>   |                                                                                                                                                                                           <span data-ttu-id="64130-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="64130-110">ENTSSO</span></span>                                                                                                                                                                                            |
|    <span data-ttu-id="64130-111">Componente</span><span class="sxs-lookup"><span data-stu-id="64130-111">Component</span></span>    |                                                                                                                                                                                             <span data-ttu-id="64130-112">N\D</span><span class="sxs-lookup"><span data-stu-id="64130-112">N\A</span></span>                                                                                                                                                                                             |
|  <span data-ttu-id="64130-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="64130-113">Symbolic Name</span></span>  |                                                                                                                                                                         <span data-ttu-id="64130-114">SSO_INFO_EXTERNAL_MAPPING_CONFLICT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="64130-114">SSO_INFO_EXTERNAL_MAPPING_CONFLICT_ALLOWED</span></span>                                                                                                                                                                          |
|  <span data-ttu-id="64130-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="64130-115">Message Text</span></span>   | <span data-ttu-id="64130-116">El cambio de contraseña de Windows provocará cambios en varias cuentas en el mismo sistema externo.%r</span><span class="sxs-lookup"><span data-stu-id="64130-116">A Windows password change will cause changes to more than one account on the same external system.%r</span></span><br /><br /> <span data-ttu-id="64130-117">Esto se permite porque el adaptador de este sistema externo está configurado para permitir conflictos de asignación.%r</span><span class="sxs-lookup"><span data-stu-id="64130-117">This is allowed because the adapter for this external system is configured to allow mapping conflicts.%r</span></span><br /><br /> <span data-ttu-id="64130-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="64130-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="64130-119">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="64130-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="64130-120">Cuenta de Windows: %3 %r</span><span class="sxs-lookup"><span data-stu-id="64130-120">Windows Account: %3%r</span></span><br /><br /> <span data-ttu-id="64130-121">Cuenta externa 1: %4 %r</span><span class="sxs-lookup"><span data-stu-id="64130-121">External Account 1: %4%r</span></span><br /><br /> <span data-ttu-id="64130-122">Cuenta externa 2: %5</span><span class="sxs-lookup"><span data-stu-id="64130-122">External Account 2: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="64130-123">Explicación</span><span class="sxs-lookup"><span data-stu-id="64130-123">Explanation</span></span>  
 <span data-ttu-id="64130-124">Este evento de información indica que el cambio de contraseña de Windows provocará cambios en varias cuentas en el mismo sistema externo.</span><span class="sxs-lookup"><span data-stu-id="64130-124">This Information event indicates that a Windows password change will cause changes to more than one account on the same external system.</span></span>  

## <a name="user-action"></a><span data-ttu-id="64130-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="64130-125">User Action</span></span>  

-   <span data-ttu-id="64130-126">No es necesario que el usuario realice ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="64130-126">No user action is necessary.</span></span>  

## <a name="more-info"></a><span data-ttu-id="64130-127">Más información</span><span class="sxs-lookup"><span data-stu-id="64130-127">More info</span></span>

- <span data-ttu-id="64130-128">**Propiedades del adaptador de sincronización de contraseñas: opciones** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="64130-128">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>

- [<span data-ttu-id="64130-129">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="64130-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
