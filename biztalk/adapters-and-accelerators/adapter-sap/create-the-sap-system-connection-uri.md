---
title: "Crear la conexión del sistema SAP URI | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- connection URI
- how to, connect using connection URI
- connecting using connection URI
- connecting to SAP, using the connection URI
ms.assetid: e41ed488-07a7-4fb7-97c0-6d626e041e95
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f9c224eb7a219cf3e5bb81f31ef8382c555295b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="create-the-sap-system-connection-uri"></a>Crear el URI de conexión de sistema SAP
El [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] URI de conexión contiene propiedades que el adaptador utiliza para establecer una conexión con el sistema SAP.  
  
> [!IMPORTANT]
>  De forma predeterminada, la biblioteca de cliente SAP (librfc32u.dll) admite un máximo de 100 conexiones al sistema SAP. Si se supera este número de conexiones, se producirá una excepción. Por este motivo, debe establecer el **MaxConnectionsPerSystem** enlace de propiedad para limitar el número de conexiones que el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] intentará abrir en el sistema SAP; o establezca la variable de entorno CPIC_MAX_CONV en aumentar el número de conexiones admitidas por la biblioteca de cliente SAP. Si cambia CPIC_MAX_CONV, debe reiniciar el equipo para que el cambio surta efecto. Para obtener más información sobre la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] propiedades de enlace, consulte [obtener información sobre el adaptador de BizTalk para propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
 Este tema proporciona información sobre el URI de conexión de SAP y también proporciona vínculos a otros temas que explican cómo especificar un URI de conexión en distintos escenarios de programación.  
  
## <a name="connection-uri-for-the-sap-adapter"></a>URI de conexión para el adaptador SAP  
 Una típica [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] dirección de punto de conexión URI se representa como sigue:  
  
```  
scheme://userinfoparams@hostinfoparams?query_string  
```  
  
 La dirección del extremo URI contiene los siguientes componentes:  
  
-   esquema es el nombre de esquema.  
  
-   userinfoparams es una colección de nombre y valor de los parámetros necesarios para la autenticación de usuario por el punto de conexión.  
  
-   hostinfoparams es la información necesaria para establecer la conexión con el host; Por ejemplo, una ruta de acceso.  
  
-   QUERY_STRING es una colección de nombre y valor opcional de parámetros delimitados por un signo de interrogación (?).  
  
 La dirección URI del extremo que la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] usos de un sistema SAP se especifica mediante un URI de conexión de SAP. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] implementa este URI de conexión como se indica a continuación:  
  
```  
sap://user=[USER_NAME];passwd=[PASSWORD];Client=[CLIENT];lang=[LANGUAGE];[UseSnc]=[True|False]@connectiontype/conndetail1/conndetail2?GwHost=[GWHOST]?GwServ=[GWSERV]?MsServ=[MSSERV]?Group=[GROUP]?ListenerDest=[LISTENERDEST]?ListenerGwHost=[LISTENERGWHOST]?ListenerGwServ=[LISTENERGWSERV]?ListenerProgramId=[LISTENERPROGRAMID]?RfcSdkTrace=[true/false]?AbapDebug=[true/false]  
```  
  
 Los componentes del URI de conexión se explican en las secciones siguientes.  
  
### <a name="the-sap-connection-uri-scheme"></a>El esquema de URI de conexión de SAP  
 El esquema para el URI de conexión de SAP es "sap".  
  
### <a name="user-information-in-the-sap-connection-uri"></a>Información de usuario en el URI de conexión de SAP  
 La información de usuario (userinfoparams) en la conexión de SAP que URI se representa como una colección de nombre / valor de los parámetros necesarios para la autenticación de usuario, la identificación de cliente y la especificación del lenguaje. En la tabla siguiente se describe estos parámetros.  
  
