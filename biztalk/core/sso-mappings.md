---
title: Asignaciones de SSO | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maps [SSO]
- maps [SSO], creating
- SSO, maps
ms.assetid: b44f7a0c-595c-49dc-9d75-2e76f29dca88
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98b44a1a9e8be3b275a4dd328c70323d79eb8a54
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sso-mappings"></a><span data-ttu-id="957ad-102">Asignaciones de SSO</span><span class="sxs-lookup"><span data-stu-id="957ad-102">SSO Mappings</span></span>
<span data-ttu-id="957ad-103">Cuando un administrador de inicio de sesión único (SSO) o un administrador afiliado de SSO define una aplicación afiliada, el administrador puede definirla como aplicación con asignaciones individuales o como aplicación de asignaciones de grupo.</span><span class="sxs-lookup"><span data-stu-id="957ad-103">When an Enterprise Single Sign-On (SSO) administrator or an SSO affiliate administrator defines an affiliate application, the administrator can define it either as an application with individual mappings, or as an application with a group mapping.</span></span>  
  
## <a name="individual-mappings"></a><span data-ttu-id="957ad-104">Asignaciones individuales</span><span class="sxs-lookup"><span data-stu-id="957ad-104">Individual Mappings</span></span>  
 <span data-ttu-id="957ad-105">Las asignaciones individuales de SSO permiten a usuarios y administradores crear una asignación de uno a uno entre usuarios de Windows y sus correspondientes credenciales ajenas a Windows.</span><span class="sxs-lookup"><span data-stu-id="957ad-105">SSO individual mappings enable administrators and users to create a one-to-one mapping between Windows users and their corresponding non-Windows credentials.</span></span> <span data-ttu-id="957ad-106">Cuando utiliza asignaciones individuales, los usuarios pueden administrar sus propias asignaciones.</span><span class="sxs-lookup"><span data-stu-id="957ad-106">When using individual mappings, users can manage their own mappings.</span></span> <span data-ttu-id="957ad-107">El sistema de SSO mantiene la relación de uno a uno para la cuenta de usuario de Windows y la cuenta de usuario ajena a Windows.</span><span class="sxs-lookup"><span data-stu-id="957ad-107">The SSO system maintains the one-to-one relation for the user's Windows account and the user's non-Windows account.</span></span>  
  
 <span data-ttu-id="957ad-108">Los usuarios finales de Windows pueden crear y administrar sus propias asignaciones para aplicaciones de tipo individual.</span><span class="sxs-lookup"><span data-stu-id="957ad-108">Windows End-users can create and manage their own mappings for individual type applications.</span></span> <span data-ttu-id="957ad-109">La misma aplicación afiliada puede actuar como una aplicación de tipo SSO iniciado por Windows y una aplicación de tipo SSO iniciado por host.</span><span class="sxs-lookup"><span data-stu-id="957ad-109">The same affiliate application can act as a Windows Initiated SSO and a Host Initiated SSO type application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="957ad-110">Las asignaciones se pueden crear sólo para cuentas de dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="957ad-110">Mappings can be created only for Windows domain accounts.</span></span> <span data-ttu-id="957ad-111">No se puede asignar cuentas locales.</span><span class="sxs-lookup"><span data-stu-id="957ad-111">Local accounts cannot be mapped.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="957ad-112">Sólo los usuarios individuales pueden obtener las credenciales a sus cuentas individuales cuando utilizan asignaciones individuales.</span><span class="sxs-lookup"><span data-stu-id="957ad-112">Only individual users can obtain the credentials to their individual accounts when using individual mappings.</span></span>  
  
## <a name="group-mapping"></a><span data-ttu-id="957ad-113">Asignación de grupo</span><span class="sxs-lookup"><span data-stu-id="957ad-113">Group Mapping</span></span>  
 <span data-ttu-id="957ad-114">La asignación de grupo de SSO consiste en asignar un grupo de Windows que contenga varios usuarios de Windows a una sola cuenta en la aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="957ad-114">SSO group mapping consists of mapping a Windows group, which contains multiple Windows users, to a single account in the affiliate application.</span></span>  
  
 <span data-ttu-id="957ad-115">Asimismo, puede especificar varias cuentas para la función de usuarios de aplicación de SSO.</span><span class="sxs-lookup"><span data-stu-id="957ad-115">You can also specify multiple accounts for the SSO Application Users role.</span></span> <span data-ttu-id="957ad-116">Cada cuenta que especifica se puede asociar a una cuenta externa.</span><span class="sxs-lookup"><span data-stu-id="957ad-116">Each account you specify can be associated with an external account.</span></span> <span data-ttu-id="957ad-117">Por ejemplo, puede asignar un grupo de dominio a EXTERNALUSER1 y una cuenta de dominio individual a EXTERNALUSER2.</span><span class="sxs-lookup"><span data-stu-id="957ad-117">For example, you can map a domain group account to EXTERNALUSER1 and an individual domain account to EXTERNALUSER2.</span></span> <span data-ttu-id="957ad-118">Si el mismo usuario dispone de más de una asignación, se utiliza la primera asignación de usuarios de aplicación de SSO.</span><span class="sxs-lookup"><span data-stu-id="957ad-118">If the same user has more than one mapping, the first mapping in the order of SSO Application Users is used.</span></span>  
  
 <span data-ttu-id="957ad-119">Una asignación de grupo sólo la puede crear o administrar un administrador de aplicaciones, un administrador afiliado de SSO o un administrador de SSO.</span><span class="sxs-lookup"><span data-stu-id="957ad-119">Only an application administrator, SSO affiliate administrator, or SSO administrator can create or manage a group mapping.</span></span>  
  
 <span data-ttu-id="957ad-120">No puede especificar la misma aplicación de grupo para SSO iniciado por Windows y SSO iniciado por host.</span><span class="sxs-lookup"><span data-stu-id="957ad-120">You cannot specify the same group application for Windows initiated SSO and Host Initiated SSO.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="957ad-121">Las asignaciones se pueden crear sólo para cuentas de dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="957ad-121">Mappings can be created only for Windows domain accounts.</span></span> <span data-ttu-id="957ad-122">No se puede asignar cuentas locales.</span><span class="sxs-lookup"><span data-stu-id="957ad-122">Local accounts cannot be mapped.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="957ad-123">Cuando utiliza asignaciones de grupos, los miembros del grupo pueden obtener la información de credenciales para la asignación de grupo.</span><span class="sxs-lookup"><span data-stu-id="957ad-123">When you use group mappings, the members of the group can obtain the credential information for the group mapping.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="957ad-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="957ad-124">See Also</span></span>  
 <span data-ttu-id="957ad-125">[Administrar asignaciones de usuario](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="957ad-125">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="957ad-126">Aplicaciones afiliadas de SSO</span><span class="sxs-lookup"><span data-stu-id="957ad-126">SSO Affiliate Applications</span></span>](../core/sso-affiliate-applications.md)