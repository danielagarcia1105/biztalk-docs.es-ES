---
title: "Solución de problemas de Enterprise Single Sign-On | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cb54af9f-a6ef-46c1-b987-2019cff3f837
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 450b2df7ec043dfd4bc775cfec7acdec0fb3ca1f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="troubleshooting-enterprise-single-sign-on"></a>Solución de problemas de Enterprise Single Sign-On
En esta tema se proporciona información sobre los problemas comunes que se pueden producir al usar el inicio de sesión único (SSO) empresarial.  
  
 Cuando empiece a solucionar problemas con el entorno de SSO, puede resultar útil seguir los elementos de la tabla siguiente para asegurarse de que todos los componentes funcionan del modo esperado:  
  
|Pregunta|Comentarios|  
|--------------|--------------|  
|¿Hay algo relacionado con el sistema SSO en el registro de eventos de la aplicación?|Los mensajes de SSO del registro de eventos permiten acotar el problema existente en el sistema SSO. El origen de los mensajes provenientes del sistema SSO es ENTSSO. **Importante:** muchos de los eventos y errores de SSO aparecen como advertencias en el registro de eventos no como errores. El sistema SSO genera una advertencia cuando el problema afecta a un solo cliente del servicio SSO, y genera errores cuando el problema afecta a todo el sistema SSO (a todos los clientes).|  
|¿El servicio SSO está instalado correctamente?<br /><br /> ¿Se inicia del modo previsto?<br /><br /> ¿En qué cuenta de servicio se está ejecutando el servicio SSO?|Asegúrese de que el servicio SSO está correctamente instalado y que la cuenta de servicio pertenece al grupo de administradores de SSO.|  
|¿Dónde está la base de datos de SSO?|Use la línea de comandos **ssoconfig -showdb**. Para obtener más información sobre este comando, consulte [cómo mostrar la información de la base de datos de SSO](../core/how-to-display-the-sso-database-information.md).|  
|¿Qué servidor de SSO se está usando?|Use la línea de comandos **ssomanage -showserver**. Para obtener más información sobre este comando, consulte [cómo establecer el servidor de SSO](../core/how-to-set-the-sso-server.md).|  
|¿Qué es la cuenta de administrador de SSO?|Use la línea de comandos **ssomanage –displaydb**. Para obtener más información sobre este comando, consulte [cómo mostrar la información de la base de datos de SSO](../core/how-to-display-the-sso-database-information.md).|  
|¿Está todo habilitado correctamente?|Use la línea de comandos **ssomanage –displaydb**. Para obtener más información sobre este comando, consulte [cómo mostrar la información de la base de datos de SSO](../core/how-to-display-the-sso-database-information.md).|  
|¿Existen las aplicaciones afiliadas?|Use la línea de comandos **ssomanage –listapps all**. Para obtener más información sobre este comando, consulte [cómo enumerar las aplicaciones afiliadas](../core/how-to-list-affiliate-applications.md).|  
|¿La aplicación afiliada específica parece correcta?<br /><br /> ¿Qué cuentas utiliza esta aplicación afiliada?|Usar la línea de comandos **ssomanage-displayapp***\<nombre de la aplicación\>*. Para obtener más información sobre este comando, consulte [cómo mostrar las propiedades de una aplicación afiliada](../core/how-to-list-the-properties-of-an-affiliate-application.md).|  
|¿Existe alguna asignación para esta aplicación afiliada?|Usar la línea de comandos **ssomanage – listmappings***\<nombre de la aplicación\>*. Para obtener más información sobre este comando, consulte [cómo Listar asignaciones de usuarios](../core/how-to-list-user-mappings.md).|  
|¿Qué cuentas pertenecen a los grupos de SSO?|Compruebe la pertenencia al grupo de todos los grupos y cuentas de SSO.|  
|¿La aplicación COM+ del servidor de SSO se está ejecutando del modo previsto?|Compruebe la aplicación COM+ del servidor de SSO. **Nota:** también puede comprobar el registro de eventos para obtener información detallada, como eventos y mensajes de advertencia.|  
  
## <a name="known-issues"></a>Problemas conocidos  
  
#### <a name="entsso-service-fails-to-start"></a>El servicio ENTSSO no consigue iniciarse  
  
##### <a name="problem"></a>Problema  
 El Servicio ENTSSO no consigue iniciarse.  
  
##### <a name="cause"></a>Causa  
 El Servicio ENTSSO no se podrá iniciar si no se ejecuta con una cuenta de administrador de SSO válida.  
  
##### <a name="resolution"></a>Solución:  
 Especifique una cuenta de administrador de SSO válida para el Servicio ENTSSO y reinicie éste desde el complemento Administrador de control de servicios.  
  
