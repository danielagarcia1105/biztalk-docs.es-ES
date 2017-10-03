---
title: "Requisitos para el inicio de sesión único-el3 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Single Sign-On, requirements
- SSO, enabling
- Single Sign-On, enabling
- SSO requirements
ms.assetid: 7d5c406b-f548-4df0-8644-fdf6a812a989
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 005f095ae09b3018b9c8fe796520205103c7961a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="80373-102">Requisitos para el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="80373-102">Requirements for Single Sign-On</span></span>
<span data-ttu-id="80373-103">Para usar el inicio de sesión único (SSO), debe tener lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="80373-103">To use Single Sign-On (SSO), you must have the following:</span></span>  
  
-   <span data-ttu-id="80373-104">Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80373-104">Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]</span></span>  
  
-   [!INCLUDE[vs2010](../includes/vs2010-md.md)]  
  
-   <span data-ttu-id="80373-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="80373-105">Enterprise Single Sign-On</span></span>  
  
-   <span data-ttu-id="80373-106">Un sistema de servidor que admite el SSO</span><span class="sxs-lookup"><span data-stu-id="80373-106">A server system that supports SSO</span></span>  
  
-   <span data-ttu-id="80373-107">El host aislado debe configurarse como autenticación de confianza.</span><span class="sxs-lookup"><span data-stu-id="80373-107">The isolated host should be configured as Authentication Trusted.</span></span>  
  
### <a name="to-enable-sso"></a><span data-ttu-id="80373-108">Para habilitar SSO</span><span class="sxs-lookup"><span data-stu-id="80373-108">To enable SSO</span></span>  
  
1.  <span data-ttu-id="80373-109">En el **propiedades de transporte** ventana, seleccione **Sí** para **usar SSO**.</span><span class="sxs-lookup"><span data-stu-id="80373-109">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2.  <span data-ttu-id="80373-110">Al especificar las propiedades del transporte, seleccione una aplicación afiliada adecuada.</span><span class="sxs-lookup"><span data-stu-id="80373-110">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
 <span data-ttu-id="80373-111">Para obtener más información, consulte [crear aplicaciones afiliadas](../core/creating-affiliate-applications1.md).</span><span class="sxs-lookup"><span data-stu-id="80373-111">For more information, see [Creating Affiliate Applications](../core/creating-affiliate-applications1.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80373-112">Después de trabajar mediante SSO, no olvide restablecer las carpetas de uso compartido de Web en **no comparten**.</span><span class="sxs-lookup"><span data-stu-id="80373-112">After performing work using SSO, remember to reset any Web-Sharing folder to **Do not share**.</span></span> <span data-ttu-id="80373-113">Las aplicaciones que usen dichas carpetas no se actualizarán ni se desinstalarán correctamente si la carpeta es de uso compartido, ya que se considerará que están en uso.</span><span class="sxs-lookup"><span data-stu-id="80373-113">Applications that use that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80373-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="80373-114">See Also</span></span>  
 [<span data-ttu-id="80373-115">Mediante el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="80373-115">Using Single Sign-On</span></span>](../core/using-single-sign-on5.md)