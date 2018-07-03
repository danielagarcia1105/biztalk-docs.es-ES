---
title: Requisitos de inicio de sesión único para el adaptador TIBCO Rendevous | Microsoft Docs
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
ms.openlocfilehash: 7e61b456def74ee76d887fa42149ee95b9ca3cbf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013741"
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="c927a-102">Requisitos para el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="c927a-102">Requirements for Single Sign-On</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c927a-103">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c927a-103">Prerequisites</span></span>
<span data-ttu-id="c927a-104">Para usar el inicio de sesión único (SSO), debe tener lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c927a-104">To use Single Sign-On (SSO), you must have the following:</span></span>  
  
-   <span data-ttu-id="c927a-105">Microsoft BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="c927a-105">Microsoft BizTalk Server</span></span>
  
-   <span data-ttu-id="c927a-106">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c927a-106">Visual Studio</span></span>  
  
-   <span data-ttu-id="c927a-107">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="c927a-107">Enterprise Single Sign-On</span></span>  
  
-   <span data-ttu-id="c927a-108">Un sistema de servidor que admita el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="c927a-108">A server system that supports SSO</span></span>  
  
-   <span data-ttu-id="c927a-109">El host aislado debe configurarse como autenticación de confianza.</span><span class="sxs-lookup"><span data-stu-id="c927a-109">The isolated host should be configured as Authentication Trusted.</span></span>  
  
## <a name="enable-sso"></a><span data-ttu-id="c927a-110">Habilitar el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="c927a-110">Enable SSO</span></span>  
  
1. <span data-ttu-id="c927a-111">En el **propiedades de transporte** ventana, seleccione **Sí** para **usar SSO**.</span><span class="sxs-lookup"><span data-stu-id="c927a-111">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2. <span data-ttu-id="c927a-112">Al especificar las propiedades del transporte, seleccione una aplicación afiliada adecuada.</span><span class="sxs-lookup"><span data-stu-id="c927a-112">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
   <span data-ttu-id="c927a-113">Para obtener más información, consulte [crear aplicaciones afiliadas](../core/creating-affiliate-applications1.md).</span><span class="sxs-lookup"><span data-stu-id="c927a-113">For more information, see [Creating Affiliate Applications](../core/creating-affiliate-applications1.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c927a-114">Después de trabajar mediante SSO, no olvide restablecer cualquier carpeta de uso compartido de Web **no comparten**.</span><span class="sxs-lookup"><span data-stu-id="c927a-114">After performing work using SSO, remember to reset any Web-Sharing folder to **Do not share**.</span></span> <span data-ttu-id="c927a-115">Las aplicaciones que usen dichas carpetas no se actualizarán ni se desinstalarán correctamente si la carpeta es de uso compartido, ya que se considerará que están en uso.</span><span class="sxs-lookup"><span data-stu-id="c927a-115">Applications that use that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c927a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c927a-116">See Also</span></span>  
[<span data-ttu-id="c927a-117">Seguridad</span><span class="sxs-lookup"><span data-stu-id="c927a-117">Security</span></span>](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)