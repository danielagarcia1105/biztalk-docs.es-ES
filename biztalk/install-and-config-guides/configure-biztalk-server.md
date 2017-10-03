---
title: "Configurar usando la configuración básica o personalizada | Documentos de Microsoft"
description: "Pasos para realizar una configuración básica o personalizada de BizTalk Server y obtenga información acerca de lo que ocurre con cada configuración"
ms.custom: 
ms.date: 08/14/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 861a1237-d77a-42db-b563-d83f7930add6
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8989fd322fd9fc34e947a80b510619446a65f71
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-biztalk-server"></a>Configuración de BizTalk Server
Configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mediante una configuración básica o una configuración personalizada.

## <a name="basic-configuration-vs-custom-configuration"></a>Configuración básica frente a configuración personalizada

* Si su configuración usa grupos de dominio, use una configuración personalizada.
* Si su configuración usa nombres de grupo personalizados en lugar de los nombres de grupo predeterminados, use una configuración personalizada.
* Si su configuración usa nombres de base de datos personalizados en lugar de los nombres de base de datos predeterminados, use una configuración personalizada.
* Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y SQL Server están en equipos diferentes, se requieren grupos de dominio. Por tanto, use una configuración personalizada.
* No puede configurar el análisis de BAM en una instancia de SQL Server con nombre mediante una configuración básica. Si usa instancias con nombre y quiere configurar el análisis de BAM, use una configuración personalizada.
* La configuración básica es recomendable para usuarios que llevan a cabo una instalación completa de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y SQL Server en ejecución en un único servidor.
* La configuración básica es más rápida porque crea automáticamente los grupos y las bases de datos locales con los nombres predeterminados.


## <a name="before-you-begin"></a>Antes de comenzar
* [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se puede configurar mediante instancias predeterminadas de SQL Server e instancias con nombre. 
* La cuenta con la que ha iniciado sesión debe ser miembro del grupo local de administradores y contar con derechos de administrador del sistema en SQL Server.
* Si usa grupos de dominio, los grupos de dominio deben existir *antes* de configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].
* Las cuentas predeterminadas que genera [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y que se enumeran en la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] son grupos locales. En un entorno de varios servidores, reemplace los grupos locales con grupos de dominio.
* Si configura los servicios de análisis de BAM, la cuenta con la que ha iniciado sesión debe ser miembro del grupo Administradores de OLAP en el equipo de OLAP.


## <a name="basic-configuration"></a>Configuración básica

1. En el menú Inicio, haga clic con el botón derecho en **Configuración de BizTalk Server** y, después, seleccione **Ejecutar como administrador**. De este modo, se abre el Asistente para configuración. 
2. Seleccione las opciones siguientes: 
    1. Seleccione **Configuración básica**.
    2. El **Nombre del servidor de bases de datos** usa automáticamente como valor predeterminado el nombre del equipo local.   
    3. Escriba el **Nombre de usuario** y la **Contraseña** para la cuenta en la que se ejecutarán los servicios de BizTalk. Se recomienda que cree una cuenta única. No use su nombre de usuario personal.  
        ![bts2016BasicConfig](../install-and-config-guides/media/bts2016basicconfig.gif)  
    Si especifica un nombre de usuario con credenciales administrativas en el equipo, recibirá una advertencia. Es algo normal. Seleccione **Aceptar** para continuar.
    
3. Seleccione **Configurar**.
4. Revise los detalles de configuración y seleccione **Siguiente**.
5. Una vez completado el Asistente para la configuración, seleccione **Finalizar**.

Se genera un archivo de registro de configuración en una carpeta temporal, similar al siguiente: `
C:\Users\username\AppData\Local\Temp\ConfigLog(01-12-2017 0h37m59s).log`.

Al usar una configuración básica, ocurre lo siguiente:

- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] genera automáticamente todos los nombres de las bases de datos.
- Toda la información aplicable de inicio de sesión de base de datos se ejecuta en la cuenta que especifique. 
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] genera automáticamente todos los servicios de BizTalk.
- Todos los servicios de BizTalk se ejecutan en la cuenta que especifique. El proceso de configuración concede a esta cuenta los permisos de seguridad necesarios con respecto al servidor y a los objetos de SQL Server.
- Todas las características se configuran en función del software necesario que haya instalado en el equipo.
- Los grupos se crean automáticamente en el equipo local con los nombres de grupo predeterminados.
- El sitio Web predeterminado de los Servicios de Internet Information Server (IIS) se utiliza para todas las características que requieran IIS.

