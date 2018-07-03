---
title: Requisitos para el inicio de sesión único | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1111377-2fe1-4d65-ac0d-c89d2f1740b8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9045c51470d666906c090b55d6307c9f85d20e0c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022482"
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="30a4e-102">Requisitos para el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="30a4e-102">Requirements for Single Sign-On</span></span>
<span data-ttu-id="30a4e-103">Para usar el inicio de sesión único (SSO), debe tener el software siguiente instalado:</span><span class="sxs-lookup"><span data-stu-id="30a4e-103">To use Single Sign-On (SSO), you must have the following software installed:</span></span>  
  
-   <span data-ttu-id="30a4e-104">Microsoft BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="30a4e-104">Microsoft BizTalk Server</span></span>
  
-   <span data-ttu-id="30a4e-105">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="30a4e-105">Visual Studio</span></span>  
  
-   <span data-ttu-id="30a4e-106">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="30a4e-106">Enterprise Single Sign-On</span></span>  
  
-   <span data-ttu-id="30a4e-107">Un sistema de servidor compatible con SSO</span><span class="sxs-lookup"><span data-stu-id="30a4e-107">A Server System that supports SSO</span></span>  
  
-   <span data-ttu-id="30a4e-108">El host aislado debe configurarse como **autenticación de confianza**.</span><span class="sxs-lookup"><span data-stu-id="30a4e-108">The isolated host should be configured as **Authentication Trusted**.</span></span>  
  
## <a name="enable-sso"></a><span data-ttu-id="30a4e-109">Habilitar el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="30a4e-109">Enable SSO</span></span>  
  
1. <span data-ttu-id="30a4e-110">En el **propiedades de transporte** ventana, seleccione **Sí** para **usar SSO**.</span><span class="sxs-lookup"><span data-stu-id="30a4e-110">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2. <span data-ttu-id="30a4e-111">Al especificar las propiedades del transporte, seleccione una aplicación afiliada adecuada.</span><span class="sxs-lookup"><span data-stu-id="30a4e-111">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
   <span data-ttu-id="30a4e-112">Para obtener información acerca de cómo crear una aplicación afiliada, vea [crear aplicaciones afiliadas](../core/creating-affiliate-applications4.md).</span><span class="sxs-lookup"><span data-stu-id="30a4e-112">For information about creating an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications4.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30a4e-113">Después de trabajar mediante SSO, no olvide restablecer cualquier carpeta de uso compartido de Web **no comparten**.</span><span class="sxs-lookup"><span data-stu-id="30a4e-113">After performing work using SSO, remember to reset any Web-Sharing folder to **Do not share**.</span></span> <span data-ttu-id="30a4e-114">Las aplicaciones que usen esas carpetas no se actualizarán ni se desinstalarán correctamente si la carpeta es de uso compartido, ya que se considerará que están en uso.</span><span class="sxs-lookup"><span data-stu-id="30a4e-114">Applications using that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30a4e-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="30a4e-115">See Also</span></span>  
 [<span data-ttu-id="30a4e-116">Seguridad del adaptador de BizTalk para JD Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="30a4e-116">Security in BizTalk Adapter for JD Edwards EnterpriseOne</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)