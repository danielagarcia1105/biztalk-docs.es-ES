---
title: Directrices para implementar permisos de Active Directory en las instalaciones de BizTalk multiservidor | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 315e25c4-b21d-4b5f-a1d2-1e2777b57f9e
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ff7b45e560278053cec99208fd06917d079d6b8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="guidelines-for-implementing-active-directory-permissions-on-multi-server-biztalk-installations"></a>Directrices para implementar permisos de Active Directory en instalaciones de BizTalk multiservidor
En este tema se describen las directrices para crear unidades de organización de Active Directory que consisten en las cuentas de usuario y los grupos que se usan en una instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 Las cuentas que se crean aquí no necesitan otros permisos en el dominio diferentes a los de los usuarios normales. Es posible que las cuentas de dominio necesiten privilegios elevados dentro del límite de confianza que incluye:  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
-   Microsoft [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] (en el servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)])  
  
-   Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]  
  
-   Base de datos externa Una  
  
-   Base de datos externa Dos  
  
-   Base de datos externa *N*  
  
 Por ejemplo, es posible que una cuenta de dominio necesite derechos concedidos para realizar determinadas acciones en los sistemas que alojan bases de datos externas. En otro caso, es posible que una cuenta necesite escribir un archivo en la carpeta de destino de los archivos y que esto exija acceso de escritura a la carpeta.  
  
 Use la **equipos y usuarios de Active Directory** consola para crear y administrar cuentas de usuario y grupo de dominio. Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **equipos y usuarios de Active Directory** a iniciar el **equipos y usuarios de Active Directory** consola.  
  
## <a name="biztalk-server-installation-and-configuration-account"></a>Cuenta de configuración e instalación de BizTalk Server  
 En el entorno de desarrollo, el programa de instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y el Asistente para configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] necesitan el uso de una cuenta con derechos administrativos en los sistemas [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Los derechos se pueden revocar o la cuenta se puede deshabilitar cuando la instalación y configuración hayan finalizado. La cuenta también debe pertenecer a varios grupos de BizTalk, lo que se describe en las secciones siguientes.  
  
> [!NOTE]
>  No podrá configurar los componentes de SSO si la cuenta usada para la instalación pertenece a un bosque de Active Directory diferente del servidor. Si no dispone de cuenta de instalador de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], use una cuenta de administrador local para la configuración de SSO. Esta metodología puede crear otros problemas durante la instalación, tal como la necesidad de iniciar sesión en recursos con credenciales diferentes.  
  
## <a name="biztalk-server-development-accounts"></a>Cuentas de desarrollo de BizTalk Server  
 Las personas que realizan el desarrollo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] necesitan tener acceso a los adaptadores, los controladores de envío y recepción, y las ubicaciones de recepción. Este acceso requiere que el grupo de desarrolladores de dominio debe ser miembro de la **administradores de BizTalk Server** y **administradores afiliados de SSO** grupos.  
  
> [!NOTE]
>  Active Directory tiene restricciones en relación a los tipos de grupos que pueden contener usuarios de dominio externos y los tipos de grupos que otros grupos pueden contener. Los grupos y las cuentas que se crean a continuación se han comprobado en un entorno multiservidor en un dominio único.  
  
## <a name="biztalk-server-deployment-accounts"></a>Cuentas de implementación de BizTalk Server  
 Las personas que implementan aplicaciones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deberán ser administradores en los sistemas locales y es posible que necesiten otros permisos en el entorno. En este tema se hace referencia a una cuenta de implementación de BizTalk Server para este fin.  
  
 Este acceso requiere que el grupo de implementación de dominio debe ser miembro de la **administradores de BizTalk Server** y **administradores afiliados de SSO** grupos.  
  
> [!NOTE]
>  No podrá configurar los componentes de SSO si la cuenta usada para la instalación pertenece a un bosque de Active Directory diferente del servidor. Si no dispone de cuenta de implementación de BizTalk Server, use una cuenta de administrador local para la configuración de SSO. Esta metodología puede crear otros problemas durante la instalación, tal como la necesidad de iniciar sesión en recursos con credenciales diferentes.  
  
