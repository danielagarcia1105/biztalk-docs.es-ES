---
title: "Requisitos para el inicio de sesión único-On2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- enabling SSO
- Single Sign-On, requirements
- SSO, enabling
- Single Sign-On, enabling
- SSO requirements
ms.assetid: ae4b5c1f-1718-4628-9159-2fb877498913
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c886792f36808152c4a27733544b09015c68f061
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="5c055-102">Requisitos para el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="5c055-102">Requirements for Single Sign-On</span></span>
<span data-ttu-id="5c055-103">Para usar el inicio de sesión único (SSO), necesita:</span><span class="sxs-lookup"><span data-stu-id="5c055-103">To use Single Sign-On (SSO), you need:</span></span>  
  
-   [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]  
  
-   [!INCLUDE[vs2010](../includes/vs2010-md.md)]  
  
-   <span data-ttu-id="5c055-104">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="5c055-104">Enterprise Single Sign-On</span></span>  
  
-   <span data-ttu-id="5c055-105">Un sistema de servidor compatible con SSO</span><span class="sxs-lookup"><span data-stu-id="5c055-105">A Server System that supports SSO</span></span>  
  
 <span data-ttu-id="5c055-106">El host aislado debe configurarse como autenticación de confianza.</span><span class="sxs-lookup"><span data-stu-id="5c055-106">The isolated host should be configured as authentication trusted.</span></span>  
  
### <a name="to-enable-sso"></a><span data-ttu-id="5c055-107">Para habilitar SSO</span><span class="sxs-lookup"><span data-stu-id="5c055-107">To enable SSO</span></span>  
  
1.  <span data-ttu-id="5c055-108">En el **propiedades de transporte** ventana, seleccione **Sí** para **usar SSO**.</span><span class="sxs-lookup"><span data-stu-id="5c055-108">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2.  <span data-ttu-id="5c055-109">Al especificar las propiedades del transporte, seleccione una aplicación afiliada adecuada.</span><span class="sxs-lookup"><span data-stu-id="5c055-109">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
 <span data-ttu-id="5c055-110">Para obtener información sobre cómo crear una aplicación afiliada, vea [crear aplicaciones afiliadas](../core/creating-affiliate-applications2.md).</span><span class="sxs-lookup"><span data-stu-id="5c055-110">For information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications2.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c055-111">Después de trabajar mediante SSO, no olvide restablecer las carpetas de uso compartido de Web en **no comparten**.</span><span class="sxs-lookup"><span data-stu-id="5c055-111">After performing work using SSO, remember to reset any Web-Sharing folder to **Do not share**.</span></span> <span data-ttu-id="5c055-112">Las aplicaciones que usen dichas carpetas no se actualizarán ni se desinstalarán correctamente si la carpeta es de uso compartido, ya que se considerará que están en uso.</span><span class="sxs-lookup"><span data-stu-id="5c055-112">Applications that use that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c055-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c055-113">See Also</span></span>  
 <span data-ttu-id="5c055-114">[Ejecución de proyectos SSO](../core/running-sso-projects1.md) </span><span class="sxs-lookup"><span data-stu-id="5c055-114">[Running SSO Projects](../core/running-sso-projects1.md) </span></span>  
 [<span data-ttu-id="5c055-115">Mediante el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="5c055-115">Using Single Sign-On</span></span>](../core/using-single-sign-on2.md)