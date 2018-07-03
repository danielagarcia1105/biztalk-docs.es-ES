---
title: 'De sesión único: Evento 10550 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73d63bc5-1e60-426c-a0d6-55c51dbb8d76
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 987e01d741ef49245c931f828f6cebeb3bf52cd2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021962"
---
# <a name="single-sign-on-event-10550"></a><span data-ttu-id="88f90-102">De sesión único: Evento 10550</span><span class="sxs-lookup"><span data-stu-id="88f90-102">Single Sign-On: Event 10550</span></span>
## <a name="details"></a><span data-ttu-id="88f90-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="88f90-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="88f90-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="88f90-104">Product Name</span></span>   |                                                                                           <span data-ttu-id="88f90-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="88f90-105">Enterprise Single Sign-On</span></span>                                                                                           |
| <span data-ttu-id="88f90-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="88f90-106">Product Version</span></span> |                                                                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                           |
|    <span data-ttu-id="88f90-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="88f90-107">Event ID</span></span>     |                                                                                                     <span data-ttu-id="88f90-108">10550</span><span class="sxs-lookup"><span data-stu-id="88f90-108">10550</span></span>                                                                                                     |
|  <span data-ttu-id="88f90-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="88f90-109">Event Source</span></span>   |                                                                                                    <span data-ttu-id="88f90-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="88f90-110">ENTSSO</span></span>                                                                                                     |
|    <span data-ttu-id="88f90-111">Componente</span><span class="sxs-lookup"><span data-stu-id="88f90-111">Component</span></span>    |                                                                                                      <span data-ttu-id="88f90-112">N/D</span><span class="sxs-lookup"><span data-stu-id="88f90-112">N/A</span></span>                                                                                                      |
|  <span data-ttu-id="88f90-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="88f90-113">Symbolic Name</span></span>  |                                                                                        <span data-ttu-id="88f90-114">SSO_ERROR_SERVICE_NOT_SSO_ADMIN</span><span class="sxs-lookup"><span data-stu-id="88f90-114">SSO_ERROR_SERVICE_NOT_SSO_ADMIN</span></span>                                                                                        |
|  <span data-ttu-id="88f90-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="88f90-115">Message Text</span></span>   | <span data-ttu-id="88f90-116">El servicio SSO no pudo iniciarse porque la cuenta de servicio en la que se está ejecutando no es miembro de la cuenta de administradores de SSO.%r</span><span class="sxs-lookup"><span data-stu-id="88f90-116">The SSO service could not start because the service account it is running under is not a member of the SSO Administrators account.%r</span></span><br /><br /> <span data-ttu-id="88f90-117">Administradores de SSO: %1 %r</span><span class="sxs-lookup"><span data-stu-id="88f90-117">SSO Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="88f90-118">Cuenta de servicio SSO: %2</span><span class="sxs-lookup"><span data-stu-id="88f90-118">SSO Service Account: %2</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="88f90-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="88f90-119">Explanation</span></span>  
 <span data-ttu-id="88f90-120">El servicio SSO debe ejecutarse en una cuenta de servicio que sea miembro de la cuenta de administradores de SSO.</span><span class="sxs-lookup"><span data-stu-id="88f90-120">The SSO service must be running under a service account that is a member of the SSO Administrators account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="88f90-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="88f90-121">User Action</span></span>  
 <span data-ttu-id="88f90-122">Para obtener más información, consulte [cómo especificar administradores de SSO y cuentas de administradores afiliados](../core/how-to-specify-sso-administrators-and-affiliate-administrators-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="88f90-122">For more information, see [How to Specify SSO Administrators and Affiliate Administrators Accounts](../core/how-to-specify-sso-administrators-and-affiliate-administrators-accounts.md).</span></span>