## <a name="custom-configuration"></a>Configuración personalizada
  
1. En el menú Inicio, haga clic con el botón derecho en **Configuración de BizTalk Server** y, después, seleccione **Ejecutar como administrador**. De este modo, se abre el Asistente para configuración.
2. Seleccione **Configuración personalizada** y, después, **Configurar**.

### <a name="configure-enterprise-single-sign-on-sso"></a>Configurar Enterprise Single Sign-On (SSO)

* Una vez que SSO se ha configurado, no se puede volver a configurar mediante la configuración de BizTalk Server. Para volver a configurar SSO, use la Administración de BizTalk Server.
* Al configurar las cuentas de Windows de SSO mediante cuentas locales, especifique únicamente el nombre de la cuenta. No escriba el nombre del equipo.
* Cuando se usa una instancia con nombre local de SQL Server como almacén de datos, use `LocalMachineName\InstanceName`. No use `LocalMachineName\InstanceName, PortNumber`. 

1. Seleccione **SSO empresarial**.
2. Configure lo siguiente:

    | Use | Para |
    | --- | --- |
    |Habilitar Inicio de sesión único empresarial en este equipo | Configurar este servidor con la configuración de SSO. |
    |Crear un nuevo sistema SSO | Si es el primer servidor de SSO que va a configurar, seleccione esta opción. De este modo, se crea y se configura la base de datos de SSO, se crea el secreto maestro (una clave de seguridad cifrada) y se instalan los servicios que usa SSO. También debe hacer una copia de seguridad del secreto de este servidor secreto.<br/><br/>Detalles de clave: <br/><ul><li>Se recomienda que configure el servidor de secreto maestro como servidor independiente.</li><li>Para llevar a cabo esta tarea de configuración, debe ser un administrador de SSO.</li><li>Tan sólo un servidor secreto principal puede asociarse a un grupo de BizTalk. No se admite la asociación de dos servidores secretos principales con el mismo grupo de BizTalk.</li></ul>|
    |Unir un sistema SSO existente | Si va a agregar un servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] a un grupo existente, seleccione esta opción. El servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] comparte la misma configuración de SSO y las bases de datos con los demás servidores [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] del grupo. |
    |Almacenes de datos | Escriba el nombre de su servidor de SSO. Si se encuentra en el servidor de SSO, seleccione el nombre del servidor local. Puede conservar **SSODB** como nombre predeterminado de la base de datos o especificar un nombre personalizado.|
    |Servicio de Windows| Especifique la cuenta que se usa para ejecutar el servicio Enterprise Single Sign-On. Si SQL Server está en otro equipo, especifique la cuenta de dominio. |
    |cuentas de Windows|Puede conservar los nombres de grupo predeterminados o especificar un nombre personalizado. Si SQL Server está en otro equipo, especifique las cuentas de dominio. |

3. Seleccione **Copia de seguridad de secreto de SSO empresarial**. Esta opción guarda el secreto maestro en un archivo de copia de seguridad cifrado. 
4. Configure lo siguiente:  

    |Use|Para|
    | --- | --- |
    |Contraseña de la copia de seguridad del secreto | Escribir la contraseña secreta maestra.|
    |Confirmar contraseña|Volver a escribir la contraseña secreta maestra.|
    |Recordatorio de contraseña|Escribir un recordatorio para la contraseña especificada. Es muy importante que no omita este paso. |
    |Ubicación del archivo de copia de seguridad|Mostrar el nombre y la ubicación del archivo de copia de seguridad. De forma predeterminada, se almacena en \Archivos de programa\Common Files\Enterprise Single Sign-On\ *nombreDeArchivo*.bak.|

**SIEMPRE** realice una copia de seguridad del secreto maestro y comparta la contraseña con otro administrador de BizTalk.
    
### <a name="configure-groups"></a>Configurar grupos

* Cuando se usa una instancia con nombre local de SQL Server como almacén de datos, use `LocalMachineName\InstanceName`. No use `LocalMachineName\InstanceName, PortNumber`.

