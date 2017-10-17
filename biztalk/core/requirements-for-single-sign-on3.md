---
title: "Requisitos para el inicio de sesión único | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d5c406b-f548-4df0-8644-fdf6a812a989
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61932b44364670515f02f89a1441a5d54030bc94
ms.sourcegitcommit: 6b6d905bbef7796c850178e99ac293578bb58317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2017
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="b8a9f-102">Requisitos para el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="b8a9f-102">Requirements for Single Sign-On</span></span>
<span data-ttu-id="b8a9f-103">Para usar el inicio de sesión único (SSO), debe tener lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b8a9f-103">To use Single Sign-On (SSO), you must have the following:</span></span>  
  
-   <span data-ttu-id="b8a9f-104">Microsoft BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="b8a9f-104">Microsoft BizTalk Server</span></span>
  
-   <span data-ttu-id="b8a9f-105">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b8a9f-105">Visual Studio</span></span>  
  
-   <span data-ttu-id="b8a9f-106">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="b8a9f-106">Enterprise Single Sign-On</span></span>  
  
-   <span data-ttu-id="b8a9f-107">Un sistema de servidor que admite el SSO</span><span class="sxs-lookup"><span data-stu-id="b8a9f-107">A server system that supports SSO</span></span>  
  
-   <span data-ttu-id="b8a9f-108">El host aislado debe configurarse como autenticación de confianza.</span><span class="sxs-lookup"><span data-stu-id="b8a9f-108">The isolated host should be configured as Authentication Trusted.</span></span>  
  
## <a name="enable-sso"></a><span data-ttu-id="b8a9f-109">Habilitar SSO</span><span class="sxs-lookup"><span data-stu-id="b8a9f-109">Enable SSO</span></span>  
  
1.  <span data-ttu-id="b8a9f-110">En el **propiedades de transporte** ventana, seleccione **Sí** para **usar SSO**.</span><span class="sxs-lookup"><span data-stu-id="b8a9f-110">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2.  <span data-ttu-id="b8a9f-111">Al especificar las propiedades del transporte, seleccione una aplicación afiliada adecuada.</span><span class="sxs-lookup"><span data-stu-id="b8a9f-111">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
 <span data-ttu-id="b8a9f-112">Para obtener más información, consulte [crear aplicaciones afiliadas](../core/creating-affiliate-applications1.md).</span><span class="sxs-lookup"><span data-stu-id="b8a9f-112">For more information, see [Creating Affiliate Applications](../core/creating-affiliate-applications1.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8a9f-113">Después de trabajar mediante SSO, no olvide restablecer las carpetas de uso compartido de Web en **no comparten**.</span><span class="sxs-lookup"><span data-stu-id="b8a9f-113">After performing work using SSO, remember to reset any Web-Sharing folder to **Do not share**.</span></span> <span data-ttu-id="b8a9f-114">Las aplicaciones que usen dichas carpetas no se actualizarán ni se desinstalarán correctamente si la carpeta es de uso compartido, ya que se considerará que están en uso.</span><span class="sxs-lookup"><span data-stu-id="b8a9f-114">Applications that use that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8a9f-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8a9f-115">See Also</span></span>  
 [<span data-ttu-id="b8a9f-116">Mediante el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="b8a9f-116">Using Single Sign-On</span></span>](../core/using-single-sign-on5.md)