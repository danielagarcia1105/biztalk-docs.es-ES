---
title: Validar contraseñas para Host SSO iniciado por | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- passwords, host initiated [SSO]
- host initiated SSO, passwords
ms.assetid: 3cc1d68a-27ac-46ce-ba1e-21139a9df55e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03a33eb83630831863f231ff9594e3082f0faa98
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287860"
---
# <a name="validating-passwords-for-host-initiated-sso"></a>Validar contraseñas para Host SSO iniciado por
Cuando se crea una aplicación afiliada para SSO iniciado por host, la validación de contraseña de usuarios ajenos a Windows está habilitada de forma predeterminada. Esto significa que, cuando las aplicaciones llaman a SSO para obtener el token de usuario de Windows  y tener acceso a los recursos, deben facilitar la contraseña y la cuenta de usuario ajeno a Windows. Si esta contraseña no coincide con la contraseña de usuario ajeno a Windows almacenada en la base de datos de SSO, se denegará el acceso. En caso necesario, la característica de validación de contraseña se puede deshabilitar para la aplicación afiliada. La característica de validación de contraseña se utiliza para las aplicaciones afiliadas de SSO iniciado por host, tanto de grupo de host como individuales.  
  
 Ejemplo de archivo XML para aplicación afiliada de SSO iniciado por host de tipo individual:  
  
```  
<sso>  
<application name="SAP">  
<description>The SAP application</description>   
<contact>someone@example.com</contact>   
<appuserAccount>domain\AppUserGroupAccount</appuserAccount>   
<appAdminAccount>domain\AppAdminGroupAccount</appAdminAccount>   
<field ordinal="0" label="User Id" masked="no" />   
<field ordinal="1" label="Password" masked="yes" />   
<flags groupApp="no"  configStoreApp="no" allowTickets="no" validateTickets="yes" allowLocalAccounts="no" timeoutTickets="yes" adminAccountSame="no" enableApp="no" />  
</application>  
</sso>  
  
```  
  
 En el caso de aplicaciones individuales de SSO iniciado por host, appUserAccount es una cuenta de grupo que contiene la lista de usuarios de dominio de Windows, con una asignación 1 a 1 con su correspondiente cuenta de usuario ajeno a Windows.  
  
 Ejemplo de archivo XML para aplicación afiliada de SSO iniciado por host de tipo grupo de host:  
  
```  
<sso>  
<application name="SAP">  
<description>The SAP application</description>   
<contact>someone@example.com</contact>   
<appuserAccount>domain\AppUserAccount</appuserAccount>   
<appAdminAccount>domain\AppAdminGroupAccount</appAdminAccount>   
<field ordinal="0" label="User Id" masked="no" />   
<field ordinal="1" label="Password" masked="yes" />   
<flags  configStoreApp="no" allowTickets="no" validateTickets="yes" allowLocalAccounts="no" timeoutTickets="yes" adminAccountSame="no" enableApp="no" />  
</application>  
</sso>  
  
```  
  
 En aplicaciones de grupo de SSO iniciado por host, appUserAccount deberá ser una cuenta de usuario individual. A esta cuenta se asignarán todas las cuentas ajenas a Windows.  
  
## <a name="see-also"></a>Vea también  
 [SSO iniciado por host](../core/host-initiated-sso.md)