1. Seleccione **Grupo**.
2. Configure lo siguiente:

    |Use|Para|
    | --- | --- |
    |Habilitar el grupo de BizTalk Server en este equipo|Seleccione esta opción para crear un grupo de BizTalk en este servidor o para unirse a un grupo existente. |
    |Crear un nuevo grupo de BizTalk| Si es el primer servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] del grupo, seleccione esta opción. Use esta opción para crear las bases de datos y agregar los grupos.|
    |Unir un grupo de BizTalk existente| Si va a agregar este servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] a un grupo existente, seleccione esta opción.|
    |Crear una base de datos de análisis para realizar un seguimiento de las agregaciones|Seleccione esta opción para instalar SQL Server Analysis Services y si quiere proceder al seguimiento y el almacenamiento de los cubos OLAP de seguimiento de estado.|
    |Almacenes de datos| Especifique el nombre del servidor que hospeda las bases de datos de BizTalk. Si este servidor tiene instalados un servidor BizTalk y SQL, escriba el nombre del servidor local. Si SQL Server está en otro equipo, especifique el nombre de SQL Server.<br/><br/>Puede conservar los nombres de base de datos predeterminados o especificar un nombre personalizado.|
    |Funciones administrativas de BizTalk|Puede conservar los nombres de grupo predeterminados o especificar un nombre personalizado. Si SQL Server está en otro equipo, especifique las cuentas de dominio.|

### <a name="configure-the-biztalk-runtime"></a>Configurar el tiempo de ejecución de BizTalk

* Una vez que se ha configurado el tiempo de ejecución, no se puede volver a configurar mediante la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para volver a configurar el tiempo de ejecución, use la Administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].
* El primer host que cree en el grupo debe ser una instancia de host y un host In-Process.
* Cuando se configura el tiempo de ejecución en varios servidores [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] del mismo grupo, no se puede usar la misma cuenta de servicio para las aplicaciones host de confianza y que no son de confianza. Debe usar una cuenta única para la aplicación de confianza y para la aplicación que no es de confianza. 

1. Seleccione **Tiempo de ejecución de BizTalk**.
2. Configure lo siguiente:

    |Use|Para|
    | --- | --- |
    | Registrar los componentes de tiempo de ejecución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] | Seleccione esta opción para crear los hosts y las instancias de host en este servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. |
    | Crear un host de BizTalk de tipo En curso y una instancia | Crea la instancia y el host BizTalkServerApplication en este equipo.<br/><br/>Opciones adicionales: <ul><li>**De confianza**: pasa las credenciales (SSID o identificador de entidad) del remitente al enviar mensajes a la base de datos de cuadro de mensaje. Esto equivale a crear una relación de confianza entre los servidores. La mayoría de los hosts e instancias no es de confianza.</li><li>**Solo de 32 bits**: algunos adaptadores solo se ejecutan en un proceso de 32 bits, pero la mayoría es compatible con 64 bits. Esta opción puede habilitarse o deshabilitarse en la Administración de BizTalk después de que se haya configurado BizTalk. Por lo tanto, no debe preocuparse por este asunto.</li><li>**Nombre de host**: el valor predeterminado es BizTalkServerApplication. Cuando cree hosts e instancias en la Administración de BizTalk puede usar nombres más específicos, como TrackingHost o ReceivingHost. Por lo tanto, déjelo tal cual.</li></ul>|
    | Crear un host aislado y una instancia| El host aislado se ejecuta en IIS. En muchos entornos, es mejor mantener los valores predeterminados.<br/><br/>Opciones adicionales: <ul><li>**De confianza**: pasa las credenciales (SSID o identificador de entidad) del remitente al enviar mensajes a la base de datos de cuadro de mensaje. Esto equivale a crear una relación de confianza entre los servidores. La mayoría de los hosts e instancias no es de confianza.</li><li>**Solo de 32 bits**: algunos adaptadores solo se ejecutan en un proceso de 32 bits, pero la mayoría es compatible con 64 bits. Esta opción puede habilitarse o deshabilitarse en la Administración de BizTalk después de que se haya configurado BizTalk.</li><li>**Nombre de host aislado**: el valor predeterminado es BizTalkServerIsolatedHost. Déjelo tal cual. </li></ul>|
    |Servicio de Windows| Especifique las cuentas que se usan para ejecutar las instancias de host. Si SQL Server está en otro equipo, especifique las cuentas de dominio. |
    |Grupos de Windows|Puede conservar los nombres de grupo predeterminados o especificar un nombre personalizado. Si SQL Server está en otro equipo, especifique las cuentas de dominio. |


