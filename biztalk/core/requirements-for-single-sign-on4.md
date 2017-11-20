---
title: Requisitos de SSO para el adaptador TIBCO EMS | Documentos de Microsoft
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
ms.openlocfilehash: 805d14e056da665f8828ce0244f28ed9adc40ff4
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="bedc6-102">Requisitos para el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="bedc6-102">Requirements for Single Sign-On</span></span>

## <a name="overview"></a><span data-ttu-id="bedc6-103">Información general</span><span class="sxs-lookup"><span data-stu-id="bedc6-103">Overview</span></span>
<span data-ttu-id="bedc6-104">El Adaptador de Microsoft BizTalk para TIBCO Enterprise Message Service (EMS) proporciona compatibilidad con inicio de sesión único (SSO).</span><span class="sxs-lookup"><span data-stu-id="bedc6-104">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) provides Single Sign-On (SSO) support.</span></span> <span data-ttu-id="bedc6-105">Una aplicación afiliada, creada por herramientas de Inicio de sesión único de la empresa, representa un sistema de servidor como TBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="bedc6-105">An affiliate application created by Enterprise Single Sign-On tools represents a server system such as TIBCO EMS.</span></span>  
  
 <span data-ttu-id="bedc6-106">Para usar el inicio de sesión único (SSO), debe tener:</span><span class="sxs-lookup"><span data-stu-id="bedc6-106">To use Single Sign-On, you must have:</span></span>  
  
-   <span data-ttu-id="bedc6-107">Microsoft BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="bedc6-107">Microsoft BizTalk Server</span></span>
  
-   <span data-ttu-id="bedc6-108">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bedc6-108">Visual Studio</span></span>  
  
-   <span data-ttu-id="bedc6-109">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="bedc6-109">Enterprise Single Sign-On</span></span>  
  
-   <span data-ttu-id="bedc6-110">Un sistema de servidor que admite el SSO</span><span class="sxs-lookup"><span data-stu-id="bedc6-110">A server system that supports SSO</span></span>  
  
 <span data-ttu-id="bedc6-111">El host aislado debe configurarse como autenticación de confianza.</span><span class="sxs-lookup"><span data-stu-id="bedc6-111">The isolated host should be configured as authentication trusted.</span></span>
  
## <a name="enable-sso"></a><span data-ttu-id="bedc6-112">Habilitar SSO</span><span class="sxs-lookup"><span data-stu-id="bedc6-112">Enable SSO</span></span>  
  
1.  <span data-ttu-id="bedc6-113">En el **propiedades de transporte** ventana, seleccione **Sí** para **usar SSO**.</span><span class="sxs-lookup"><span data-stu-id="bedc6-113">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2.  <span data-ttu-id="bedc6-114">Al especificar las propiedades del transporte, seleccione una aplicación afiliada adecuada.</span><span class="sxs-lookup"><span data-stu-id="bedc6-114">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
     <span data-ttu-id="bedc6-115">Para obtener información sobre cómo crear una aplicación afiliada, vea [crear aplicaciones afiliadas](../core/creating-affiliate-applications5.md).</span><span class="sxs-lookup"><span data-stu-id="bedc6-115">For information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications5.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bedc6-116">Después de trabajar mediante SSO, no olvide restablecer las carpetas de uso compartido de Web en **no comparten**.</span><span class="sxs-lookup"><span data-stu-id="bedc6-116">After performing work using SSO, remember to reset any Web-Sharing folder to **Do not share**.</span></span> <span data-ttu-id="bedc6-117">Las aplicaciones que usen dichas carpetas no se actualizarán ni se desinstalarán correctamente si la carpeta es de uso compartido, ya que se considerará que están en uso.</span><span class="sxs-lookup"><span data-stu-id="bedc6-117">Applications that use that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bedc6-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="bedc6-118">See Also</span></span>  
[<span data-ttu-id="bedc6-119">Proteger el adaptador</span><span class="sxs-lookup"><span data-stu-id="bedc6-119">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-tibco-ems.md)