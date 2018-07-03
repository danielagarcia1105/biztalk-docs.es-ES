---
title: Cómo configurar los requisitos de Host SSO iniciado por | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service accounts, granting privileges [SSO]
- host initiated SSO, configuring
- domain function level [SSO]
- host initiated SSO, Transaction Integrator (TI)
- SPN [SSO]
- managing [SSO], granting TCB privileges
- Transaction Integrator (TI)
- host initiated SSO, SPN
- host initiated SSO, TCB privileges
- configuring, host initiated SSO
- creating, SPNs [SSO]
- TCB privileges [SSO]
- managing [SSO], host initiated
- host initiated SSO, domain function level
- service accounts, SSO
- SSO, host initiated
- managing [SSO], creating SPNs
- SSO, service accounts
ms.assetid: 91d77c9f-bab2-4f6e-8bce-e31c59cebb20
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 829deaba6782cb6e72f004c4fa96a6f8e2831be4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982829"
---
# <a name="how-to-configure-requirements-for-host-initiated-sso"></a>Cómo configurar requisitos para SSO iniciado por host
Si bien SSO empresarial y SSO iniciado por host tiene determinados aspectos en común, algunos requisitos de plataforma y Active Directory son únicos de SSO iniciado por host. Este tema trata esos requisitos y enumera los pasos para comprobarlos o crearlos en el sistema.  
  
- SSO iniciado por host se puede ejecutar solo en un entorno de dominio de Windows Server 2008 nativo.  
  
- La cuenta de servicio SSO que lleva a cabo SSO iniciado por host debe estar configurada con privilegios TCB. Puede configurar esto para la cuenta de servicio en la directiva de seguridad del dominio.  
  
  Además, son necesarios determinados requisitos cuando se usa Transaction Integrator para el procesamiento iniciado por host. TI for HIP aprovecha SSO iniciado por host para lograr inicio de sesión único para usuarios que no son de Windows.  
  
  Por ejemplo, la cuenta de servicio de TI for HIP se ejecuta con una cuenta de dominio domainname\hipsvc. Este servicio puede alojar aplicaciones que desean obtener acceso a recursos remotos o locales en Windows con la cuenta de Windows que corresponde a la cuenta que no es de Windows.  
  
  La cuenta domainname\hipsvc debe pertenecer a la cuenta del grupo de administradores de aplicación para la aplicación afiliada que se usa para el inicio de sesión único.  
  
  La cuenta domainname\hipsvc debe tener privilegios de delegación restringida para usar el inicio de sesión único iniciado por host. Esto lo puede configurar el administrador del dominio en Active Directory. Se puede configurar delegación para las cuentas que tienen SPN registrados. La delegación restringida permite a la cuenta de servicio obtener acceso sólo a los componentes que especifica el administrador.  
  
### <a name="to-check-your-domain-function-level"></a>Para comprobar su nivel funcional del dominio  
  
1.  En su **dominios de Active Directory y las confianzas** complemento de MMC, derecho, haga clic en el nodo **dominios de Active Directory y las confianzas**y, a continuación, haga clic en **elevar el nivel funcional del bosque**.  
  
2.  Compruebe que el nivel funcional es **Windows Server 2008**. Si no es así, consulte la documentación de Active Directory antes de intentar cambiar esta configuración.  
  
### <a name="to-create-an-spn"></a>Para crear un SPN  
  
1. Descargue el **setspn** utilidad en la siguiente ubicación: [ http://go.microsoft.com/fwlink/?LinkId=33178 ](http://go.microsoft.com/fwlink/?LinkId=33178).  
  
2. En el menú **Inicio** , haga clic en **Ejecutar**.  
  
3. En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.  
  
4. En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
5. Tipo **setpsn - a hipsvc\computername.domain.com domain\hissvc**  
  
    donde **hipsvc\computername.domain.com** es el servicio que se llevará a cabo la operación y el equipo se está ejecutando, y **domain\hissvc** es la cuenta de servicio para hipsvc.  
  
   Tras hacer esto, puede configurar la delegación restringida en Active Directory para que esta cuenta de servicio (domain\hissvc) tenga acceso al recurso correspondiente en la red.  
  
#### <a name="to-give-tcb-privileges-for-the-sso-service-account"></a>Para conceder a TCB privilegios para la cuenta de servicio SSO  
  
-   En su **directiva de seguridad de dominio - directivas locales - asignación de derechos de usuario**, agregue la cuenta de servicio de inicio de sesión único para el **actuar como parte del sistema operativo** directiva.  
  
     Para obtener más información acerca de la transición del protocolo Kerberos y delegación restringida, vaya a [ http://go.microsoft.com/fwlink/?LinkId=195484 ](http://go.microsoft.com/fwlink/?LinkId=195484).  
  
## <a name="see-also"></a>Vea también  
 [SSO iniciado por host](../core/host-initiated-sso.md)