### <a name="configure-business-rules-engine-bre"></a>Configurar el motor de reglas de negocios (BRE)

Si no usa BRE, omita esta sección.

- Se recomienda que configure un grupo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] antes de configurar el motor de reglas de negocios. Si configura BRE antes que un grupo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no agregará roles administrativos relacionados con grupos a la base de datos del motor de reglas.

1. Seleccione **Motor de reglas de negocios**.
2. Configure lo siguiente:

    |Use|Para|
    | --- | --- |
    |Habilitar el motor de reglas de negocios en este equipo | Si usa BRE en este servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], seleccione esta opción. |
    |Almacenes de datos| Especifique el nombre del servidor que hospeda la base de datos de reglas. Si este servidor tiene instalados un servidor BizTalk y SQL, escriba el nombre del servidor local. Si SQL Server está en otro equipo, especifique el nombre de SQL Server.<br/><br/>Puede conservar el nombre de base de datos predeterminado o especificar un nombre personalizado.|
    |Servicio de Windows| Especifique las cuentas que se usan para ejecutar el servicio de actualización de reglas. Si SQL Server está en otro equipo, especifique la cuenta de dominio. |


### <a name="configure-bam-tools"></a>Configurar herramientas de BAM

Si no usa herramientas de BAM, omita esta sección.

Entre las herramientas de Supervisión de la actividad económica se incluyen las siguientes:

- Complemento de SAE para Excel
- administrador de BAM
- Portal de BAM


- La configuración de las herramientas de BAM requiere ciertas funcionalidades administrativas de SQL Server y debe realizarse en una máquina que tenga instalado Integration Services.
- Las herramientas de SAE pueden ser utilizadas por varios grupos de BizTalk. Al quitar la configuración de las herramientas de BAM, se quita la conexión con el grupo de BizTalk, pero la infraestructura de SQL Server de BAM sigue funcionando para otros grupos de BizTalk que apuntan a las tablas de importación principal de BAM.
- Use la página Herramientas de Supervisión de la actividad económica para volver a configurar la base de datos de BAM sobre la marcha. Por ejemplo, vuelva a configurar la base de datos de BAM sin quitar la configuración existente. Al volver a configurar estas bases de datos de BAM, se interrumpen todas las vistas OLAP ya implementadas y todas las alertas. Si quiere que alguna de las alertas y vistas existentes forme parte de las bases de datos recién configuradas, lleve a cabo uno de los procedimientos siguientes:  
    - Anule la implementación de las alertas y las vistas antes de efectuar una nueva configuración, y vuelva a efectuar la implementación después de volver a llevar a cabo la configuración. Ningún dato que se haya archivado formará parte de las vistas.
    - Si no está utilizando alertas de SAE, haga copias de seguridad de las bases de datos antes de volver a configurar. Tras llevar a cabo la reconfiguración, restaure las bases de datos en la ubicación recién configurada.
- Si está consolidando bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], debe excluir el archivo de BAM y bases de datos de análisis de BAM.


1. Seleccione **Herramientas de BAM**.
2. Configure lo siguiente:

    |Use|Para|
    | --- | --- |
    |Habilitar las herramientas de Supervisión de la actividad económica | Habilite e instale herramientas de BAM en este equipo. |
    | Habilitar servicios de análisis para las agregaciones de BAM | Proporciona información de seguimiento de las alertas de BAM.|
    |Almacenes de datos| Especifique el nombre del servidor que hospeda las bases de datos de BAM. Si este servidor tiene instalados un servidor BizTalk y SQL, escriba el nombre del servidor local. Si SQL Server está en otro equipo, especifique el nombre de SQL Server.<br/><br/>Puede conservar el nombre de base de datos predeterminado o especificar un nombre personalizado.|
    |Quitar las herramientas de Supervisión de la actividad económica para este grupo de BizTalk | Desinstala y quita las herramientas de BAM del grupo de BizTalk. |
    
 ### <a name="configure-bam-alerts"></a>Configurar alertas de BAM 

Las alertas BAM requieren que las herramientas de BAM estén habilitadas.