|Propiedad|Description|  
|--------------|-----------------|  
|Usuario|El nombre de usuario en el sistema SAP; Este valor distingue mayúsculas de minúsculas. Debe establecer el **AcceptCredentialsInUri** enlazar la propiedad a **true** para especificar el nombre de usuario y la contraseña en el URI de conexión. **Nota:** el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] conserva el caso del valor que especifique para el nombre de usuario cuando se abre una conexión en el sistema SAP.|  
|Passwd|La contraseña para el usuario en el sistema SAP; Este valor distingue mayúsculas de minúsculas. Debe establecer el **AcceptCredentialsInUri** enlazar la propiedad a **true** para especificar el nombre de usuario y la contraseña en el URI de conexión. **Nota:** el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] conserva el caso del valor que especifique para la contraseña cuando se abre una conexión en el sistema SAP.|  
|Cliente|El identificador de cliente del sistema SAP.|  
|Lenguaje|Idioma.|  
|UseSnc|Parámetro opcional que especifica si las comunicaciones de red segura de SAP (SNC) está habilitada. El valor puede ser True o False. Si es True, se habilita SNC. El valor predeterminado es False<br /><br /> Cuando se habilita SNC, también debe establecer el **SncPartnerName** y **SncLibrary** propiedades de enlace. Para obtener más información, consulte [obtener información sobre el adaptador de BizTalk para propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).<br /><br /> Si se habilita SNC y el URI de conexión contiene credenciales, el adaptador lanza una excepción. **Nota:** UseSnc parámetro de conexión sólo es aplicable para los tipos de conexión A y B. Los tipos de conexión diferentes y su importancia se describe en detalle más adelante en este tema.|  
  
> [!NOTE]
>  Debe especificar el cliente y el idioma en el URI de conexión de SAP.  
  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] superficies la **AcceptCredentialsinUri** propiedad de enlace, por lo que puede controlar si las credenciales del sistema SAP se pueden especificar en el URI de conexión. Esto es porque las credenciales se representan como texto sin formato en el URI de conexión y esto supone un riesgo de seguridad inherente. De forma predeterminada, el **AcceptCredentialsInUri** enlaza la propiedad es false y el adaptador produce una excepción si se especifican las credenciales en el URI de conexión.  
  
 Hay algunos escenarios en los que es necesario especificar credenciales en la conexión URI; Por ejemplo, para recibir las operaciones de entrada de SAP de sistema cuando se usa WCF servicio modelo o el modelo de canal WCF. Puede establecer la **AcceptCredentialsInUri** propiedad en true para estos escenarios. Es una práctica recomendada, sin embargo, para evitar proporcionar las credenciales directamente en el URI de conexión. Para obtener más información acerca de cómo proporcionar de forma más segura credenciales para la conexión de SAP, consulte [proteger sus aplicaciones de SAP](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md).  
  
> [!IMPORTANT]
>  Si habilita las comunicaciones de red seguro (SNC) estableciendo el parámetro UseSnc en true, el adaptador lanza una excepción.  
  
### <a name="host-information-in-the-sap-connection-uri"></a>Información del host en el URI de conexión de SAP  
 La información de host SAP (hostinfoparams) se representa mediante los siguientes elementos en el URI de conexión de SAP: `connectiontype/conndetail1/conndetail2`. Estos parámetros especifican detalles acerca de la conexión de cliente al sistema SAP. Detalles adicionales sobre la conexión de cliente SAP, así como detalles que establecer una conexión como un agente de escucha para un destino RFC de SAP pueden especificarse en el query_string. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite los siguientes tipos de conexión de cliente en el URI de conexión de SAP:  
  
-   R: un host de aplicación en función de conexión en el que el URI de conexión especifica un servidor de aplicaciones a través del cual el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] se conecta a SAP.  
  
-   B: una carga equilibrada de conexión en el que el URI de conexión especifica un servidor de mensajes a través del cual el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] se conecta a SAP.  
  
-   D: una conexión basada en destino en el que el URI de conexión especifica un destino en el archivo saprfc.ini que contiene los parámetros de conexión de SAP.  

    > [!NOTE]
    > Conexión de tipo B solo se aplica a los puertos de envío.  Al configurar una ubicación de recepción, elija un tipo de conexión o D.
  
 En la tabla siguiente describe cómo se especifican estas conexiones en el URI de conexión de SAP.  
  
