---
title: 'De sesión único: Evento 10568 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 266fd09a-c7e6-4a69-ac1c-1834097fa393
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c94c99580b63c5dc6eede29b595435daa256115
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010253"
---
# <a name="single-sign-on-event-10568"></a><span data-ttu-id="b7bec-102">De sesión único: Evento 10568</span><span class="sxs-lookup"><span data-stu-id="b7bec-102">Single Sign-On: Event 10568</span></span>
## <a name="details"></a><span data-ttu-id="b7bec-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="b7bec-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                             |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b7bec-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="b7bec-104">Product Name</span></span>   |                                                                                                  <span data-ttu-id="b7bec-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="b7bec-105">Enterprise Single Sign-On</span></span>                                                                                                  |
| <span data-ttu-id="b7bec-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="b7bec-106">Product Version</span></span> |                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                  |
|    <span data-ttu-id="b7bec-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="b7bec-107">Event ID</span></span>     |                                                                                                            <span data-ttu-id="b7bec-108">10568</span><span class="sxs-lookup"><span data-stu-id="b7bec-108">10568</span></span>                                                                                                            |
|  <span data-ttu-id="b7bec-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="b7bec-109">Event Source</span></span>   |                                                                                                           <span data-ttu-id="b7bec-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b7bec-110">ENTSSO</span></span>                                                                                                            |
|    <span data-ttu-id="b7bec-111">Componente</span><span class="sxs-lookup"><span data-stu-id="b7bec-111">Component</span></span>    |                                                                                                             <span data-ttu-id="b7bec-112">N/D</span><span class="sxs-lookup"><span data-stu-id="b7bec-112">N/A</span></span>                                                                                                             |
|  <span data-ttu-id="b7bec-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b7bec-113">Symbolic Name</span></span>  |                                                                                              <span data-ttu-id="b7bec-114">SSO_WARN_INVALID_APP_ADMIN_GROUP</span><span class="sxs-lookup"><span data-stu-id="b7bec-114">SSO_WARN_INVALID_APP_ADMIN_GROUP</span></span>                                                                                               |
|  <span data-ttu-id="b7bec-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b7bec-115">Message Text</span></span>   | <span data-ttu-id="b7bec-116">Cuenta de administradores de aplicación no válida para actualización de la aplicación.%r</span><span class="sxs-lookup"><span data-stu-id="b7bec-116">The Application Administrators account is not valid for application update.%r</span></span><br /><br /> <span data-ttu-id="b7bec-117">Nombre de la aplicación: %1 %r</span><span class="sxs-lookup"><span data-stu-id="b7bec-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="b7bec-118">Administradores de aplicación: %2 %r</span><span class="sxs-lookup"><span data-stu-id="b7bec-118">Application Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="b7bec-119">Cuentas no válidas: %3 %r</span><span class="sxs-lookup"><span data-stu-id="b7bec-119">Invalid accounts: %3%r</span></span><br /><br /> <span data-ttu-id="b7bec-120">Código de error: %4</span><span class="sxs-lookup"><span data-stu-id="b7bec-120">Error Code: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="b7bec-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="b7bec-121">Explanation</span></span>  
 <span data-ttu-id="b7bec-122">Ha intentado actualizar una cuenta de administradores de aplicación que no es válida o que no existe.</span><span class="sxs-lookup"><span data-stu-id="b7bec-122">You have attempted to update an Application Administrators account which is either invalid or does not exist.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b7bec-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b7bec-123">User Action</span></span>  
 <span data-ttu-id="b7bec-124">Compruebe si el nombre de la cuenta es correcto.</span><span class="sxs-lookup"><span data-stu-id="b7bec-124">Check that the name of the account is correct.</span></span>