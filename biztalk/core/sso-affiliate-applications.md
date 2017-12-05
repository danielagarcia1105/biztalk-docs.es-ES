---
title: Aplicaciones afiliadas de SSO | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO, designing applications
- applications [SSO], application types
- SSO, application types
- SSO, application properties
- applications [SSO], properties
- applications [SSO]
- SSO, applications
- applications [SSO], designing
ms.assetid: 002ecf7e-4d52-425a-9498-0e7bd6545047
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1621973fed0c7a87538e3ed18161f05c4c9cf9e6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="sso-affiliate-applications"></a>Aplicaciones afiliadas de SSO
Las aplicaciones afiliadas de Inicio de sesión único (SSO) empresarial son entidades lógicas que representan un sistema o subsistema, como un host, un sistema back-end o una línea de aplicación empresarial, a los que se conecta mediante SSO. Una aplicación afiliada puede representar un sistema back-end, como un equipo UNIX o gran sistema. También puede representar una aplicación, como SAP o una subdivisión del sistema, como los subsistemas "Beneficios" o "Recibos de pago".  
  
 Cuando el administrador de SSO o el administrador afiliado de SSO define una aplicación afiliada, también debe determinar quién administrará la aplicación afiliada (el administrador de aplicación), quiénes serán los usuarios de la aplicación afiliada (los usuarios de aplicación) y qué parámetros utilizará el sistema de SSO para autenticar los usuarios de la aplicación afiliada (el Id. de usuario, las contraseñas, los números PIN, etc.). Para obtener más información acerca de los administradores de aplicaciones y usuarios de la aplicación, consulte [grupos de usuarios de SSO](../core/sso-user-groups.md).  
  
## <a name="affiliate-application-types"></a>Tipos de aplicación afiliada  
 El SSO empresarial define varios tipos de aplicación diferentes. Los distintos tipos de aplicación admiten diferentes tipos de asignaciones entre la cuenta de Windows y la cuenta del sistema distinto de Windows.  
  
 Los tipos de aplicación son:  
  
 **Individuales** aplicaciones individuales admiten asignaciones uno a uno entre la cuenta de Windows y la cuenta distinta de Windows. En una aplicación de tipo individual, una cuenta de Windows se asigna a una cuenta que no es de Windows, y sólo a una. La asignación se puede utilizar en cualquier sentido: desde Windows al sistema distinto de Windows, desde éste a Windows, o en ambos sentidos, en función de los indicadores que se han definido para la aplicación. De este modo, las aplicaciones individuales se pueden utilizar para SSO iniciado por Windows, SSO iniciado por host o para ambos.  
  
 **Grupo** aplicaciones de grupo admiten asignaciones entre un grupo de Windows y una cuenta distinta de Windows. La cuenta de usuarios de aplicación se utiliza para definir el grupo de Windows que se usará para la aplicación de grupo. Tan sólo se puede definir una asignación para una aplicación de grupo, y esa asignación debe establecerse entre el grupo de Windows y la cuenta que no es de Windows y que utilizarán todos los miembros del grupo de Windows para obtener acceso al sistema distinto de Windows. Las aplicaciones de grupo sólo pueden utilizarse para SSO iniciado por Windows.  
  
 **Grupo host** aplicaciones de grupo Host constituyen, conceptualmente, la inversa de las aplicaciones de grupo. Admiten asignaciones entre un grupo definido de cuentas que no son de Windows y una cuenta de Windows. La cuenta de usuarios de aplicación de la aplicación define la cuenta de Windows única que utilizarán las cuentas que no son de Windows. El grupo de las cuentas que no son de Windows al que se permite el acceso a esta aplicación se define mediante la creación de una asignación para cada cuenta que no es de Windows. Las aplicaciones de grupo de host sólo pueden utilizarse para SSO iniciado por host.  
  
## <a name="designing-an-affiliate-application"></a>Diseñar una aplicación afiliada  
 Antes de crear una aplicación afiliada, el administrador afiliado de SSO o el administrador de SSO tiene que tomar las siguientes decisiones:  
  
1.  **¿Qué representará la aplicación afiliada?** Es necesario saber a qué aplicación que no es de Windows representará la aplicación afiliada en el sistema de SSO. Por ejemplo,  
  
     Nombre de la aplicación: APP1  
  
     Descripción: Aplicación de departamento de recibos de pago  
  
     Póngase en contacto con:administrator@companyname.com  
  
2.  **¿Quién administrará la aplicación afiliada?** Es necesario determinar los administradores de la aplicación afiliada. Ellos forman el grupo de administradores de Windows para la aplicación afiliada. Por ejemplo, Dominio\GrupoAdminAPP1  
  
3.  **¿Quién va a usar la aplicación afiliada?** Es necesario determinar quiénes serán los usuarios finales de la aplicación afiliada. Estos usuarios representan el grupo de usuarios de Windows de la aplicación afiliada; por ejemplo, Dominio\UsuariosDominio. En el caso de la aplicación para los recibos de pago, si se desea que todos los usuarios obtengan acceso a la información de los recibos de pago correspondientes, se puede especificar el grupo de usuarios de dominio como el grupo de usuarios de la aplicación.  
  
4.  **¿Qué credenciales utiliza de la aplicación afiliada para autenticar sus usuarios?** Las distintas aplicaciones utilizan credenciales diferentes para autenticar usuarios. Por ejemplo, algunas aplicaciones pueden utilizar Id. de usuario, contraseñas, números PIN o una combinación de estos elementos. Asimismo, es preciso determinar si el sistema tiene que enmascarar las credenciales a medida que el usuario las proporciona.  
  