## <a name="biztalk-server-support-accounts"></a>Cuentas de soporte técnico de BizTalk Server  
 Las personas que ofrecen soporte técnico para las aplicaciones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deberán ser administradores en los sistemas locales. En este tema se hace referencia a una cuenta de soporte técnico de BizTalk para este fin.  
  
 Este acceso requiere que el grupo de soporte técnico de dominio debe ser miembro de la **administradores de BizTalk Server** grupo.  
  
## <a name="sql-server-service-accounts"></a>Cuentas de servicio de SQL Server  
 El servicio que ejecuta la instancia de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] debe pertenecer al mismo dominio de Active Directory que las cuentas que instalan, desarrollan e implementan componentes de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
-   Use **SQLAdmin** para las funciones administrativas (inicio de sesión interactivo).  
  
-   Use **SQLService** para administrar el servicio (sin inicio de sesión interactivo).  
  
-   Use **SQLAccess** para tener acceso a bases de datos externas.  
  
-   SQLAdmin debe ser miembro del grupo de administradores locales en el sistema [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  
  
-   SQLService debe ser miembro del grupo Administradores local en el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sistema y debe concedérsele el **iniciar sesión como un servicio** derecho de usuario.  
  
-   SQLAccess necesita los derechos adecuados en los servidores de base de datos remotos.  
  
 **Cuentas SQL:**  
  
|**Nombre de usuario.**|**First Name**|**Last Name**|**Nombre completo**|  
|-------------------|--------------------|-------------------|-------------------|  
|SQLService|SQL|SQLService|Cuenta de servicio SQL|  
|SQLAdmin|Administración|SQLService|Cuenta de administrador de SQL|  
|SQLAccess|Acceso|SQLService|Cuenta de acceso de SQL|  
  
 Defina las contraseñas de cuenta según los estándares de la compañía.  
  
> [!IMPORTANT]
>  En el equipo donde se ejecuta [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], modifique los parámetros de inicio para SQL Server y los servicios SQLServerAgent para usar la cuenta y las credenciales de SQLService.  
  
> [!NOTE]
>  Los campos de nombre de usuario son ejemplos, es posible que deba cambiar los nombres para evitar conflictos con otras cuentas de Active Directory.  
  
## <a name="windows-sharepoint-services-account"></a>Cuenta de Windows SharePoint Services  
 Es necesario crear las cuentas de Windows SharePoint Services antes de instalar [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].  
  
 Recomendaciones y notas acerca de la cuenta de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]:  
  
-   Use la cuenta de administración de SharePoint (SPAdmin) para los roles administrativos, el servicio de temporizador de SharePoint y todo el acceso a [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].  
  
-   SPAdmin es el propietario del sitio y necesitará un alias de correo electrónico.  
  
-   SPAdmin debe ser miembro del grupo de administradores locales en el equipo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] local (la configuración de Windows SharePoint Services lo hace).  
  
-   SPAdmin debe tener los roles de administrador de seguridad y creador de base de datos en el equipo [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] (la configuración de Windows SharePoint Services lo hace).  
  
 **Cuentas de SharePoint:**  
  
|**Nombre de usuario.**|**First Name**|**Last Name**|**Nombre completo**|  
|-------------------|--------------------|-------------------|-------------------|  
|SPAdmin|Administración|SPService|Cuenta de administración de SharePoint|  
  
 Defina las contraseñas de cuenta según los estándares de la compañía para que pueda recuperarlas durante los pasos de configuración. Hacer referencia a la **contraseñas** sección de este tema para problemas relacionados con las contraseñas generadas.  
  
> [!NOTE]
>  Este campo de nombre de usuario es un ejemplo; es posible que necesite cambiar el nombre para proteger otras cuentas de Active Directory.  
  
> [!IMPORTANT]
>  Después de instalar Windows SharePoint Services en el equipo donde se ejecuta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], confirme que los parámetros de inicio del Servicio de temporizador de SharePoint usan la cuenta y las credenciales de SPAdmin.  
  
