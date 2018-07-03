---
title: Cómo configurar el inicio de sesión único | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 511edc1d-de82-4d17-88ea-6cacfccde10d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b23e2bb61f4549e642bcd9a59f56bc232b40038
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019939"
---
# <a name="how-to-configure-single-sign-on"></a><span data-ttu-id="2b7a1-102">Cómo configurar el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="2b7a1-102">How to Configure Single Sign-On</span></span>
<span data-ttu-id="2b7a1-103">Antes de obtener acceso al inicio de sesión único (SSO) empresarial, debería estar seguro de que se ha configurado correctamente para el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="2b7a1-103">Before accessing Enterprise Single Sign-On, you should make sure that Enterprise Single Sign-On is set correctly for the current user.</span></span> <span data-ttu-id="2b7a1-104">Para la mayoría de las configuraciones, use uno de dos interfaces.</span><span class="sxs-lookup"><span data-stu-id="2b7a1-104">For most configurations, you use one of two interfaces.</span></span> <span data-ttu-id="2b7a1-105">`ISSOAdmin` es la interfaz de administración general que le permite crear nuevas aplicaciones afiliadas.</span><span class="sxs-lookup"><span data-stu-id="2b7a1-105">`ISSOAdmin` is the general administration interface that enables you to create new affiliation applications.</span></span> <span data-ttu-id="2b7a1-106">Sin embargo, si usa ISSOAdmin.GetGlobalInfo e ISSOAdmin.UpdateGlobalInfo, puede establecer una serie de valores de administración y marcas.</span><span class="sxs-lookup"><span data-stu-id="2b7a1-106">However, by using ISSOAdmin.GetGlobalInfo and ISSOAdmin.UpdateGlobalInfo, you can set a variety of flags and administration values.</span></span> <span data-ttu-id="2b7a1-107">Una posible tarea, como se describe en el procedimiento siguiente, consiste en asegurarse de que se ha habilitado la compra de vales SSO.</span><span class="sxs-lookup"><span data-stu-id="2b7a1-107">One possible task, as described in the following procedure, is to ensure that SSO ticketing has been enabled.</span></span>  
  
### <a name="to-enable-ticketing"></a><span data-ttu-id="2b7a1-108">Para habilitar la compra de vales</span><span class="sxs-lookup"><span data-stu-id="2b7a1-108">To enable ticketing</span></span>  
  
1. <span data-ttu-id="2b7a1-109">Cree una nueva instancia de `ISSOAdmin`.</span><span class="sxs-lookup"><span data-stu-id="2b7a1-109">Create a new instance of `ISSOAdmin`.</span></span>  
  
2. <span data-ttu-id="2b7a1-110">Recupere la configuración actual mediante `ISSOAdmin.GetGlobalInfo`.</span><span class="sxs-lookup"><span data-stu-id="2b7a1-110">Retrieve the current settings through `ISSOAdmin.GetGlobalInfo`.</span></span>  
  
    <span data-ttu-id="2b7a1-111">En caso necesario, es posible que desee confirmar que las marcas están establecidas en los valores correctos en este punto.</span><span class="sxs-lookup"><span data-stu-id="2b7a1-111">If necessary, you may want to confirm that the flags are set to the correct values at this point.</span></span>  
  
3. <span data-ttu-id="2b7a1-112">Cambie cualquier marca pertinente mediante `ISSOAdmin.UpdateGlobalInfo`.</span><span class="sxs-lookup"><span data-stu-id="2b7a1-112">Change any relevant flags using `ISSOAdmin.UpdateGlobalInfo`.</span></span>  
  
    <span data-ttu-id="2b7a1-113">En este caso particular, todas las marcas se establecen para validar y habilitar vales.</span><span class="sxs-lookup"><span data-stu-id="2b7a1-113">In this particular case, all the flags are being set to validate and enable tickets.</span></span>  
  
   <span data-ttu-id="2b7a1-114">En el siguiente ejemplo se muestra cómo habilitar la compra de vales mediante el inicio de sesión único (SSO).</span><span class="sxs-lookup"><span data-stu-id="2b7a1-114">The following example shows how to enable ticketing using Single Sign-On.</span></span>  
  
```  
public static bool EnableTickets()  
{  
   try  
   {  
      ISSOAdmin admin=new ISSOAdmin();  
      int flags=0;  
      int appDeleteMax=1000;  
      int mappingDeleteMax=1000;  
      int ntpLookupMax=-1000;  
      int xplLookupMax=-1000;  
      int ticketTimeout=2;  
      int cacheTimeout=60;  
      string secretServer=null;  
      string ssoAdminGroup=null;  
      string affiliateAppMgrGroup=null;  
      // Get current default settings.  
      admin.GetGlobalInfo(out flags, out appDeleteMax, out mappingDeleteMax, out ntpLookupMax, out xplLookupMax, out ticketTimeout, out cacheTimeout, out secretServer, out ssoAdminGroup, out affiliateAppMgrGroup);  
      // Update global settings.  
      admin.UpdateGlobalInfo(SSOFlag.SSO_FLAG_ALLOW_TICKETS | SSOFlag.SSO_FLAG_VALIDATE_TICKETS, SSOFlag.SSO_FLAG_ALLOW_TICKETS | SSOFlag.SSO_FLAG_VALIDATE_TICKETS, ref appDeleteMax, ref mappingDeleteMax, ref ntpLookupMax, ref xplLookupMax, ref ticketTimeout, ref cacheTimeout, null, null, null);   
   }  
   catch  
   {  
      return false;  
   }  
return true;  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="2b7a1-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b7a1-115">See Also</span></span>  
 [<span data-ttu-id="2b7a1-116">Programación con Enterprise Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="2b7a1-116">Programming with Enterprise Single Sign-On</span></span>](../core/programming-with-enterprise-single-sign-on.md)