|Tipo de conexión|Conndetail1|Conndetail2|Description|  
|---------------------|-----------------|-----------------|-----------------|  
|Un|ASHOST (Host de servidor de aplicación)|SYSNR (número de sistema SAP)|Especifica una conexión basada en host de aplicación. Para una conexión basada en host de aplicación, un Host de puerta de enlace y el servicio de puerta de enlace opcionales pueden especificarse en el query_string.|  
|B|MSHOST (Host de servidor de mensaje)|R3NAME (nombre SAP R3)|Especifica una conexión a través de un servidor de mensajes de equilibrio de carga. Para una conexión de equilibrio de carga, un grupo de servidor opcional y el servicio de mensaje pueden especificarse en el query_string.|  
|D|DESTINO (destino que contiene los parámetros de conexión en el archivo saprfc.ini)|--|Especifica una conexión basada en destino. Los parámetros de conexión de SAP se encuentran en el destino especificado en el archivo saprfc.ini. Sólo las conexiones de tipo A y B-type se pueden especificar en el destino.|  
  
> [!NOTE]
>  Si se especifican valores de conexión en el archivo saprfc.ini, asegúrese de que el archivo se encuentra en la misma carpeta como el .exe al acceder al archivo o en una ubicación estándar según sea necesario por el sistema SAP. Para obtener más información, consulte la documentación de SAP.  
  
### <a name="query-information-in-the-sap-connection-uri"></a>Información de la consulta en el URI de conexión de SAP  
 La información de consulta (query_string) en el URI de conexión de SAP contiene parámetros opcionales que se pueden incluidos para especificar lo siguiente:  
  
-   Detalles de conexión adicionales para las conexiones basadas en host de aplicación (A).  
  
-   Detalles de conexión adicionales para cargar las conexiones equilibrio (B).  
  
-   Detalles de agente de escucha que se especifican un destino RFC en el sistema SAP a través del cual el sistema SAP puede enviar las solicitudes de cambio, TRFCs e IDOC a la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
-   Si desea habilitar las comunicaciones de red segura de SAP (SNC).  
  
-   Detalles que especifican la configuración de depuración.  
  
 Parámetros de consulta son opcionales; No obstante, deben especificarse los detalles de agente de escucha para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] para que actúe como un servidor RFC.  
  
 En la tabla siguiente se describe los parámetros de consulta y se indica los tipos de conexión de SAP para el que son válidos.  
  
|Valor|Tipo de conexión válido|Description|  
|-----------|---------------------------|-----------------|  
|GwHost|Un|Especifica el nombre de un host de puerta de enlace opcional en una conexión basada en host de aplicación.|  
|GwServ|Un|Especifica el nombre de un servicio de puerta de enlace opcional en una conexión basada en host de aplicación.|  
|MsServ|B|Especifica el nombre de un servicio de mensaje opcional en una conexión de equilibrio de carga.|  
|Grupo|B|Especifica un grupo opcional de servidores de aplicaciones en una conexión de equilibrio de carga.|  
|ListenerDest|(R)|Especifica un destino opcional en el archivo saprfc.ini en una conexión de servidor rfc. El destino debe especificar una conexión de tipo R.|  
|ListenerGwHost|(R)|Especifica el host de puerta de enlace para una conexión al servidor rfc. Este parámetro es opcional; Sin embargo, si se desea una conexión de servidor rfc y LISTENERDEST no se especifica o no hay ningún host de puerta de enlace especificado por el destino en el archivo saprfc.ini, LISTENERGWHOST debe contener un host de puerta de enlace válida.|  
|ListenerGwServ|(R)|Especifica el servicio de puerta de enlace para una conexión al servidor rfc. Este parámetro es opcional; Sin embargo, si se desea una conexión de servidor rfc y LISTENERDEST no se especifica o no se especifica ningún servicio de puerta de enlace por el destino en el archivo saprfc.ini, LISTENERGWSERV debe contener un servicio de puerta de enlace válida.|  
|ListenerProgramId|(R)|Especifica el identificador de programa para una conexión al servidor rfc. Este parámetro es opcional; Sin embargo, si se desea una conexión de servidor rfc y LISTENERDEST no se especifica o no se especifica ningún servicio de puerta de enlace por el destino en el archivo saprfc.ini, LISTENERPROGRAMID debe contener un servicio de puerta de enlace válida.|  
|RfcSdkTrace|Todos|Parámetro opcional que especifica si está habilitado el seguimiento de la biblioteca RFC. El valor puede ser True o False. Si es True, está habilitado el seguimiento de la biblioteca de RFC. El valor predeterminado es False.<br /><br /> El nivel de seguimiento habilitado por el parámetro RfcSdkTrace depende de la variable de entorno RFC_TRACE.<br /><br /> -Si RFC_TRACE no presente o se establece en 0, se habilita el nivel mínimo de seguimiento.<br />-RFC_TRACE se puede establecer en 1 o 2 para aumentar el nivel de seguimiento.|  
|AbapDebug|Todos|Parámetro opcional que especifica si ABAP depuración desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] está habilitado. El valor puede ser True o False. Si es True, está habilitada la depuración de ABAP. El valor predeterminado es False. Si AbapDebug es True, se abre la GUI de SAP.|  
  
 Los parámetros en la cadena de consulta son parámetros SAP y sus valores se definen por SAP. Para obtener más información acerca de estos parámetros, consulte la documentación de SAP.  
  
 A continuación muestra un URI de conexión de ejemplo para una conexión basada en host de aplicación:  
  
