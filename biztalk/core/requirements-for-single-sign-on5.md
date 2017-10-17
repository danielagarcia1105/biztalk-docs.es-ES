---
title: "Requisitos para el inicio de sesión único | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 318b9977-ce24-48d6-971b-49a059a1bdbc
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2abd36879428c9d775251e20dd63f8778aa7b63
ms.sourcegitcommit: 6b6d905bbef7796c850178e99ac293578bb58317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2017
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="55874-102">Requisitos para el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="55874-102">Requirements for Single Sign-On</span></span>
<span data-ttu-id="55874-103">Para usar el inicio de sesión único (SSO), debe tener:</span><span class="sxs-lookup"><span data-stu-id="55874-103">To use Single Sign-On (SSO), you must have:</span></span>  
  
-   <span data-ttu-id="55874-104">Microsoft BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="55874-104">Microsoft BizTalk Server</span></span> 
  
-   <span data-ttu-id="55874-105">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="55874-105">Visual Studio</span></span>  
  
-   <span data-ttu-id="55874-106">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="55874-106">Enterprise Single Sign-On</span></span>  
  
-   <span data-ttu-id="55874-107">Un sistema de servidor compatible con SSO</span><span class="sxs-lookup"><span data-stu-id="55874-107">A Server System that supports SSO</span></span>  
  
 <span data-ttu-id="55874-108">El host aislado debe configurarse como autenticación de confianza.</span><span class="sxs-lookup"><span data-stu-id="55874-108">The isolated host should be configured as authentication trusted.</span></span>  
  
## <a name="enable-sso"></a><span data-ttu-id="55874-109">Habilitar SSO</span><span class="sxs-lookup"><span data-stu-id="55874-109">Enable SSO</span></span>  
  
1.  <span data-ttu-id="55874-110">En el **propiedades de transporte** ventana, seleccione **Sí** para **usar SSO**.</span><span class="sxs-lookup"><span data-stu-id="55874-110">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2.  <span data-ttu-id="55874-111">Al especificar las propiedades del transporte, seleccione una aplicación afiliada adecuada.</span><span class="sxs-lookup"><span data-stu-id="55874-111">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
     <span data-ttu-id="55874-112">Para obtener información acerca de cómo crear aplicaciones afiliadas, vea [crear aplicaciones afiliadas](../core/creating-affiliate-applications3.md).</span><span class="sxs-lookup"><span data-stu-id="55874-112">For information about creating affiliate applications, see [Creating Affiliate Applications](../core/creating-affiliate-applications3.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="55874-113">Después de trabajar mediante SSO, no olvide restablecer cualquiera **uso compartido de Web** carpeta **no comparten**.</span><span class="sxs-lookup"><span data-stu-id="55874-113">After performing work using SSO, remember to reset any **Web-Sharing** folder to **Do not share**.</span></span> <span data-ttu-id="55874-114">Las aplicaciones que usen esas carpetas no se actualizarán ni se desinstalarán correctamente si la carpeta es de uso compartido, ya que se considerará que están en uso.</span><span class="sxs-lookup"><span data-stu-id="55874-114">Applications using that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55874-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="55874-115">See Also</span></span>  
 [<span data-ttu-id="55874-116">Mediante el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="55874-116">Using Single Sign-On</span></span>](../core/using-single-sign-on3.md)