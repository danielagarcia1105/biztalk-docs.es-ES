---
title: "Requisitos para el inicio de sesión único-EL4 | Documentos de Microsoft"
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
ms.assetid: 645c7b3f-f860-4c20-b5ca-a8fb93736344
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15d7bdbf52869e5b13ae113716689bbb5b7ffec3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="dbc2d-102">Requisitos para el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="dbc2d-102">Requirements for Single Sign-On</span></span>
<span data-ttu-id="dbc2d-103">El Adaptador de Microsoft BizTalk para TIBCO Enterprise Message Service (EMS) proporciona compatibilidad con inicio de sesión único (SSO).</span><span class="sxs-lookup"><span data-stu-id="dbc2d-103">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) provides Single Sign-On (SSO) support.</span></span> <span data-ttu-id="dbc2d-104">Una aplicación afiliada, creada por herramientas de Inicio de sesión único de la empresa, representa un sistema de servidor como TBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="dbc2d-104">An affiliate application created by Enterprise Single Sign-On tools represents a server system such as TIBCO EMS.</span></span>  
  
 <span data-ttu-id="dbc2d-105">Para usar el inicio de sesión único (SSO), debe tener:</span><span class="sxs-lookup"><span data-stu-id="dbc2d-105">To use Single Sign-On, you must have:</span></span>  
  
-   <span data-ttu-id="dbc2d-106">Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbc2d-106">Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]</span></span>  
  
-   [!INCLUDE[vs2010](../includes/vs2010-md.md)]  
  
-   <span data-ttu-id="dbc2d-107">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="dbc2d-107">Enterprise Single Sign-On</span></span>  
  
-   <span data-ttu-id="dbc2d-108">Un sistema de servidor que admite el SSO</span><span class="sxs-lookup"><span data-stu-id="dbc2d-108">A server system that supports SSO</span></span>  
  
 <span data-ttu-id="dbc2d-109">El host aislado debe estar configurado como con autenticación de confianza.</span><span class="sxs-lookup"><span data-stu-id="dbc2d-109">The isolated host should be configured as authentication trusted</span></span>  
  
### <a name="to-enable-sso"></a><span data-ttu-id="dbc2d-110">Para habilitar SSO</span><span class="sxs-lookup"><span data-stu-id="dbc2d-110">To enable SSO</span></span>  
  
1.  <span data-ttu-id="dbc2d-111">En el **propiedades de transporte** ventana, seleccione **Sí** para **usar SSO**.</span><span class="sxs-lookup"><span data-stu-id="dbc2d-111">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2.  <span data-ttu-id="dbc2d-112">Al especificar las propiedades del transporte, seleccione una aplicación afiliada adecuada.</span><span class="sxs-lookup"><span data-stu-id="dbc2d-112">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
     <span data-ttu-id="dbc2d-113">Para obtener información sobre cómo crear una aplicación afiliada, vea [crear aplicaciones afiliadas](../core/creating-affiliate-applications5.md).</span><span class="sxs-lookup"><span data-stu-id="dbc2d-113">For information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications5.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dbc2d-114">Después de trabajar mediante SSO, no olvide restablecer las carpetas de uso compartido de Web en **no comparten**.</span><span class="sxs-lookup"><span data-stu-id="dbc2d-114">After performing work using SSO, remember to reset any Web-Sharing folder to **Do not share**.</span></span> <span data-ttu-id="dbc2d-115">Las aplicaciones que usen dichas carpetas no se actualizarán ni se desinstalarán correctamente si la carpeta es de uso compartido, ya que se considerará que están en uso.</span><span class="sxs-lookup"><span data-stu-id="dbc2d-115">Applications that use that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbc2d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="dbc2d-116">See Also</span></span>  
 [<span data-ttu-id="dbc2d-117">Mediante el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="dbc2d-117">Using Single Sign-On</span></span>](../core/using-single-sign-on4.md)