```  
sap://Client=800;lang=EN@A/YourSAPHOST/00  
```  
  
## <a name="connection-uri-properties-in-the-configure-adapter-dialog-box"></a>Propiedades URI de conexión en el cuadro de diálogo adaptador configurar  
 Cuando se conecta al sistema SAP con el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] o [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] establecer la conexión de los parámetros URI de la **propiedades de URI** pestaña en el **configurar el adaptador de** cuadro de diálogo. En la tabla siguiente se muestra cómo se muestran las propiedades URI en el **propiedades de URI** hoja. (Se enumeran las propiedades URI por grupo en el orden en que aparecen en la hoja de propiedades del URI.)  
  
|Categoría|Propiedad URI|Parte del URI|  
|--------------|------------------|--------------|  
|Servidor de aplicaciones|Host de servidor de aplicación|Conndetail1 (un tipo de conexión de información de host)|  
|Servidor de aplicaciones|Host de puerta de enlace|GwHost (cadena de consulta)|  
|Servidor de aplicaciones|Servicio de puerta de enlace|GwServ (cadena de consulta)|  
|Servidor de aplicaciones|Número del sistema|Conndetail2 (un tipo de conexión de información de host)|  
|Destino|Nombre de destino|Conndetail1 (tipo de conexión de información D de host)|  
|Diagnósticos|Seguimiento RFC|RfcSdkTrace (cadena de consulta)|  
|Diagnósticos|Depuración ABAP|AbapDebug (cadena de consulta)|  
|Información de inicio de sesión|Cliente|Cliente (userinfoparams)|  
|Información de inicio de sesión|Lenguaje|Idioma (userinfoparams)|  
|Servidor de mensajes|Nombre de grupo de servidores de aplicación|Grupo (cadena de consulta)|  
|Servidor de mensajes|Host de servidor de mensaje|Conndetail1 (tipo de conexión de información B de host)|  
|Servidor de mensajes|Servicio del servidor de mensajes|MsServ (cadena de consulta)|  
|Servidor de mensajes|Nombre del sistema R/3|Conndetail2 (tipo de conexión de información B de host)|  
|Varios|Tipo de conexión|Tipo de conexión (información de host: A, B o D)|  
|Servidor RFC|Nombre de destino|ListenerDest (cadena de consulta)|  
|Servidor RFC|Host de puerta de enlace|ListenerGwHost (cadena de consulta)|  
|Servidor RFC|Servicio de puerta de enlace|ListenerGwServ (cadena de consulta)|  
|Servidor RFC|Id. de programa|ListenerProgramId (cadena de consulta)|  
|SNC|UseSnc|UseSnc (información de usuario)|  
  