1. Seleccione **Alertas de BAM**.
2. Configure lo siguiente:

    |Use|Para|
    | --- | --- |
    | Habilitar alertas de BAM | Si usa alertas de BAM, active esta opción. <br/><br/>Recuerde que debe haber configurado Correo electrónico de base de datos SQL para poder usar las alertas de BAM. |
    | Servicio de Windows | Especifique las cuentas que se usan para ejecutar el servicio de alertas de BAM. Si SQL Server está en otro equipo, especifique la cuenta de dominio. |
    | Servidor SMTP de alertas de BAM| Especifique el nombre de servidor SMTP que ha configurado con Correo electrónico de base de datos SQL. |
    | Ubicación de archivo de alertas de BAM| Especifique un recurso compartido de red para almacenar las alertas de BAM. <br/><br/>**Nota** <br/>Debe crear manualmente este recurso compartido antes de que las alertas SAE puedan almacenar los archivos.|
    | Servidor SQL Server para bases de datos de alertas | Especifique el nombre de servidor SQL Server que hospeda la base de datos de alertas.<br/><br/>**Nota** <br/>El uso de las direcciones IPv6 para especificar el servidor SQL Server de servicios de notificación para las bases de datos de alertas no es compatible. Sin embargo, puede usar un nombre de equipo y la traducción de DNS controlará la búsqueda.|
    |Prefijo de nombres de bases de datos de alertas| Especifique el prefijo usado para las bases de datos de alertas.|  

### <a name="configure-the-bam-portal"></a>Configurar el portal de BAM

1. Seleccione **Portal de BAM**.
2. Configure lo siguiente:

    |Use|Para|
    | --- | --- |
    |Habilitar el portal de BAM | Si usa el portal de BAM, active esta opción. | 
    |Cuentas de servicio Web | Especifique las cuentas que se usan para ejecutar los servicios IIS. Si SQL Server está en otro equipo, especifique las cuentas de dominio.|
    |grupos de Windows | Puede conservar el nombre de grupo predeterminado o especificar un nombre personalizado. Si SQL Server está en otro equipo, especifique la cuenta de dominio.|
    |Sitio Web del portal de SAE|Seleccione el sitio web que hospedará el portal de BAM. En algunos entornos, el sitio web predeterminado es el único sitio web configurado. |

### <a name="configure-biztalk-edias2-runtime"></a>Configurar el tiempo de ejecución de EDI y AS2 de BizTalk 

* Debe configurar Enterprise SSO, el grupo y el tiempo de ejecución de BizTalk antes de configurar el tiempo de ejecución de EDI y AS2 de BizTalk. 
* Es necesario habilitar las herramientas de BAM antes de configurar las características de creación de informes de estado en tiempo de ejecución de EDI y AS2.
* Si solo va a configurar EDI, BAM no es necesario.

1. Seleccione **Tiempo de ejecución de EDI y AS2 de BizTalk**.
2. Configure lo siguiente:

    |Use|Para|
    | --- | --- |
    |Habilitar el tiempo de ejecución de EDI y AS2 de BizTalk en este equipo| Si va a usar los protocolos X12, EDIFACT o AS2 para la mensajería de negocio a negocio, seleccione esta opción. |
    |Habilitar EDI de BizTalk para este grupo de BizTalk | Seleccione esta opción si se usa X12 o EDIFACT. |
    | Habilitar AS2 de BizTalk para este grupo de BizTalk | Seleccione esta opción si se usa AS2. |
    | Habilitar los informes de estado de tiempo de ejecución de EDI y AS2 de BizTalk para este grupo de BizTalk | Habilite la experiencia de usuario de informes para proporcionar el estado de intercambios y confirmaciones de EDI. |
    |Quitar las funcionalidades de informes de estado, AS2 y EDI de BizTalk de este grupo de BizTalk | Desinstala y quita del grupo la característica de informes. |

### <a name="configure-windows-sharepoint-services-web-service---biztalk-server-2013-and-r2-only"></a>Configurar el servicio web de Windows SharePoint Services (solo BizTalk Server 2013 y R2) 

> [!IMPORTANT] 
> Esta sección SOLO se aplica a BizTalk Server 2013 R2 y BizTalk Server 2013. Si no usa BizTalk Server 2013 R2 o BizTalk Server 2013, omita esta sección.

* Este servicio web de SharePoint Services (SSOM) se ha eliminado a partir de BizTalk Server 2016 y está en desuso en BizTalk Server 2013 R2. Se ha reemplazado por el adaptador de SharePoint Services (CSOM). La opción CSOM no se muestra en la configuración de BizTalk. La opción CSOM se instala automáticamente con BizTalk, igual que el adaptador de archivo, o se instala automáticamente el adaptador de HTTP.

