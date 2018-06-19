---
title: Requisitos de SSO para adaptador TIBCO Rendevous | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d5c406b-f548-4df0-8644-fdf6a812a989
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40cf27a3b96534239fa871bd04b90febee9beafe
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015999"
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="5dd1f-102">Requisitos para el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="5dd1f-102">Requirements for Single Sign-On</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5dd1f-103">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5dd1f-103">Prerequisites</span></span>
<span data-ttu-id="5dd1f-104">Para usar el inicio de sesión único (SSO), debe tener lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5dd1f-104">To use Single Sign-On (SSO), you must have the following:</span></span>  
  
-   <span data-ttu-id="5dd1f-105">Microsoft BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="5dd1f-105">Microsoft BizTalk Server</span></span>
  
-   <span data-ttu-id="5dd1f-106">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5dd1f-106">Visual Studio</span></span>  
  
-   <span data-ttu-id="5dd1f-107">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="5dd1f-107">Enterprise Single Sign-On</span></span>  
  
-   <span data-ttu-id="5dd1f-108">Un sistema de servidor que admite el SSO</span><span class="sxs-lookup"><span data-stu-id="5dd1f-108">A server system that supports SSO</span></span>  
  
-   <span data-ttu-id="5dd1f-109">El host aislado debe configurarse como autenticación de confianza.</span><span class="sxs-lookup"><span data-stu-id="5dd1f-109">The isolated host should be configured as Authentication Trusted.</span></span>  
  
## <a name="enable-sso"></a><span data-ttu-id="5dd1f-110">Habilitar SSO</span><span class="sxs-lookup"><span data-stu-id="5dd1f-110">Enable SSO</span></span>  
  
1.  <span data-ttu-id="5dd1f-111">En el **propiedades de transporte** ventana, seleccione **Sí** para **usar SSO**.</span><span class="sxs-lookup"><span data-stu-id="5dd1f-111">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2.  <span data-ttu-id="5dd1f-112">Al especificar las propiedades del transporte, seleccione una aplicación afiliada adecuada.</span><span class="sxs-lookup"><span data-stu-id="5dd1f-112">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
 <span data-ttu-id="5dd1f-113">Para obtener más información, consulte [crear aplicaciones afiliadas](../core/creating-affiliate-applications1.md).</span><span class="sxs-lookup"><span data-stu-id="5dd1f-113">For more information, see [Creating Affiliate Applications](../core/creating-affiliate-applications1.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5dd1f-114">Después de trabajar mediante SSO, no olvide restablecer las carpetas de uso compartido de Web en **no comparten**.</span><span class="sxs-lookup"><span data-stu-id="5dd1f-114">After performing work using SSO, remember to reset any Web-Sharing folder to **Do not share**.</span></span> <span data-ttu-id="5dd1f-115">Las aplicaciones que usen dichas carpetas no se actualizarán ni se desinstalarán correctamente si la carpeta es de uso compartido, ya que se considerará que están en uso.</span><span class="sxs-lookup"><span data-stu-id="5dd1f-115">Applications that use that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dd1f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5dd1f-116">See Also</span></span>  
[<span data-ttu-id="5dd1f-117">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5dd1f-117">Security</span></span>](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)