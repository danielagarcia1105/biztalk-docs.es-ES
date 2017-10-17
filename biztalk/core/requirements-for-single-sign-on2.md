---
title: "Requisitos para el inicio de sesión único | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae4b5c1f-1718-4628-9159-2fb877498913
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 472893a2a65d762f17747dac78b67b373165c0cf
ms.sourcegitcommit: 6b6d905bbef7796c850178e99ac293578bb58317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2017
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="82a91-102">Requisitos para el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="82a91-102">Requirements for Single Sign-On</span></span>
<span data-ttu-id="82a91-103">Para usar el inicio de sesión único (SSO), necesita:</span><span class="sxs-lookup"><span data-stu-id="82a91-103">To use Single Sign-On (SSO), you need:</span></span>  
  
-   <span data-ttu-id="82a91-104">BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="82a91-104">BizTalk Server</span></span>
  
-   <span data-ttu-id="82a91-105">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="82a91-105">Visual Studio</span></span>  
  
-   <span data-ttu-id="82a91-106">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="82a91-106">Enterprise Single Sign-On</span></span>  
  
-   <span data-ttu-id="82a91-107">Un sistema de servidor compatible con SSO</span><span class="sxs-lookup"><span data-stu-id="82a91-107">A Server System that supports SSO</span></span>  
  
 <span data-ttu-id="82a91-108">El host aislado debe configurarse como autenticación de confianza.</span><span class="sxs-lookup"><span data-stu-id="82a91-108">The isolated host should be configured as authentication trusted.</span></span>  
  
## <a name="enable-sso"></a><span data-ttu-id="82a91-109">Habilitar SSO</span><span class="sxs-lookup"><span data-stu-id="82a91-109">Enable SSO</span></span>  
  
1.  <span data-ttu-id="82a91-110">En el **propiedades de transporte** ventana, seleccione **Sí** para **usar SSO**.</span><span class="sxs-lookup"><span data-stu-id="82a91-110">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2.  <span data-ttu-id="82a91-111">Al especificar las propiedades del transporte, seleccione una aplicación afiliada adecuada.</span><span class="sxs-lookup"><span data-stu-id="82a91-111">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
 <span data-ttu-id="82a91-112">Para obtener información sobre cómo crear una aplicación afiliada, vea [crear aplicaciones afiliadas](../core/creating-affiliate-applications2.md).</span><span class="sxs-lookup"><span data-stu-id="82a91-112">For information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications2.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82a91-113">Después de trabajar mediante SSO, no olvide restablecer las carpetas de uso compartido de Web en **no comparten**.</span><span class="sxs-lookup"><span data-stu-id="82a91-113">After performing work using SSO, remember to reset any Web-Sharing folder to **Do not share**.</span></span> <span data-ttu-id="82a91-114">Las aplicaciones que usen dichas carpetas no se actualizarán ni se desinstalarán correctamente si la carpeta es de uso compartido, ya que se considerará que están en uso.</span><span class="sxs-lookup"><span data-stu-id="82a91-114">Applications that use that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82a91-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="82a91-115">See Also</span></span>  
 <span data-ttu-id="82a91-116">[Ejecución de proyectos SSO](../core/running-sso-projects1.md) </span><span class="sxs-lookup"><span data-stu-id="82a91-116">[Running SSO Projects](../core/running-sso-projects1.md) </span></span>  
 [<span data-ttu-id="82a91-117">Mediante el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="82a91-117">Using Single Sign-On</span></span>](../core/using-single-sign-on2.md)