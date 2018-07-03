---
title: 'De sesión único: Evento 10680 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88ea12ff-d181-423f-9054-b0c656cc4558
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1ce2871618722af1fce4175be715c8ac1fa55a9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974901"
---
# <a name="single-sign-on-event-10680"></a><span data-ttu-id="ee81e-102">De sesión único: Evento 10680</span><span class="sxs-lookup"><span data-stu-id="ee81e-102">Single Sign-On: Event 10680</span></span>
## <a name="details"></a><span data-ttu-id="ee81e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ee81e-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ee81e-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ee81e-104">Product Name</span></span>   |                                                                                                                                        <span data-ttu-id="ee81e-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="ee81e-105">Enterprise Single Sign-On</span></span>                                                                                                                                        |
| <span data-ttu-id="ee81e-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ee81e-106">Product Version</span></span> |                                                                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                        |
|    <span data-ttu-id="ee81e-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ee81e-107">Event ID</span></span>     |                                                                                                                                                  <span data-ttu-id="ee81e-108">10680</span><span class="sxs-lookup"><span data-stu-id="ee81e-108">10680</span></span>                                                                                                                                                  |
|  <span data-ttu-id="ee81e-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ee81e-109">Event Source</span></span>   |                                                                                                                                                 <span data-ttu-id="ee81e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ee81e-110">ENTSSO</span></span>                                                                                                                                                  |
|    <span data-ttu-id="ee81e-111">Componente</span><span class="sxs-lookup"><span data-stu-id="ee81e-111">Component</span></span>    |                                                                                                                                                   <span data-ttu-id="ee81e-112">N\D</span><span class="sxs-lookup"><span data-stu-id="ee81e-112">N\A</span></span>                                                                                                                                                   |
|  <span data-ttu-id="ee81e-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ee81e-113">Symbolic Name</span></span>  |                                                                                                                                      <span data-ttu-id="ee81e-114">SSO_WARN_PS_GET_CREDS_FAILED</span><span class="sxs-lookup"><span data-stu-id="ee81e-114">SSO_WARN_PS_GET_CREDS_FAILED</span></span>                                                                                                                                       |
|  <span data-ttu-id="ee81e-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ee81e-115">Message Text</span></span>   | <span data-ttu-id="ee81e-116">No se cambió la contraseña de la cuenta externa porque no se pudieron obtener las credenciales externas existentes de la base de datos de SSO.%r</span><span class="sxs-lookup"><span data-stu-id="ee81e-116">The password was not changed for the external account because the existing external credentials could not be obtained from the SSO database.%r</span></span><br /><br /> <span data-ttu-id="ee81e-117">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="ee81e-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="ee81e-118">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="ee81e-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="ee81e-119">Nombre de la aplicación: %3 %r</span><span class="sxs-lookup"><span data-stu-id="ee81e-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="ee81e-120">Cuenta externa: %4 %r</span><span class="sxs-lookup"><span data-stu-id="ee81e-120">External Account: %4%r</span></span><br /><br /> <span data-ttu-id="ee81e-121">Código de error: %5</span><span class="sxs-lookup"><span data-stu-id="ee81e-121">Error Code: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="ee81e-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="ee81e-122">Explanation</span></span>  
 <span data-ttu-id="ee81e-123">Este evento de advertencia indica que no se cambió la contraseña de la cuenta externa porque no se pudieron obtener las credenciales externas existentes de la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="ee81e-123">This Warning event indicates that the password was not changed for the external account because the existing external credentials could not be obtained from the SSO database.</span></span>  

## <a name="user-action"></a><span data-ttu-id="ee81e-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ee81e-124">User Action</span></span>  
 <span data-ttu-id="ee81e-125">Para resolver esta advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ee81e-125">To resolve this warning, do the following:</span></span>  

-   <span data-ttu-id="ee81e-126">Compruebe las credenciales externas.</span><span class="sxs-lookup"><span data-stu-id="ee81e-126">Verify external credentials.</span></span>  

-   <span data-ttu-id="ee81e-127">Si las credenciales externas no son válidas, use las herramientas de administración de SSO para establecerlas para esta cuenta externa.</span><span class="sxs-lookup"><span data-stu-id="ee81e-127">The external credentials are not valid, use the SSO administration tools to set the external credentials for this external account.</span></span> <span data-ttu-id="ee81e-128">Debe establecer la contraseña externa (para la cuenta especificada) en todas las aplicaciones asociadas.</span><span class="sxs-lookup"><span data-stu-id="ee81e-128">You must set the external password (for the given account) in all associated applications.</span></span>  

## <a name="more-info"></a><span data-ttu-id="ee81e-129">Más información</span><span class="sxs-lookup"><span data-stu-id="ee81e-129">More info</span></span>

- [<span data-ttu-id="ee81e-130">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="ee81e-130">Password Synchronization</span></span>](../core/password-synchronization2.md)  

- <span data-ttu-id="ee81e-131">**Propiedades del adaptador de sincronización de contraseñas: opciones** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="ee81e-131">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
