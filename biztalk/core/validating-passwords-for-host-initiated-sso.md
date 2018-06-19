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
# <a name="validating-passwords-for-host-initiated-sso"></a><span data-ttu-id="1e825-102">Validar contraseñas para Host SSO iniciado por</span><span class="sxs-lookup"><span data-stu-id="1e825-102">Validating Passwords for Host Initiated SSO</span></span>
<span data-ttu-id="1e825-103">Cuando se crea una aplicación afiliada para SSO iniciado por host, la validación de contraseña de usuarios ajenos a Windows está habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1e825-103">When an affiliate application for host initiated SSO is created, password validation for the non-Windows user is enabled by default.</span></span> <span data-ttu-id="1e825-104">Esto significa que, cuando las aplicaciones llaman a SSO para obtener el token de usuario de Windows  y tener acceso a los recursos, deben facilitar la contraseña y la cuenta de usuario ajeno a Windows.</span><span class="sxs-lookup"><span data-stu-id="1e825-104">This means when applications call SSO to obtain the Windows user token to access resources, they must provide the non-Windows user account and the non-Windows password.</span></span> <span data-ttu-id="1e825-105">Si esta contraseña no coincide con la contraseña de usuario ajeno a Windows almacenada en la base de datos de SSO, se denegará el acceso.</span><span class="sxs-lookup"><span data-stu-id="1e825-105">If the password does not match the password in the SSO database for that non-Windows user, access is denied.</span></span> <span data-ttu-id="1e825-106">En caso necesario, la característica de validación de contraseña se puede deshabilitar para la aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="1e825-106">If necessary, the password validation feature can be disabled for the affiliate application.</span></span> <span data-ttu-id="1e825-107">La característica de validación de contraseña se utiliza para las aplicaciones afiliadas de SSO iniciado por host, tanto de grupo de host como individuales.</span><span class="sxs-lookup"><span data-stu-id="1e825-107">The password validation feature applies to both individual and host group type affiliate applications for host initiated SSO.</span></span>  
  
 <span data-ttu-id="1e825-108">Ejemplo de archivo XML para aplicación afiliada de SSO iniciado por host de tipo individual:</span><span class="sxs-lookup"><span data-stu-id="1e825-108">An example XML file for Individual type host initiated SSO affiliate application is:</span></span>  
  
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
  
 <span data-ttu-id="1e825-109">En el caso de aplicaciones individuales de SSO iniciado por host, appUserAccount es una cuenta de grupo que contiene la lista de usuarios de dominio de Windows, con una asignación 1 a 1 con su correspondiente cuenta de usuario ajeno a Windows.</span><span class="sxs-lookup"><span data-stu-id="1e825-109">In the case of individual applications for host initiated SSO, the appUserAccount is a group account that contains the list of Windows domain account users that have a 1 to 1 mapping with their corresponding non-Windows accounts.</span></span>  
  
 <span data-ttu-id="1e825-110">Ejemplo de archivo XML para aplicación afiliada de SSO iniciado por host de tipo grupo de host:</span><span class="sxs-lookup"><span data-stu-id="1e825-110">An example XML file for host group type host initiated SSO affiliate application is:</span></span>  
  
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
  
 <span data-ttu-id="1e825-111">En aplicaciones de grupo de SSO iniciado por host, appUserAccount deberá ser una cuenta de usuario individual.</span><span class="sxs-lookup"><span data-stu-id="1e825-111">In group applications for host initiated SSO, the appUserAccount must be an individual user account.</span></span> <span data-ttu-id="1e825-112">A esta cuenta se asignarán todas las cuentas ajenas a Windows.</span><span class="sxs-lookup"><span data-stu-id="1e825-112">It is this account that all non-Windows accounts are mapped to.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e825-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e825-113">See Also</span></span>  
 [<span data-ttu-id="1e825-114">SSO iniciado por host</span><span class="sxs-lookup"><span data-stu-id="1e825-114">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)