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
# <a name="how-to-configure-single-sign-on"></a>Cómo configurar el inicio de sesión único
Antes de obtener acceso al inicio de sesión único (SSO) empresarial, debería estar seguro de que se ha configurado correctamente para el usuario actual. Para la mayoría de las configuraciones, use uno de dos interfaces. `ISSOAdmin` es la interfaz de administración general que le permite crear nuevas aplicaciones afiliadas. Sin embargo, si usa ISSOAdmin.GetGlobalInfo e ISSOAdmin.UpdateGlobalInfo, puede establecer una serie de valores de administración y marcas. Una posible tarea, como se describe en el procedimiento siguiente, consiste en asegurarse de que se ha habilitado la compra de vales SSO.  
  
### <a name="to-enable-ticketing"></a>Para habilitar la compra de vales  
  
1. Cree una nueva instancia de `ISSOAdmin`.  
  
2. Recupere la configuración actual mediante `ISSOAdmin.GetGlobalInfo`.  
  
    En caso necesario, es posible que desee confirmar que las marcas están establecidas en los valores correctos en este punto.  
  
3. Cambie cualquier marca pertinente mediante `ISSOAdmin.UpdateGlobalInfo`.  
  
    En este caso particular, todas las marcas se establecen para validar y habilitar vales.  
  
   En el siguiente ejemplo se muestra cómo habilitar la compra de vales mediante el inicio de sesión único (SSO).  
  
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
  
## <a name="see-also"></a>Vea también  
 [Programación con Enterprise Single Sign-On](../core/programming-with-enterprise-single-sign-on.md)