## <a name="how-to-specify-a-connection-uri-for-rfc-server-connections"></a>Cómo especificar un URI de conexión para las conexiones de servidor de RFC.  
 Para crear una dirección de extremo a través del cual el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] puede actuar como un servidor RFC, debe especificar un identificador de programa SAP, un host de puerta de enlace SAP y un servicio de puerta de enlace SAP que corresponden a un destino RFC en el sistema SAP. Para obtener información acerca de cómo configurar un destino RFC en SAP, consulte [crear una solicitud de cambio, el destino de RFC y enviar una solicitud de cambio de SAP](creating-an-rfc-in-an-sap-system.md).  
  
 Puede especificar el Id. de programa, el host de puerta de enlace y el servicio de puerta de enlace en la conexión de URI de una de dos maneras:  
  
-   al establecer los parámetros de consulta ListenerGwHost, ListenerGwServ y ListenerProgramId  
  
-   estableciendo el parámetro de consulta ListenerDest a un destino en el archivo saprfc.ini especifica una conexión de tipo R.  
  
> [!NOTE]
>  Si se especifican valores de conexión en el archivo saprfc.ini, asegúrese de que el archivo reside en la misma ubicación que el .exe al acceder al archivo o en una ubicación estándar según sea necesario por el sistema SAP. Para obtener más información, consulte la documentación de SAP.  
  
 Para especificar un URI de conexión para una conexión al servidor RFC, especifique una conexión de cliente normal con un destino de RFC especificado en la cadena de consulta, como en el ejemplo siguiente:  
  
```  
sap://Client=800;lang=EN@A/YourSAPHOST/00?ListenerGwHost=YourSAPHOST&ListenerGwServ=SAPGW00&ListenerProgramId=MyProgramId  
```  
  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] usa la información contenida en la parte userinfoparams y hostinfoparams del URI de conexión para recuperar metadatos desde el sistema SAP y utiliza la información proporcionada por los parámetros de agente de escucha en la cadena de consulta para registrarse a sí misma como un agente de escucha en el destino de RFC de SAP.  
  
## <a name="using-reserved-characters-in-the-connection-uri"></a>Utilizar caracteres reservados en el URI de conexión  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] no admite la especificación de un URI que incluye caracteres especiales para cualquiera de los valores de parámetros de conexión. Si los valores de parámetro de conexión contienen caracteres especiales, asegúrese de que se realice una de las siguientes acciones:  
  
-   Si se especifica el URI en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] con [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], debe especificarlos tal-está en la **propiedades de URI** pestaña, es decir, sin usar cualquier carácter de escape. Si especifica el URI directamente en el **configurar un URI** campo y los parámetros de conexión contienen caracteres reservados, debe especificar los parámetros de conexión con caracteres de escape adecuados.  
  
-   Si se especifica el URI al crear un envío o recepción puerto en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración y los parámetros de conexión contienen caracteres reservados, debe especificar los parámetros de conexión con caracteres de escape adecuados.  
  
## <a name="using-the-connection-uri-to-connect-to-the-sap-system"></a>Usar el URI de conexión para conectarse al sistema SAP  
 Para obtener información acerca de cómo establecer una conexión con el sistema SAP cuando es:  
  
-   Use la [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] o [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], consulte [conectar con el sistema SAP en Visual Studio](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md).  
  
-   Configurar un puerto de envío o recepción (ubicación) del puerto en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución, consulte [configurar manualmente un enlace de puerto físico para el adaptador SAP](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md).  
  
-   Utilizar el modelo de canal WCF en una solución de programación, vea [crear un canal con SAP](../../adapters-and-accelerators/adapter-sap/create-a-channel-using-sap.md).  
  
-   Utilizar el modelo de servicio WCF en una solución de programación, vea [configurar un enlace para el sistema SAP de cliente](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md).  
  
-   Utilice WCF ServiceModel Metadata Utility Tool (svcutil.exe), consulte [mediante la herramienta de utilidad de metadatos de ServiceModel con el adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-servicemodel-metadata-utility-with-the-sap-adapter-in-biztalk.md).  
  
## <a name="see-also"></a>Vea también  
 [Crear una conexión con el sistema SAP.](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md)