## <a name="biztalk-groups-and-users"></a>Grupos y usuarios de BizTalk  
 Los grupos y usuarios de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deben crearse antes de ejecutar el Asistente para configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En una instalación de un único sistema, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa grupos y cuentas locales creados durante la configuración. Sin embargo, si se implementan diferentes hosts de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] se instalan en dos equipos diferentes, debe usar las cuentas de grupo y usuario de dominio.  
  
> [!NOTE]
>  El Asistente para configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no puede crear cuentas de dominio.  
  
 Recomendaciones y notas acerca de las cuentas de usuario y servicio de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   Cree una unidad de organización (OU) para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Todas las cuentas y grupos pertenecerán a esta OU.  
  
-   Sea descriptivo con los nombres completos; los nombres de las listas siguientes deben permitir al instalador seleccionar los grupos/cuentas/usuarios adecuados durante la configuración.  
  
-   El primer nombre y los apellidos son opcionales; se incluyen sólo por coherencia.  
  
-   El diferenciador **BTService** y **BTUser** hace referencia a las cuentas de servicio (autómatas) y usuarios humanos genéricos/compartidos.  
  
-   Cree las cuentas de dominio y rellénelas mediante una secuencia de comandos de ADSI para la creación de cuentas de usuario y de grupo para entornos principales.  
  
 **Cuentas de servicio de BizTalk**  
  
|**Nombre de usuario.**|**First Name**|**Last Name**|**Nombre completo**|  
|-------------------|--------------------|-------------------|-------------------|  
|BTService|BTS|BTService|Cuenta de servicio de BizTalk|  
|BTServiceHost|Host|BTService|Cuenta de instancias de host de BizTalk|  
|BTServiceHostIso|HostIso|BTService|Cuenta de instancia de host aislada de BizTalk|  
|SSOService|SSO|BTService|Servicio de inicio de sesión único (SSO) empresarial|  
|BTServiceREU|REU|BTService|Servicio de actualización de motor de reglas|  
  
 Defina los nombres de usuario según los estándares de la compañía y del entorno (por ejemplo, devBTService, alphaBTService). Establecer las contraseñas de cuenta según los estándares de la empresa y que pueda recuperarlos para conocer los pasos de configuración. Hacer referencia a la **consideraciones de contraseña para el desarrollo** sección de este tema para problemas relacionados con las contraseñas generadas.  
  
 El instalador observará que las cuentas de servicio son bastante individualizadas, con una asignación de uno a uno con los servicios que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ha creado. La individualización permite a la seguridad de la TI corporativa realizar el seguimiento del acceso o restringirlo según sea necesario. Se recomienda seguir esta individualización, aunque siempre el diseñador del sistema y el personal de seguridad de la empresa son los que deben determinar si esto es necesario en el entorno de la empresa.  
  
 Las cuentas de servicio del grupo anterior están previstas sólo para un acceso automatizado, no para el inicio de sesión interactivo de los usuarios.  
  
#### <a name="to-set-the-appropriate-account-options"></a>Para definir las opciones de cuenta adecuadas  
  
1.  En el **equipos y usuarios de Active Directory** de la consola, haga clic para expandir el dominio y, a continuación, haga clic para expandir el **usuarios** contenedor.  
  
2.  Haga clic en la cuenta y, a continuación, seleccione **propiedades** para mostrar la **propiedades** cuadro de diálogo para la cuenta.  
  
3.  Haga clic en el **cuenta** pestaña de la **propiedades** cuadro de diálogo.  
  
4.  Haga clic para activar las opciones siguientes:  
  
    -   **Usuario no puede cambiar la contraseña** (seguridad de la empresa procesará por lotes cambiar las contraseñas).  
  
    -   **La contraseña nunca caduca**  
  
5.  Haga clic en el **iniciar sesión en** botón para mostrar el **estaciones de trabajo de inicio de sesión** cuadro de diálogo.  
  
6.  Haga clic en la opción de **los siguientes equipos**, agregar los equipos que ejecuten [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]y, a continuación, haga clic en **Aceptar**.  
  
