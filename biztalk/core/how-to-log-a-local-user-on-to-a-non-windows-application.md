---
title: Cómo registrar un usuario Local en una aplicación distinta de Windows | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b55957f4-22c4-48b5-827a-ab41d8f846ac
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3c2e9ffaede20e29987938a436ad2a091920fce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22253876"
---
# <a name="how-to-log-a-local-user-on-to-a-non-windows-application"></a>Cómo registrar un usuario Local en una aplicación distinta de Windows
Una vez configurado el usuario con una aplicación afiliada, puede usar el inicio de sesión único (SSO) para obtener acceso a las credenciales y al nombre de usuario externos del usuario actual. Con estas credenciales, el usuario puede iniciar sesión en la aplicación afiliada que se ejecuta en un servidor de host.  
  
> [!NOTE]
>  Además de establecer los protocolos de seguridad pertinentes para SSO, puede que sea necesario establecer seguridad adicional para permitir que la aplicación llame a SSO en el contexto de seguridad adecuado. Si la aplicación no puede llamar a SSO en el contexto de seguridad adecuado, SSO denegará el acceso a la aplicación.  
  
### <a name="to-set-the-security-context-for-an-sso-application"></a>Para establecer el contexto de seguridad de una aplicación de SSO  
  
1.  Identifique las credenciales necesarias para que la aplicación se ejecute correctamente.  
  
     Por ejemplo, una aplicación que usa servicios web o comunicación remota de .NET Framework hospedada en IIS necesita suplantar al cliente para transferir las credenciales adecuadas a SSO.  
  
2.  Confirme que la configuración de seguridad relevante, como la de los directorios virtuales, grupos de aplicaciones y archivos web.config, se establece de forma que se proporcione a la aplicación dichas credenciales.  
  
     Para obtener más información acerca de cómo establecer las credenciales de seguridad, consulte [Building Secure ASP.NET Applications: autenticación, autorización y comunicación segura](http://go.microsoft.com/fwlink/?LinkId=193906).  
  
     Para obtener más información acerca de la transferencia de credenciales a un servicio Web ASP.NET, vea [HOW TO: pasar credenciales actuales para un servicio Web ASP.NET](http://go.microsoft.com/fwlink/?LinkId=193907).  
  
### <a name="to-log-a-local-user-on-to-a-host-application"></a>Para hacer que un usuario local inicie sesión en una aplicación de host  
  
1.  Espere a recibir la solicitud para hacer que el usuario actual inicie sesión en una aplicación que se esté ejecutando en el servidor de host.  
  
     Es responsabilidad suya determinar cómo el usuario actual solicita el inicio de sesión en una aplicación de host.  
  
2.  Recuperar las credenciales del usuario actual que está usando `ISSOLookup1.GetCredentials` o `ISSOLookup2.GetCredentials`.  
  
     Debe proporcionar el nombre de la aplicación de host junto con cualquier marca pertinente. `GetCredentials`Devuelve el nombre de usuario asociado y las credenciales de la aplicación host.  
  
     Tenga en cuenta que puede usar `ISSOLookup1` o `ISSOLookup2`. La única diferencia es que `ISSOLookup2` también tiene un método para registrar un usuario remoto en una aplicación de windows local.  
  
3.  Utilice las credenciales y el nombre de usuario externos para iniciar sesión en la aplicación de host.  
  
     Es responsabilidad suya determinar cómo utilizar las credenciales para iniciar sesión en la aplicación de host.  
  
## <a name="see-also"></a>Vea también  
 [Cómo registrar un usuario remoto en una aplicación Local](../core/how-to-log-a-remote-user-on-to-a-local-application.md)