5.  **¿Usará asignaciones individuales o una asignación de grupo para la aplicación afiliada?** ¿Cada usuario de Windows tiene una cuenta en el sistema de servidor o dispone éste de una cuenta para todos los usuarios de Windows? En el caso del sistema de recibos de pago, cada usuario tiene su propia cuenta para obtener acceso a la información de recibos de pago correspondiente, por lo que será preciso utilizar asignaciones individuales.  
  
 Tras crear una aplicación afiliada, no podrá modificar las siguientes propiedades:  
  
-   Nombre de la aplicación afiliada  
  
-   Campos asociados con la aplicación afiliada  
  
-   Tipo de aplicación afiliada (grupo de host, individual o almacén de configuración)  
  
-   Cuenta de administración igual al grupo de administradores afiliados. (Si se selecciona esta propiedad, el grupo de administradores afiliados se utiliza como la cuenta de administradores de aplicación para la aplicación afiliada.)  
  
## <a name="affiliate-application-properties"></a>Propiedades de aplicaciones afiliadas  
 En la siguiente tabla se enumeran las propiedades que es preciso definir para cada aplicación afiliada que se cree.  
  
|Propiedad|Description|  
|--------------|-----------------|  
|Nombre de la aplicación|Nombre de la aplicación afiliada. No es posible cambiar esta propiedad tras crear la aplicación afiliada.|  
|Description|Breve descripción de la aplicación afiliada|  
|Contacto|Contacto principal de la aplicación afiliada que pueden utilizar los usuarios. (Puede ser una dirección de correo electrónico.)|  
|appUserAccount|El grupo de Windows que contiene las cuentas de usuario de los usuarios finales que utilizará la aplicación afiliada.|  
|appAdminAccount|El grupo de Windows que contiene las cuentas de administradores que administrará la aplicación afiliada. **Nota:** no es necesario definir esta propiedad si se establece adminaccountsame como Sí.|  
  
|Indicador de aplicaciones|Description|  
|----------------------|-----------------|  
|enableApp|Estado de la aplicación afiliada.|  
|groupApp|Determina si la aplicación utiliza una asignación de grupo (Sí) o asignaciones individuales (No).<br /><br /> No es posible cambiar esta propiedad tras crear la aplicación.|  
|configStoreApp|Determina si la aplicación afiliada es una aplicación de tipo de almacén de configuración (Sí).<br /><br /> No es posible cambiar esta propiedad tras crear la aplicación.|  
|hostInitiatedSSO|Habilite esta opción si la aplicación es del tipo SSO iniciado por host. El valor predeterminado es No.|  
|windowsInitiatedSSO|Habilite esta opción si la aplicación es del tipo SSO iniciado por Windows. El valor predeterminado es Sí.|  
|validatePassword|Esto es aplicable únicamente a aplicaciones de SSO iniciadas por host. Cuando la aplicación intente recuperar credenciales, debe proporcionar la contraseña de la base de datos de SSO que se utiliza para que los servicios SSO efectúen la validación. El valor predeterminado es Sí.|  
|disableCredCache|El servidor de SSO almacena las credenciales en una caché para acelerar el acceso. El valor predeterminado es No.|  
|allowTickets|Determina si el sistema de SSO utiliza vales para la aplicación afiliada.<br /><br /> **Seguridad** debe ser un administrador de SSO para establecer este indicador.|  
|validateTickets|Determina si el sistema de SSO valida vales cuando el usuario los canjea.<br /><br /> **Seguridad** debe ser un administrador de SSO para establecer este indicador.|  
|appTicketTimeOut|Especifica un tiempo de espera de vales específico para la aplicación afiliada. Se puede establecer únicamente al actualizar una aplicación afiliada, no al crearla.<br /><br /> Si vales está habilitada para esta aplicación y esta propiedad no es así, es el tiempo de espera especificado en el sistema de SSO (Global) se utiliza el nivel.<br /><br /> **Seguridad** debe ser un administrador de SSO para establecer este indicador.|  
|timeoutTickets|Determina si los vales tienen un periodo de vencimiento. El valor predeterminado es Sí.<br /><br /> **Seguridad** a menos que sea necesario, deshabilite los tiempos de espera de vale (no).<br /><br /> **Seguridad** debe ser un administrador de SSO para establecer este indicador.|  
|allowLocalAccounts|Determina si se permite el uso de las cuentas y los grupos locales en el sistema de SSO. Este indicador puede configurarse únicamente como Sí en escenarios de un solo equipo.|  
|adminAccountSame|Determina si se utiliza el grupo de administradores afiliados de SSO como el grupo de administradores de aplicación.<br /><br /> No es posible cambiar esta propiedad tras crear la aplicación.<br /><br /> **Seguridad** debe ser un administrador de SSO o administrador afiliado de SSO para establecer este indicador.|  
  
|Campos de aplicación|Description|Description|  
|------------------------|-----------------|-----------------|  
|Campo [0]|\<*credencial*\>: enmascara/Unmasked|Determina el tipo de credencial (Id. de usuario, contraseña o tarjeta inteligente) que deben proporcionar los usuarios finales para efectuar la conexión con la aplicación afiliada, así como si la credencial se enmascara (es decir, si los caracteres que el usuario escribe se muestran en pantalla) o no.<br /><br /> Puede especificar tantos campos como credenciales haya para la aplicación afiliada, aunque el primer campo debe ser el Id. de usuario.<br /><br /> No es posible cambiar esta propiedad tras crear la aplicación.|  
  
## <a name="see-also"></a>Vea también  
 [Administrar aplicaciones afiliadas](../core/managing-affiliate-applications.md)   
 [Asignaciones de SSO](../core/sso-mappings.md)   
 [Administración de asignaciones de usuarios](../core/managing-user-mappings.md)