7.  Haga clic en el **Control remoto** pestaña de la **propiedades** cuadro de diálogo y, a continuación, haga clic para desactivar la opción de **habilitar el control remoto**.  
  
8.  Haga clic en el **perfil de Terminal Services** pestaña de la **propiedades** cuadro de diálogo.  
  
9. Haga clic para activar la opción de **denegar los permisos de este usuario para iniciar sesión en cualquier Terminal Server**.  
  
10. Haga clic en **Aceptar** para cerrar el **propiedades** cuadro de diálogo para la cuenta.  
  
11. Repita los pasos del 3 al 10 para cada cuenta de servicio.  
  
 **Cuentas de usuario de BizTalk**  
  
|**Nombre de usuario.**|**First Name**|**Last Name**|**Nombre completo**|  
|-------------------|--------------------|-------------------|-------------------|  
|BTUserAdmin|Administración|BTUser|Cuenta de usuario administrativa de BizTalk|  
|BTUserDeploy|Implementar|BTUser|Cuenta de usuario de implementación de BizTalk|  
|BTUserHostInstance|HostInstance|BTUser|Cuenta de instancias de host de BizTalk|  
|BTUserHostIsolated|IsolatedlHost|BTUser|Cuenta de instancia de host aislada de BizTalk|  
|BTUserInstall|Install|BTUser|Cuenta de usuario de instalación de BizTalk|  
|BTUserSupport|Soporte técnico|BTUser|Cuenta de acceso de soporte técnico de BizTalk|  
  
#### <a name="to-set-the-appropriate-account-options-follow-these-steps"></a>Para definir las opciones de cuenta apropiadas, realice los pasos siguientes  
  
1.  En el **equipos y usuarios de Active Directory** consola haga clic para expandir el dominio y, a continuación, haga clic para expandir el **usuarios** contenedor.  
  
2.  Haga clic en la cuenta y, a continuación, seleccione **propiedades** para mostrar la **propiedades** cuadro de diálogo para la cuenta.  
  
3.  Haga clic en el **cuenta** pestaña de la **propiedades** cuadro de diálogo.  
  
4.  Haga clic para activar las opciones siguientes:  
  
    -   **Usuario no puede cambiar la contraseña** (seguridad de la empresa procesará por lotes cambiar las contraseñas).  
  
    -   **La contraseña nunca caduca**  
  
5.  Haga clic en el **iniciar sesión en** botón para mostrar el **estaciones de trabajo de inicio de sesión** cuadro de diálogo.  
  
6.  Haga clic en la opción de **los siguientes equipos**, agregar los equipos que ejecuten [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]y, a continuación, haga clic en **Aceptar**.  
  
7.  Haga clic en el **Control remoto** pestaña de la **propiedades** cuadro de diálogo y, a continuación, haga clic para activar la opción de **habilitar el control remoto**.  
  
8.  Haga clic en el **perfil de Terminal Services** pestaña de la **propiedades** cuadro de diálogo.  
  
9. Haga clic para desactivar la opción de **denegar los permisos de este usuario para iniciar sesión en cualquier Terminal Server**.  
  
10. Haga clic en **Aceptar** para cerrar el **propiedades** cuadro de diálogo para la cuenta.  
  
11. Repita los pasos del 3 al 10 para cada cuenta de usuario.  
  
    > [!NOTE]
    >  Cualquiera de estas cuentas se puede deshabilitar si los roles que se van a proporcionar están asignados a usuarios reales. En las primeras etapas de la versión uno y de la versión dos, se supone que estas cuentas se usan en los entornos de desarrollo, prueba alfa y prueba beta.  
  
 **Cuentas de grupo de BizTalk**  
  
