---
title: "Requisitos para el inicio de sesión único-On5 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Single Sign-On, requirements [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], Single Sign-On
- SSO, requirements [JD Edwards OneWorld adapters]
- Single Sign-On, enabling [JD Edwards OneWorld adapters]
ms.assetid: 318b9977-ce24-48d6-971b-49a059a1bdbc
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b186eca2c24ef9c2731b66194a0543aba14e8bf1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="0b05c-102">Requisitos para el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="0b05c-102">Requirements for Single Sign-On</span></span>
<span data-ttu-id="0b05c-103">Para usar el inicio de sesión único (SSO), debe tener:</span><span class="sxs-lookup"><span data-stu-id="0b05c-103">To use Single Sign-On (SSO), you must have:</span></span>  
  
-   <span data-ttu-id="0b05c-104">Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b05c-104">Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]</span></span>  
  
-   [!INCLUDE[vs2010](../includes/vs2010-md.md)]  
  
-   <span data-ttu-id="0b05c-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="0b05c-105">Enterprise Single Sign-On</span></span>  
  
-   <span data-ttu-id="0b05c-106">Un sistema de servidor compatible con SSO</span><span class="sxs-lookup"><span data-stu-id="0b05c-106">A Server System that supports SSO</span></span>  
  
 <span data-ttu-id="0b05c-107">El host aislado debe configurarse como autenticación de confianza.</span><span class="sxs-lookup"><span data-stu-id="0b05c-107">The isolated host should be configured as authentication trusted.</span></span>  
  
### <a name="to-enable-sso"></a><span data-ttu-id="0b05c-108">Para habilitar SSO</span><span class="sxs-lookup"><span data-stu-id="0b05c-108">To enable SSO</span></span>  
  
1.  <span data-ttu-id="0b05c-109">En el **propiedades de transporte** ventana, seleccione **Sí** para **usar SSO**.</span><span class="sxs-lookup"><span data-stu-id="0b05c-109">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2.  <span data-ttu-id="0b05c-110">Al especificar las propiedades del transporte, seleccione una aplicación afiliada adecuada.</span><span class="sxs-lookup"><span data-stu-id="0b05c-110">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
     <span data-ttu-id="0b05c-111">Para obtener información acerca de cómo crear aplicaciones afiliadas, vea [crear aplicaciones afiliadas](../core/creating-affiliate-applications3.md).</span><span class="sxs-lookup"><span data-stu-id="0b05c-111">For information about creating affiliate applications, see [Creating Affiliate Applications](../core/creating-affiliate-applications3.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0b05c-112">Después de trabajar mediante SSO, no olvide restablecer cualquiera **uso compartido de Web** carpeta **no comparten**.</span><span class="sxs-lookup"><span data-stu-id="0b05c-112">After performing work using SSO, remember to reset any **Web-Sharing** folder to **Do not share**.</span></span> <span data-ttu-id="0b05c-113">Las aplicaciones que usen esas carpetas no se actualizarán ni se desinstalarán correctamente si la carpeta es de uso compartido, ya que se considerará que están en uso.</span><span class="sxs-lookup"><span data-stu-id="0b05c-113">Applications using that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b05c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b05c-114">See Also</span></span>  
 [<span data-ttu-id="0b05c-115">Mediante el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="0b05c-115">Using Single Sign-On</span></span>](../core/using-single-sign-on3.md)