---
title: Directrices para solucionar problemas de permisos de IIS | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: troubleshooting
ms.assetid: d9793a90-3aa3-46ab-a317-6d1e0fbfc1ef
caps.latest.revision: "30"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb91509ec3ad1c329190c848c25a60434f93499e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="guidelines-for-resolving-iis-permissions-problems"></a>Directrices para solucionar problemas de permisos de IIS
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] hace abundante uso de Microsoft Internet Information Services (IIS) para la compatibilidad con servicios Web y para su utilización con los adaptadores de HTTP, SOAP y Windows SharePoint Services.  
  
 Antes de solucionar los problemas de permisos de IIS, le resultará útil entender cómo implementa IIS el aislamiento de aplicaciones.  
  
 IIS proporciona funciones para crear aplicaciones de IIS como procesos de host diferenciados que se ejecutan en su propio espacio de memoria. Una vez que cree un host de aplicación de IIS, debe definir dos conjuntos de permisos, el host de aplicación de IIS **identidad del proceso** y el host de aplicación de IIS **derechos de acceso de usuario**. Deberá examinar cada uno de estos conjuntos de permisos cuando solucione problemas con los permisos de IIS.  
  
> [!NOTE]
>  El **identidad del proceso** y **derechos de acceso de usuario** también se conocen como el **contexto de seguridad** del proceso de host de aplicación de IIS.  
  
 Este tema describe cómo establecer **identidad del proceso** y **derechos de acceso de usuario** para un proceso de host de aplicación de IIS y ofrece algunas directrices generales para solucionar problemas de permisos de IIS.  
  
## <a name="setting-iis-application-host-process-identity"></a>Establecer la identidad de proceso del host de la aplicación de IIS  
 La configuración del proceso de host de una aplicación de IIS puede variar dependiendo del nivel de funcionalidad que proporcione dicho proceso de host. Por ejemplo, el proceso de host de una aplicación de IIS que solo proporciona páginas HTML estáticas normalmente se configura de forma distinta al proceso de host de una aplicación de IIS que proporciona páginas ASP o aplicaciones ASP.NET.  
  
 La configuración del proceso de host de una aplicación de IIS también varía dependiendo de la versión de IIS que hospede la aplicación. La identidad del proceso de host de aplicaciones que se ejecutan en Windows Server 2008 (IIS 7.0) la determina la identidad del grupo de aplicaciones asociado con la aplicación.  
  
### <a name="setting-iis-process-identity-for-iis-70-on-windows-server-2008-or-windows-vista"></a>Establecer la identidad de proceso de IIS para IIS 7.0 en Windows Server 2008 o Windows Vista  
  
1.  Haga clic en **iniciar**, a continuación, **todos los programas**y haga clic en **el Administrador de Internet Information Services (IIS) 7**.  
  
2.  En el Administrador de Internet Information Services (IIS), expanda  *\<nombre_equipo\>***(cuenta de usuario)** y haga clic en **grupos de aplicaciones**.  
  
3.  Haga clic en un grupo de aplicaciones y haga clic en **ver aplicaciones** para ver las aplicaciones asociadas con el grupo de aplicaciones.  
  
4.  Haga clic en un grupo de aplicaciones y haga clic en **configuración avanzada** para mostrar el cuadro de diálogo Configuración avanzada para el grupo de aplicaciones.  
  
5.  Modifique la identidad del grupo de aplicaciones, haga clic en el botón de puntos suspensivos (...) junto a **identidad** en el **modelo de proceso** sección de la **configuración avanzada** cuadro de diálogo cuadro.  
  
## <a name="setting-user-access-rights-for-the-iis-server"></a>Establecer los derechos de acceso de usuario para el servidor IIS  
 Si bien la identidad de proceso controla el contexto de seguridad disponible para el proceso de host de la aplicación de IIS en ejecución, los permisos de acceso de usuario controlan el contexto de seguridad de la cuenta que realmente obtiene acceso a las páginas web que se proporcionan. Con el fin de evitar errores de permisos, es preciso establecer los permisos de la forma adecuada para ambos contextos de seguridad.  
  
 IIS 7.0 admite los siguientes métodos de autenticación de usuario:  
  
-   **El acceso anónimo:** permite a los usuarios establecer una conexión anónima. El servidor IIS inicia la sesión del usuario con la cuenta de invitado especificada.  
  
-   **Suplantación de ASP.NET** permite que una aplicación para que se ejecute en uno de dos contextos diferentes: como usuario autenticado por IIS o como una cuenta arbitraria que configuró.  
  
-   **La autenticación básica:** transmite las contraseñas a través de la red en texto sin formato, sin cifrar.  
  