|**Nombre de grupo**|**Tipo de grupo**|**Miembros**|  
|--------------------|--------------------|-----------------|  
|Usuarios de aplicación de BizTalk|Global o universal|-BTServiceHost<br />-BTUserHostInstance|  
|Usuarios de desarrollo de BizTalk|Global o universal|(cuentas de dominio local de usuarios de desarrollo) **Nota:** como práctica recomendada, no habilite el grupo de usuarios de desarrollo de BizTalk en entornos principales.|  
|Usuarios de implementación de BizTalk|Global o universal|(cuentas de dominio local de usuarios de implementación)|  
|Usuarios de host de BizTalk|Global o universal|BTUserHostInstance|  
|Usuarios de hosts aislados de BizTalk|Global o universal|-BTServiceHostIso<br />-BTUserHostInstance|  
|Administradores de servidor BizTalk Server|Global o universal|-BTUserAdmin<br />-BTUserInstall<br />: Los usuarios de desarrollo de BizTalk<br />: Los usuarios de la implementación de BizTalk|  
|Usuarios de soporte técnico de BizTalk|Global o universal|BTUserSupport (cuentas de dominio local de usuarios de soporte técnico)|  
|Administradores de SSO|Global o universal|-SSOService<br />-BTUserInstall<br />: Administrador local|  
|Administradores afiliados de SSO|Global o universal|: Los usuarios de desarrollo de BizTalk<br />: Los usuarios de la implementación de BizTalk<br />-BTServiceHostIso<br />-   \<usuario de la consola\>|  
|Administradores de Windows SharePoint Services|Global o universal|-SPAdmin<br />-BTUserInstall<br />-BTUserDeploy<br />: Los usuarios de desarrollo de BizTalk<br />: Los usuarios de la implementación de BizTalk|  
  
 Recomendaciones y notas acerca de los grupos de dominios:  
  
-   Cree los grupos y agregue miembros antes de instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
-   Los grupos de dominios pueden ser grupos globales o universales.  
  
-   Use  *\<DomainName\>\\< nombre de usuario\>*  cuando se especifica la información de la cuenta de dominio en el Asistente para configuración.  
  
-   Los grupos y las cuentas de usuario o servicio deben pertenecer al dominio al que pertenece el equipo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] (el Asistente para configuración lo comprueba y no muestra cuentas ni grupos que contengan cuentas de otros dominios).  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] necesita cuentas de dominio en todos los escenarios de clúster.  
  
-   Al instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], el usuario de consola debe ser un miembro de los grupos siguientes:  
  
    -   Administradores de servidor BizTalk Server  
  
    -   Administradores de SSO (sólo al configurar el servidor secreto principal).  
  
    -   Administrador de Windows  
  
    -   Administrador de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]  
  
    -   Administrador de OLAP  
  
     La cuenta BTUserInstall debería usarse para la instalación y configuración y, una vez que estos procesos han finalizado, debería deshabilitarse.  
  
-   Para permitir que los eventos de mensaje y seguimiento de instancias de servicio para adjuntar orquestaciones al depurador, el programador debe pertenecer al grupo de administradores de BizTalk Server, tal como se describe anteriormente en la sección **cuentas de desarrollo de BizTalk** .  
  
## <a name="local-administrator-accounts"></a>Cuentas de administrador local  
 Confirme o agregue los grupos y cuentas siguientes al grupo de administradores locales en el equipo de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]:  
  
-   Dominio\BTUserInstall (deshabilitar cuando la configuración ha finalizado)  
  
-   Dominio\BTUserDeploy (deshabilitar en la producción cuando la implementación ha finalizado)  
  
-   Dominio\SPAdmin  
  
-   Dominio\SQLAdmin  
  
-   Dominio\SQLService  
  
-   Dominio\usuarios de desarrollo (omitir en entornos principales)  
  
-   Dominio\Usuarios de implementación de BizTalk (omitir en entornos de desarrollo)  
  
 Confirme o agregue los grupos y cuentas siguientes al grupo de administradores locales en el equipo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   Dominio\BTUserInstall (deshabilitar cuando la configuración ha finalizado)  
  
-   Dominio\BTUserDeploy (deshabilitar en la producción cuando la implementación ha finalizado)  
  
-   Dominio\BTUserSupport  
  
-   Dominio\SPAdmin  
  
-   Dominio\Usuarios de desarrollo de BizTalk (omitir en entornos principales)  
  
-   Dominio\Usuarios de implementación de BizTalk (omitir en entornos de desarrollo)  
  