#### <a name="biztalk-services-dependent-on-the-enterprise-single-sign-on-service-entsso-fail-to-start-after-a-reboot"></a>Los servicios de BizTalk que dependen del inicio de sesión único empresarial (ENTSSO) no se inician después de reiniciar el equipo  
  
##### <a name="problem"></a>Problema  
 BTSSvc$BizTalkServerApplication depende del Servicio de inicio de sesión único empresarial (ENTSSO) y después de reiniciar el equipo puede causar un tiempo de espera durante el inicio.  
  
##### <a name="cause"></a>Causa  
 El Servicio de inicio de sesión único empresarial puede tardar unos 3 minutos en iniciarse.  
  
##### <a name="resolution"></a>Solución:  
 Configure el servicio “Grupo de BizTalk del servicio de BizTalk: BizTalkServerApplication" con la opción de tipo de inicio automático (inicio retrasado). De este modo, el servicio se iniciará después de que todos los servicios automáticos finalicen sus rutinas de inicio.  
  
#### <a name="cannot-access-an-affiliate-application"></a>No puede obtener acceso a una aplicación afiliada  
  
##### <a name="problem"></a>Problema  
 El Servicio de inicio de sesión único empresarial deshabilita una aplicación afiliada si la cuenta de administrador de aplicación asociada con él no es válida.  
  
##### <a name="cause"></a>Causa  
 La cuenta de administrador de aplicación de SSO no es válida.  
  
##### <a name="resolution"></a>Solución:  
 Antes de crear una aplicación afiliada, asegúrese de que la cuenta de administrador de aplicación de SSO es válida. Después deberá habilitar la aplicación afiliada para poder usarla.  
  
#### <a name="rpc-error-occurs-when-connecting-to-a-client-computer"></a>Se produce un error RPC al conectarse a un equipo cliente  
  
##### <a name="problem"></a>Problema  
 Cuando un usuario ejecuta un comando como **ssomanage - displayapp***\<applicationname\>*, donde el equipo intenta conectarse a un servidor de SSO remoto para recuperar la información recibe el siguiente error: ERROR: 0x800706BA: el servidor RPC no está disponible.  
  
##### <a name="cause"></a>Causa  
 Este error se produce cuando el usuario especifica la información de servidor incorrecta o cuando el servicio SSO no está disponible en el servidor remoto.  
  
##### <a name="resolution"></a>Solución  
  
-   Siga los pasos de [cómo establecer el servidor de SSO](../core/how-to-set-the-sso-server.md) para asegurarse de que está conectado al servidor de SSO correcto.  
  
-   Asegúrese de que el Servicio SSO está habilitado y en ejecución en el servidor de SSO al que se conecta.  
  
#### <a name="master-secret-is-missing-or-corrupt"></a>El secreto principal falta o está dañado  
  
##### <a name="problem"></a>Problema  
 El secreto principal falta o está dañado. Normalmente, se genera durante la configuración. Si falta el secreto, en el registro de eventos aparecerá uno de los mensajes siguientes cuando se inicie el Servicio de inicio de sesión único (SSO) empresarial.  
  
 Id. del mensaje=10520  
  
 Gravedad=Advertencia  
  
 SSO_WARN_NO_SECRETS  
  
 Id. del mensaje=10565  
  
 Gravedad=Error  
  
 SSO_ERROR_SECRET_VALIDATE_FAILED  
  
 Id. del mensaje=10521  
  
 Gravedad=Error  
  
 SSO_ERROR_SECRETS_NOT_LOADED  
  
##### <a name="cause"></a>Causa  
 Es posible que este problema se produzca si se genera un secreto mientras se estaba ejecutando el Servicio de inicio de sesión único (SSO) empresarial en una cuenta de servicio y, posteriormente, se cambia la cuenta de servicio. El secreto se almacena en el Registro en formato cifrado mediante una clave basada en la identidad de la cuenta de servicio (en la cual se ejecuta ENTSSO).  
  
##### <a name="resolution"></a>Solución:  
 Cambie la cuenta de servicio con la que se ejecuta ENTSSO a la cuenta de servicio original cuando se creó el secreto principal.  
  
 Para cambiar la cuenta de servicio ENTSSO:  
  
1.  Haga una copia de seguridad del secreto principal. Para obtener más información, consulte [cómo volver la seguridad del secreto principal](../core/how-to-back-up-the-master-secret.md).  
  
2.  Detenga los Servicios de inicio de sesión único (SSO) empresarial.  
  
3.  Cambie la cuenta de servicio.  
  
4.  Reinicie el SSO y haga caso omiso de los errores del registro de eventos de un secreto dañado, si éstos se produjeran.  
  
5.  Restaure el secreto principal. Para obtener más información, consulte [cómo restaurar el secreto principal](../core/how-to-restore-the-master-secret.md).  
  
## <a name="see-also"></a>Vea también  
 [Implementación de Enterprise Single Sign-On](../core/implementing-enterprise-single-sign-on.md)