1. Seleccione **Adaptador de Windows SharePoint Services**.
2. Configure lo siguiente:

    |Use|Para|
    | --- | --- |
    | Habilitar Adaptador de Windows SharePoint Services en este equipo | Seleccione esta opción para instalar el servicio web de SharePoint Services. En el equipo de SharePoint Services también se instala un servicio web IIS que puede estar en el mismo equipo de BizTalk Server o en otro distinto. En la mayoría de los entornos, BizTalk Server y SharePoint Services están en equipos independientes.|
    |Grupo de Windows|Puede conservar el nombre de grupo predeterminado o especificar un nombre personalizado. |
    |Sitio web del adaptador de Windows SharePoint Services|Seleccione el sitio web que hospeda el servicio web del adaptador de Windows SharePoint Services.|
    
    
### <a name="apply-your-configuration"></a>Aplicar la configuración

Seleccione **Aplicar configuración** y continúe con la configuración. 

1. En **Resumen**, revise los componentes que ha seleccionado y seleccione **Siguiente**.
2. Cuando haya finalizado, seleccione **Finalizar**.

Al acabar, se genera un archivo de registro de configuración en una carpeta temporal, similar al siguiente: `
C:\Users\username\AppData\Local\Temp\ConfigLog(1-12-2017 2h39m30s).log`.

## <a name="iis-application-pools-and-web-sites"></a>Grupos de aplicaciones de IIS y sitios web
Después de configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], pueden crearse los siguientes grupos de aplicaciones de Internet Information Services (IIS) y las aplicaciones virtuales: 
  
### <a name="application-pools"></a>Grupos de aplicaciones  
  
|Grupo de aplicaciones|Identidad del grupo de aplicaciones predeterminado|Description|  
|----------------------|---------------------------------------|-----------------|  
|BAMAppPool|*Definido por el usuario*|Grupo de aplicaciones para el portal de BAM.|  
|BTSSharePointAdapterWSAppPool|*Definido por el usuario*|Grupo de aplicaciones para el servicio Web del adaptador de Windows SharePoint Services.|  
|STSWebServiceAppPool|*Definido por el usuario*|Grupo de aplicaciones para las Herramientas de Administración de socios comerciales.|  
|TpmWSAppPool|*Definido por el usuario*|Grupo de aplicaciones para el servicio Web de administración de TPM.|  
  
### <a name="virtual-applications"></a>Aplicaciones virtuales  
  
|Aplicación virtual|Grupo de aplicaciones predeterminado|Description|  
|-------------------------|------------------------------|-----------------|  
|BAM|BAMAppPool|Aplicación virtual que aloja los componentes del portal de BAM (páginas, imágenes, código precompilado y otros recursos). Esta aplicación virtual llama a la aplicación BAMManagementService para comunicarse con las bases de datos de BAM. **Nota:** su marca en el Portal de BAM, puede modificar el contenido de esta aplicación.|  
|BAMManagementService|BAMAppPool|La aplicación virtual que aloja el servicio Web BAMManagementService. La aplicación del portal de BAM utiliza este servicio Web para comunicarse con las tablas de importación principal (PIT) de BAM. La comunicación con la base de datos se realiza a través de credenciales suplantadas almacenadas en el Registro que se crean durante la configuración. Los clientes personalizados pueden usar los métodos expuestos por este servicio Web para obtener vistas y los detalles correspondientes, además de actividades relacionadas y diseños de tabla dinámica para cualquier usuario. Los métodos también se pueden usar para administrar alertas en la base de datos.|  
|BTSharePointAdapterWS|BTSSharePointAdapterWSAppPool|Aplicación virtual que aloja el servicio Web del adaptador de Windows SharePoint Services. Se aplica a BizTalk Server 2013 R2 y solo de 2013.|  

 
## <a name="more-configuration-topics"></a>Más temas de configuración  
  
 [Configurar BizTalk Server en una máquina virtual de Azure](http://msdn.microsoft.com/library/azure/jj248689.aspx)  
  
[Configuración de BizTalk Server en un clúster](../install-and-config-guides/configure-biztalk-server-in-a-cluster.md)

[Pasos posteriores a la configuración para optimizar el entorno](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)

 [Proteger la implementación de BizTalk Server](../install-and-config-guides/securing-your-biztalk-server-deployment.md)  
  
 