## <a name="sql-server-administrator-accounts"></a>Cuentas de administrador de servidor SQL Server  
 Los programas de configuración aceptan entradas del instalador y asignan roles de SQL a usuarios y grupos:  
  
-   Durante la configuración de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)], a la cuenta SPAdmin se le conceden derechos de administrador de seguridad y creador de base de datos en el equipo de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Estos derechos se pueden quitar si la cuenta SPAdmin es miembro del grupo de administradores locales.  
  
## <a name="e-mail-account"></a>Cuenta de correo electrónico  
 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] enviará correo según determinados eventos del sistema. Durante el proceso de configuración, se solicita una dirección de correo electrónico. Cree alias de correo electrónico para este fin y supervíselos durante la configuración y las pruebas que realice en la unidad. En el entorno de producción, el administrador de sistema que supervise el sistema debería tener acceso a esta cuenta.  
  
 La cuenta de correo electrónico utilizada por [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] es el **correo electrónico del Administrador de WSS** cuenta.  
  
## <a name="password-considerations-for-development"></a>Consideraciones de contraseña para el desarrollo  
 En los entornos de desarrollo y prueba, las contraseñas de cuenta pueden definirse por un estándar y ser distribuibles. Los estándares del instalador varían; en este tema se usa la plantilla que consiste en letras mayúsculas iniciales que abrevian el componente de servicio seguido de una abreviación en minúsculas para el resto de la cuenta (servicio o usuario). Para las cuentas de servicio, en este tema se usa “Serv” mientras que para las cuentas de usuario se usa “User”.  
  
 Por ejemplo:  
  
-   Contraseñas de cuenta (SPAdmin) de servicio y administración de Windows SharePoint Services (SharePoint): 'SPServ'.  
  
-   Las contraseñas de cuentas de BizTalk Service: 'BTServ'.  
  
-   Las contraseñas de cuentas de usuario de BizTalk: 'BTUser'.  
  
 Algunos entornos de TI exigen que las contraseñas contengan caracteres no alfabéticos o numéricos. En este escenario, puede usar un signo del dólar ($) para sustituir la "s" y un signo “arroba” (@) para la "a". Los símbolos son ejemplos; desarrolle un patrón que se adecue a sus necesidades para las cuentas compartidas con contraseñas semipúblicas.  
  
 Algunas contraseñas de ejemplo que se pueden volver a distribuir en uso en el entorno de desarrollo son las siguientes:  
  
-   BT$erv99           Cuentas de servicio de BizTalk  
  
-   BTU$er99          Cuentas de usuarios de BizTalk  
  
-   SP$erv99           Cuenta de servicio de WSS (SPAdmin)  
  
-   SQL$erv99         Servicio SQL/Acceso/Cuenta de administración  
  
> [!NOTE]
>  Estas recomendaciones están dirigidas únicamente a entornos de desarrollo y compartidos, y no se recomienda o se desaconseja el uso de directivas de contraseñas corporativas. Consulte al administrador de la red para conocer los requisitos de contraseña.  
  
> [!NOTE]
>  Si la directiva de contraseñas corporativas incluye contraseñas generadas, tenga en cuenta que algunos símbolos y combinaciones de símbolos son caracteres de uso especial en XML. El uso inadecuado de estos caracteres impedirá que los archivos XML de configuración se puedan abrir durante el proceso de configuración. Estos símbolos incluyen "&", "\<","\>", comillas simples y dobles y pueden incluir otros usuarios. Pruebe el archivo XML de configuración antes de ejecutar la configuración basada en archivos. Puede probar de forma confiable el formato XML adecuado mediante la apertura del documento en Internet Explorer (o en un editor de XML) con las contraseñas generadas integradas en él.  
  
 Para obtener más información acerca de la implementación de contraseñas seguras en entornos principales (incluido el método para probar un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] archivo de configuración), consulte [Introducción a la configuración de BizTalk Server 2013 y 2013 R2](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72).  
  
## <a name="see-also"></a>Vea también  
 [Solucionar problemas de permisos de servidor BizTalk Server](../core/troubleshooting-biztalk-server-permissions.md)