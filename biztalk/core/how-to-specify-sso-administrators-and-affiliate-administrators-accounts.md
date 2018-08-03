---
title: Cómo especificar administradores de SSO y los administradores afiliados de cuentas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- administrator accounts, SSO
- enabling, SSO
- SSO, enabling
- disabling, SSO
- SSO, disabling
- managing [SSO], configuring administrator accounts
- managing [SSO], enabling
- managing [SSO], disabling
- SSO, administrator accounts
ms.assetid: 6c300e09-b781-45de-b2da-b1083164a1c0
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab6a40db19ae42f0ba4007fd8044d7d7aa086adb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968245"
---
# <a name="how-to-specify-sso-administrators-and-affiliate-administrators-accounts"></a>Cómo especificar administradores de SSO y los administradores afiliados de cuentas
Las cuentas de administradores de inicio de sesión único (SSO) empresarial y las cuentas de administradores afiliados pueden ser individuales o de grupo de hosts. Debe crear estas cuentas antes de configurar el sistema de SSO.  
  
 Cuando utilice cuentas de dominio, deberá crear cuentas de administradores de SSO y cuentas de administradores afiliados como grupos de seguridad de dominio globales en el controlador de dominio. Es el administrador de dominio quien debe crear estas cuentas.  
  
 Debe especificar las cuentas de administradores de SSO y las cuentas de administradores afiliados en la base de datos de SSO. Deberá deshabilitar el sistema de SSO antes de actualizar la base de datos SSO con el grupo de administradores de SSO.  
  
 El código XML siguiente muestra un ejemplo de XML para actualizar la base de datos de SSO:  
  
```  
<sso>  
<globalInfo>  
<ssoAdminAccount>Domain\Accountname</ssoAdminAccount>  
<ssoAffiliateAdminAccount>Domain\Accountname</ssoAffiliateAdminAccount>  
</globalInfo>  
</sso>  
```  
  
> [!NOTE]
>  El Asistente para configuración especifica el grupo de administradores de SSO y el grupo de administradores afiliados en la base de datos de SSO.  
  
> [!NOTE]
>  Si SSO no se configura, los usuarios deben comprobar si las cuentas de dominio local se van a usar en un dominio de modo combinado.  
  
### <a name="to-disable-the-enterprise-single-sign-on-system-using-the-mmc-snap-in"></a>Para deshabilitar el sistema de inicio de sesión único empresarial utilizando el Complemento MMC  
  
1.  En el **iniciar** menú, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.  
  
2.  En el panel de ámbito del complemento MMC de ENTSSO, expanda el **Enterprise Single Sign-On** nodo.  
  
3.  Haga clic en **sistema**y, a continuación, haga clic en **deshabilitar**.  
  
### <a name="to-disable-the-enterprise-single-sign-on-system-using-the-command-line"></a>Para deshabilitar el sistema de inicio de sesión único empresarial utilizando la línea de comandos  
  
1.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es \< *unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo **ssomanage** –**disablesso**.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
### <a name="to-update-the-sso-database-using-the-mmc-snap-in"></a>Para actualizar la base de datos de SSO utilizando el Complemento MMC  
  
1.  En el **iniciar** menú, haga clic en **todos los programas**, **Microsoft Enterprise Single Sign-On**y, a continuación, **administración de SSO**.  
  
2.  En el panel de ámbito del complemento MMC de ENTSSO, expanda el **Enterprise Single Sign-On** nodo.  
  
3.  Haga clic en **sistema**y, a continuación, haga clic en **actualización**.  
  
### <a name="to-update-the-sso-database-using-the-command-line"></a>Para actualizar la base de datos de SSO utilizando la línea de comandos  
  
1. En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2. En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  *\<unidad\>*: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3. Tipo ** ssomanage – updatedb *\<archivo de actualización\>**<em>, donde *\<archivo de actualización\></em>  es la ruta de acceso y nombre del archivo XML.  
  
   > [!NOTE]
   >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
### <a name="to-enable-the-enterprise-single-sign-on-system-using-the-mmc-snap-in"></a>Para habilitar el sistema de inicio de sesión único empresarial utilizando el Complemento MMC  
  
1.  En el **iniciar** menú, haga clic en **todos los programas**, **Microsoft Enterprise Single Sign-On**y, a continuación, **administración de SSO**.  
  
2.  En el panel de ámbito del complemento MMC de ENTSSO, expanda el **Enterprise Single Sign-On** nodo.  
  
3.  Haga clic en **sistema**y, a continuación, haga clic en **habilitar**.  
  
### <a name="to-enable-the-enterprise-single-sign-on-system-using-the-command-line"></a>Para habilitar el sistema de inicio de sesión único empresarial utilizando la línea de comandos  
  
1.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  *\<unidad\>*: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo **ssomanage – enablesso**.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Grupos de usuarios de SSO](../core/sso-user-groups.md)