-   **La autenticación implícita:** funciona sólo con cuentas de Active Directory, enviar un valor hash a través de la red, en lugar de una contraseña de texto simple. La autenticación implícita funciona en servidores proxy y firewalls, y está disponible en directorios del Sistema distribuido de creación y control de versiones web (WebDAV). El uso de la autenticación implícita requiere que la autenticación anónima se deshabilite primero.  
  
-   **Autenticación mediante formularios** incorpora la autenticación para sitios de tráfico elevado o aplicaciones en servidores públicos. La autenticación de formularios permite administrar el registro de clientes y su autenticación en el nivel de aplicación, en lugar de depender de mecanismos de autenticación proporcionados por el sistema operativo.  
  
-   **Autenticación de Windows:** usa la autenticación en el dominio de Windows para autenticar las conexiones de cliente.  
  
#### <a name="to-set-user-access-rights-for-a-virtual-directory-in-iis-70"></a>Para establecer los derechos de acceso de usuario para un directorio virtual en IIS 7.0  
  
1.  En el Administrador de Internet Information Services (IIS), expanda  *\<nombre_equipo\>*, **sitios**, y **sitio Web predeterminado** en el **Conexiones** panel.  
  
2.  Haga clic para seleccionar el directorio virtual y haga clic en el **vista características** en la parte inferior del panel de área de trabajo para enumerar la características configurables para el directorio virtual.  
  
3.  Haga doble clic en el **autenticación** característica en el panel de área de trabajo para que se enumeran los métodos de autenticación que están habilitados para el directorio virtual.  
  
4.  Haga clic para seleccionar el método de autenticación que desea habilitar o deshabilitar y haga clic en **deshabilitar** o **habilitar** en el **acciones** panel del Administrador de IIS.  
  
    > [!NOTE]
    >  Si **habilitar el acceso anónimo** está habilitado, IIS establecerá derechos de acceso de usuario como la identidad de usuario anónimo configurada antes de establecer derechos de acceso de usuario con los demás métodos de autenticación habilitados.  
    >   
    >  Para configurar la identidad de usuario anónimo, haga clic en el **autenticación anónima** método y haga clic en **editar** para mostrar la **editar credenciales de autenticación anónima**cuadro de diálogo.  
  
## <a name="general-guidelines-for-resolving-iis-permissions-problems"></a>Directrices generales para solucionar problemas de permisos de IIS  
 Siga estos pasos para solucionar problemas con los permisos de IIS:  
  
1.  Compruebe si existen errores detallados en el registro de la aplicación del equipo del servidor IIS.  
  
2.  Siga los pasos de [IIS 7.0: configurar el seguimiento de solicitudes con error en IIS 7.0](http://go.microsoft.com/fwlink/?LinkId=130600) para solucionar problemas de permisos en equipos IIS 7.0.  
  
3.  Compruebe la existencia de errores HTTP 401 en los archivos de registro de IIS del servidor IIS.  
  
     De forma predeterminada, en un equipo con Windows Server 2008 o Windows Vista, los archivos de registro de IIS se encuentran en el siguiente directorio:  
  
     C:\inetpub\logs\LogFiles\W3SVC1\  
  
    -   Si el archivo de registro IIS de un equipo IIS 7.0 contiene errores HTTP 401, siga los pasos descritos en el artículo 943891 de Microsoft Knowledge Base, "lo códigos de estado HTTP en IIS 7.0" disponible en [http://support.microsoft.com/kb/943891](http://support.microsoft.com/kb/943891) para determinar el código de subestado y para solucionar el problema de permisos basado en el código de estado.  
  
    -   Compruebe el valor de la **cs-username** campo asociado con el error HTTP 401. Este campo contiene el nombre del usuario autenticado que obtiene acceso al servidor IIS. En este campo, la cuenta de usuario anónimo se representa mediante un guión (-). Asegúrese de que esta cuenta tiene permisos para los recursos apropiados.  
  
4.  Compruebe que las credenciales de identidad de proceso empleadas por el proceso de host de la aplicación de IIS están establecidas correctamente y que la cuenta tiene los permisos apropiados. Si la cuenta usada para la identidad de proceso no tiene permisos suficientes, cambie la cuenta o bien conceda los permisos apropiados a la misma.  
  
5.  Use las utilidades RegMon y FileMon se describe en [herramientas y utilidades que se usan para la solución de problemas](../core/tools-and-utilities-to-use-for-troubleshooting.md) para diagnosticar problemas de permisos de acceso de archivo o del registro.  
  
## <a name="see-also"></a>Vea también  
 [Solucionar problemas de permisos de servidor BizTalk Server](../core/troubleshooting-biztalk-server-permissions.md)   
 [IIS 7.0: Configurar la autenticación en IIS 7.0](http://go.microsoft.com/fwlink/?LinkId=129909)