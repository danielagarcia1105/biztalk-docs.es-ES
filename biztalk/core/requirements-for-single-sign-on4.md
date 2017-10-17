---
title: "Requisitos para el inicio de sesión único | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 645c7b3f-f860-4c20-b5ca-a8fb93736344
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98d5164fa194f9a02314b897b267d9873879a9c0
ms.sourcegitcommit: 6b6d905bbef7796c850178e99ac293578bb58317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2017
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="f2e7f-102">Requisitos para el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="f2e7f-102">Requirements for Single Sign-On</span></span>
<span data-ttu-id="f2e7f-103">El Adaptador de Microsoft BizTalk para TIBCO Enterprise Message Service (EMS) proporciona compatibilidad con inicio de sesión único (SSO).</span><span class="sxs-lookup"><span data-stu-id="f2e7f-103">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) provides Single Sign-On (SSO) support.</span></span> <span data-ttu-id="f2e7f-104">Una aplicación afiliada, creada por herramientas de Inicio de sesión único de la empresa, representa un sistema de servidor como TBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="f2e7f-104">An affiliate application created by Enterprise Single Sign-On tools represents a server system such as TIBCO EMS.</span></span>  
  
 <span data-ttu-id="f2e7f-105">Para usar el inicio de sesión único (SSO), debe tener:</span><span class="sxs-lookup"><span data-stu-id="f2e7f-105">To use Single Sign-On, you must have:</span></span>  
  
-   <span data-ttu-id="f2e7f-106">Microsoft BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f2e7f-106">Microsoft BizTalk Server</span></span>
  
-   <span data-ttu-id="f2e7f-107">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f2e7f-107">Visual Studio</span></span>  
  
-   <span data-ttu-id="f2e7f-108">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="f2e7f-108">Enterprise Single Sign-On</span></span>  
  
-   <span data-ttu-id="f2e7f-109">Un sistema de servidor que admite el SSO</span><span class="sxs-lookup"><span data-stu-id="f2e7f-109">A server system that supports SSO</span></span>  
  
 <span data-ttu-id="f2e7f-110">El host aislado debe estar configurado como con autenticación de confianza.</span><span class="sxs-lookup"><span data-stu-id="f2e7f-110">The isolated host should be configured as authentication trusted</span></span>  
  
## <a name="enable-sso"></a><span data-ttu-id="f2e7f-111">Habilitar SSO</span><span class="sxs-lookup"><span data-stu-id="f2e7f-111">Enable SSO</span></span>  
  
1.  <span data-ttu-id="f2e7f-112">En el **propiedades de transporte** ventana, seleccione **Sí** para **usar SSO**.</span><span class="sxs-lookup"><span data-stu-id="f2e7f-112">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2.  <span data-ttu-id="f2e7f-113">Al especificar las propiedades del transporte, seleccione una aplicación afiliada adecuada.</span><span class="sxs-lookup"><span data-stu-id="f2e7f-113">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
     <span data-ttu-id="f2e7f-114">Para obtener información sobre cómo crear una aplicación afiliada, vea [crear aplicaciones afiliadas](../core/creating-affiliate-applications5.md).</span><span class="sxs-lookup"><span data-stu-id="f2e7f-114">For information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications5.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f2e7f-115">Después de trabajar mediante SSO, no olvide restablecer las carpetas de uso compartido de Web en **no comparten**.</span><span class="sxs-lookup"><span data-stu-id="f2e7f-115">After performing work using SSO, remember to reset any Web-Sharing folder to **Do not share**.</span></span> <span data-ttu-id="f2e7f-116">Las aplicaciones que usen dichas carpetas no se actualizarán ni se desinstalarán correctamente si la carpeta es de uso compartido, ya que se considerará que están en uso.</span><span class="sxs-lookup"><span data-stu-id="f2e7f-116">Applications that use that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2e7f-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2e7f-117">See Also</span></span>  
 [<span data-ttu-id="f2e7f-118">Mediante el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="f2e7f-118">Using Single Sign-On</span></span>](../core/using-single-sign-on4.md)