---
title: Requisitos para el inicio de sesión único | Documentos de Microsoft
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
ms.openlocfilehash: 43e54da709384611bffd1e05da6a79decc778e57
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015627"
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="dfcae-102">Requisitos para el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="dfcae-102">Requirements for Single Sign-On</span></span>
<span data-ttu-id="dfcae-103">Para usar el inicio de sesión único (SSO), debe tener el software siguiente instalado:</span><span class="sxs-lookup"><span data-stu-id="dfcae-103">To use Single Sign-On (SSO), you must have the following software installed:</span></span>  
  
-   <span data-ttu-id="dfcae-104">Microsoft BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="dfcae-104">Microsoft BizTalk Server</span></span>
  
-   <span data-ttu-id="dfcae-105">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="dfcae-105">Visual Studio</span></span>  
  
-   <span data-ttu-id="dfcae-106">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="dfcae-106">Enterprise Single Sign-On</span></span>  
  
-   <span data-ttu-id="dfcae-107">Un sistema de servidor compatible con SSO</span><span class="sxs-lookup"><span data-stu-id="dfcae-107">A Server System that supports SSO</span></span>  
  
-   <span data-ttu-id="dfcae-108">El host aislado debe configurarse como **autenticación de confianza**.</span><span class="sxs-lookup"><span data-stu-id="dfcae-108">The isolated host should be configured as **Authentication Trusted**.</span></span>  
  
## <a name="enable-sso"></a><span data-ttu-id="dfcae-109">Habilitar SSO</span><span class="sxs-lookup"><span data-stu-id="dfcae-109">Enable SSO</span></span>  
  
1.  <span data-ttu-id="dfcae-110">En el **propiedades de transporte** ventana, seleccione **Sí** para **usar SSO**.</span><span class="sxs-lookup"><span data-stu-id="dfcae-110">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2.  <span data-ttu-id="dfcae-111">Al especificar las propiedades del transporte, seleccione una aplicación afiliada adecuada.</span><span class="sxs-lookup"><span data-stu-id="dfcae-111">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
 <span data-ttu-id="dfcae-112">Para obtener información acerca de cómo crear una aplicación afiliada, vea [crear aplicaciones afiliadas](../core/creating-affiliate-applications4.md).</span><span class="sxs-lookup"><span data-stu-id="dfcae-112">For information about creating an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications4.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dfcae-113">Después de trabajar mediante SSO, no olvide restablecer las carpetas de uso compartido de Web en **no comparten**.</span><span class="sxs-lookup"><span data-stu-id="dfcae-113">After performing work using SSO, remember to reset any Web-Sharing folder to **Do not share**.</span></span> <span data-ttu-id="dfcae-114">Las aplicaciones que usen esas carpetas no se actualizarán ni se desinstalarán correctamente si la carpeta es de uso compartido, ya que se considerará que están en uso.</span><span class="sxs-lookup"><span data-stu-id="dfcae-114">Applications using that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfcae-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="dfcae-115">See Also</span></span>  
 [<span data-ttu-id="dfcae-116">Seguridad del adaptador de BizTalk para JD Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="dfcae-116">Security in BizTalk Adapter for JD Edwards EnterpriseOne</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)