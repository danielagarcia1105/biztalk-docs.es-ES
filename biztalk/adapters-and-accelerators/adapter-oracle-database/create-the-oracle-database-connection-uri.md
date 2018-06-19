---
title: Crear el URI de conexión de base de datos de Oracle | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection URI, basic format of
- connection URI, database credentials and
- connection URI, connecting to the Oracle database
- connection URI
ms.assetid: 17d0a6d3-1b0c-43d6-a705-402c09a78ee0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45f7b0fcc0c83bd4a844ac1a83488e1a3e8d9a65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217476"
---
# <a name="create-the-oracle-database-connection-uri"></a>Crear el URI de conexión de base de datos de Oracle
El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] URI de conexión contiene propiedades que el adaptador utiliza para establecer una conexión con la base de datos de Oracle. Este tema proporciona información sobre cómo especificar el URI de conexión para conectarse a la base de datos de Oracle mediante tnsnames.ora y sin utilizar tnsnames.ora. También proporciona información sobre cómo usar el URI de conexión para conectarse a la base de datos de Oracle.  
  
## <a name="connection-uri-to-connect-to-the-oracle-database-using-tnsnamesora"></a>URI de conexión para conectarse a la base de datos de Oracle mediante tnsnames.ora  
  
> [!IMPORTANT]
>  -   En este caso, debe agregar la entrada de nombre de servicio de red en el archivo tnsnames.ora en el equipo con el cliente de adaptador instalado. Para obtener más información acerca de la entrada de nombre de servicio de red, consulte [configurar el cliente de Oracle para el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md).  
> -   Debido a una limitación del cliente de Oracle, el **DataSourceName** parámetro (nombre de servicio de red) en el URI de conexión no puede contener más de 39 caracteres si va a realizar las operaciones en una transacción. Por lo tanto, asegúrese de que el valor especificado para la **DataSourceName** parámetro es menor o igual a 39 caracteres si va a realizar las operaciones en una transacción.  
  
 Un punto de conexión típica dirección URI en [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] se representa como: `scheme://userauthparams@hostinfoparams?query_string`, donde:  
  
-   esquema es el nombre de esquema.  
  
-   userauthparams es una colección de nombre y valor de los parámetros necesarios para la autenticación de usuario por el punto de conexión.  
  
-   hostinfoparams es la información necesaria para establecer la conexión con el host; Por ejemplo, una ruta de acceso.  
  
-   QUERY_STRING es una colección de nombre y valor opcional de parámetros delimitados por un signo de interrogación (?).  
  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] conexión URI se ajusta a este formato básico y se implementa como sigue:  
  
```  
oracledb://User=[USER_NAME];Password=[PASSWORD]@[NET_SERVICE_NAME]?PollingId=[POLLING_ID]  
```  
  
 La siguiente tabla explica las propiedades contenidas en el URI de conexión.  
  
|Propiedad URI de conexión|Categoría|Description|  
|-----------------------------|--------------|-----------------|  
|[NOMBREDEUSUARIO]|userauthparams|El nombre de usuario que se utilizará para la autenticación en la base de datos de Oracle; Por ejemplo, SCOTT. Debe establecer el **AcceptCredentialsInUri** enlazar la propiedad a **true** para especificar el nombre de usuario y la contraseña en el URI de conexión.<br /><br /> **Tenga en cuenta** el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] conserva el caso del valor que especifique para el nombre de usuario cuando se abre una conexión en la base de datos de Oracle. Nombres de usuario en la base de datos de Oracle distinguen entre mayúsculas y minúsculas. Debe asegurarse de que proporciona los nombres de usuario de Oracle para el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] en el caso esperado por la base de datos de Oracle. Normalmente, esto significa que el nombre de usuario de la credencial de SCOTT/TIGER debería estar mayúsculas: "SCOTT".|  
|[CONTRASEÑA]|userauthparams|La contraseña que se utilizará para la autenticación en la base de datos de Oracle; Por ejemplo, "Tiger". Debe establecer el **AcceptCredentialsInUri** enlazar la propiedad a **true** para especificar el nombre de usuario y la contraseña en el URI de conexión.<br /><br /> **Tenga en cuenta** el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] conserva el caso del valor que especifique para la contraseña cuando se abre una conexión en la base de datos de Oracle. Para obtener la versión 10g y versiones anteriores, las contraseñas en el sistema Oracle no distinguen mayúsculas de minúsculas.|  
|[NET_SERVICE_NAME]|hostinfoparams|Un nombre de servicio de red que se especifica en el archivo tnsnames.ora en el equipo donde el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] está instalado. Para obtener más información acerca de los nombres de servicio de red y tnsnames.ora, consulte [configurar el cliente de Oracle para el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md).|  
|[POLLING_ID]|QUERY_STRING|Una cadena opcional que se debe anexar por el adaptador para el espacio de nombres estándar de la operación de POLLINGSTMT. Esto le permite especificar un espacio de nombres único para cada operación de sondeo cuando un proyecto contiene varias operaciones de sondeo. No es necesario especificar una cadena de PollingId si el proyecto contiene una única operación de POLLINGSTMT.|  
  
> [!NOTE]
>  Parámetros de consulta también se usan en el URI de conexión cuando se especifica una dirección de punto de conexión para un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] cliente de intercambio de metadatos.  
  
## <a name="connection-uri-to-connect-to-the-oracle-database-without-using-tnsnamesora"></a>URI de conexión para conectarse a la base de datos de Oracle sin usar tnsnames.ora  
  
> [!IMPORTANT]
>  -   En este caso, el nombre de servicio de red en el archivo tnsnames.ora o el propio archivo tnsnames.ora real no necesita estar presente en el equipo cliente.  
> -   No se admite este modo de conectividad si va a realizar las operaciones en una transacción. Esto es debido a una limitación del cliente de Oracle.  
  
 Un punto de conexión típica dirección URI en [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] se representa como: `scheme://userauthparams@hostinfoparams?query_string`, donde:  
  
-   esquema es el nombre de esquema.  
  
-   userauthparams es una colección de nombre y valor de los parámetros necesarios para la autenticación de usuario por el punto de conexión.  
  
-   hostinfoparams es la información necesaria para establecer la conexión con el host; Por ejemplo, nombre del servidor, número de puerto, etcetera.  
  
-   QUERY_STRING es una colección de nombre y valor opcional de parámetros delimitados por un signo de interrogación (?).  
  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] conexión URI se ajusta a este formato básico y se implementa como sigue:  
  
```  
oracledb://User=[USER_NAME];Password=[PASSWORD]@[SERVER_NAME]:[PORT_NUMBER]/[SERVICE_NAME]/SERVICE_TYPE]?PollingId=[POLLING_ID]  
```  
  
 La siguiente tabla explica las propiedades contenidas en el URI de conexión.  
  
|Propiedad URI de conexión|Categoría|Description|  
|-----------------------------|--------------|-----------------|  
|[NOMBREDEUSUARIO]|userauthparams|El nombre de usuario que se utilizará para la autenticación en la base de datos de Oracle; Por ejemplo, SCOTT. Debe establecer el **AcceptCredentialsInUri** enlazar la propiedad a **true** para especificar el nombre de usuario y la contraseña en el URI de conexión.<br /><br /> **Tenga en cuenta** el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] conserva el caso del valor que especifique para el nombre de usuario cuando se abre una conexión en la base de datos de Oracle. Nombres de usuario en la base de datos de Oracle distinguen entre mayúsculas y minúsculas. Debe asegurarse de que proporciona los nombres de usuario de Oracle para el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] en el caso esperado por la base de datos de Oracle. Normalmente, esto significa que el nombre de usuario de la credencial de SCOTT/TIGER debería estar mayúsculas: "SCOTT".|  
|[CONTRASEÑA]|userauthparams|La contraseña que se utilizará para la autenticación en la base de datos de Oracle; Por ejemplo, "Tiger". Debe establecer el **AcceptCredentialsInUri** enlazar la propiedad a **true** para especificar el nombre de usuario y la contraseña en el URI de conexión.<br /><br /> **Tenga en cuenta** el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] conserva el caso del valor que especifique para la contraseña cuando se abre una conexión en la base de datos de Oracle. Para obtener la versión 10g y versiones anteriores, las contraseñas en el sistema Oracle no distinguen mayúsculas de minúsculas.|  
|[NOMBREDESERVIDOR]|hostinfoparams|Nombre del servidor en el que se ejecuta la base de datos de Oracle. Esto es obligatorio.|  
|[PORT_NUMBER]|hostinfoparams|El puerto de escucha de red de Oracle. Si no se especifica ningún valor, el adaptador toma el valor predeterminado 1521.|  
|[SERVICE_NAME]|hostinfoparams|El nombre de servicio de base de datos de Oracle. Esto es obligatorio.|  
|[SERVICE_TYPE]|hostinfoparams|El tipo de servicio de Oracle. Los valores posibles son **dedicado** o **Shared**. Un servicio dedicado utiliza un proceso de servidor dedicado para atender el proceso de un solo usuario. Un servicio compartido utiliza un proceso de servidor compartido que puede que puede atender varios procesos de usuario. Valor predeterminado es **dedicado**.|  
|[POLLING_ID]|QUERY_STRING|Una cadena opcional que se debe anexar por el adaptador para el espacio de nombres estándar de la operación de POLLINGSTMT. Esto le permite especificar un espacio de nombres único para cada operación de sondeo cuando un proyecto contiene varias operaciones de sondeo. No es necesario especificar una cadena de PollingId si el proyecto contiene una única operación de POLLINGSTMT.|  
  
> [!NOTE]
>  Parámetros de consulta también se usan en el URI de conexión cuando se especifica una dirección de punto de conexión para un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] cliente de intercambio de metadatos.  
  
## <a name="oracle-database-credentials-and-the-connection-uri"></a>Credenciales de base de datos de Oracle y el URI de conexión  
 De forma predeterminada, la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] produce una excepción cuando se especifican las credenciales de la base de datos de Oracle en el URI de conexión. Esto es porque estas credenciales se representan como texto sin formato en el URI de conexión, y esto supone un riesgo de seguridad. Puede establecer la **AcceptCredentialsInUri** propiedad de enlace para controlar si el URI de conexión puede contener las credenciales para la base de datos de Oracle. Si el **AcceptCredentialsInUri** propiedad es **false**, [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] produce una excepción si el URI de conexión contiene credenciales de base de datos de Oracle; si la propiedad es **true** , se inicia ninguna excepción. Hay algunos escenarios limitados en el que es necesario especificar credenciales en la conexión URI; Por ejemplo, para recibir la entrada POLLINGSTMT operación cuando se usa WCF servicio modelo o el modelo de canal WCF. Para la mayoría de los casos, sin embargo, no debe proporcionar las credenciales en el URI de conexión. Para obtener más información acerca de cómo proporcionar de forma más segura credenciales para la base de datos de Oracle, vea [proteger sus aplicaciones de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md).  
  
> [!IMPORTANT]
>  Debido a los riesgos de seguridad asociados al pasar las credenciales en las cadenas como texto sin formato, no debe especificar las credenciales de conexión de base de datos de Oracle en el URI de conexión.  
  
## <a name="using-reserved-characters-in-the-connection-uri"></a>Utilizar caracteres reservados en el URI de conexión  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite la especificación de un URI que incluye caracteres especiales para cualquiera de los valores de parámetros de conexión. Si los valores de parámetro de conexión contienen caracteres especiales, asegúrese de que se realice una de las siguientes acciones:  
  
-   Si se especifica el URI en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] con [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], debe especificarlos tal-está en la **propiedades de URI** pestaña, es decir, sin usar cualquier carácter de escape. Si especifica el URI directamente en el **configurar un URI** campo y los parámetros de conexión contienen caracteres reservados, debe especificar los parámetros de conexión con caracteres de escape adecuados.  
  
-   Si se especifica el URI al crear un envío o recepción puerto en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración y los parámetros de conexión contienen caracteres reservados, debe especificar los parámetros de conexión con caracteres de escape adecuados.  
  
## <a name="using-the-connection-uri-to-connect-to-the-oracle-database"></a>Usar el URI de conexión para conectarse a la base de datos de Oracle  
 El siguiente es un ejemplo de un URI de conexión para [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
|Usar tnsnames.ora|Sin usar tnsnames.ora|  
|------------------------|--------------------------------|  
|`oracledb://ADAPTER`<br /><br /> En este ejemplo, el adaptador es un nombre de servicio de red que está asociado con la información de conexión y el nombre del servicio de la base de datos de Oracle de destino en tnsnames.ora.|`oracledb://yourOracleServer:1521/yourOracleDatabaseServiceName/Dedicated`<br /><br /> En este ejemplo, el nombre del servidor es "yourOracleServer" y el nombre del servicio es "yourOracleDatabaseServiceName".|  
  
 El siguiente es un ejemplo de un URI de conexión para una operación de POLLINGSTMT. Este URI incluye un parámetro de PollingId para modificar el espacio de nombres de la operación de POLLINGSTMT.  
  
|Usar tnsnames.ora|Sin usar tnsnames.ora|  
|------------------------|--------------------------------|  
|`oracledb://ADAPTER?PollingId=MyPollingNotification1`|`oracledb://yourOracleServer:1521/yourOracleDatabaseServiceName/Dedicated? PollingId=MyPollingNotification1`|  
  
 Para la conexión anterior URI, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] crea el siguiente espacio de nombres para la operación de POLLINGSTMT.  
  
```  
http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTMyPollingNotification1  
```  
  
 Para obtener información acerca de cómo establecer una conexión con Oracle con la base de datos al:  
  
-   Use la [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] o [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], consulte [conectar con base de datos de Oracle en Visual Studio mediante el servicio de adaptador](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service.md).  
  
-   Configurar un puerto de envío o recepción (ubicación) del puerto en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución, consulte [configurar manualmente un enlace de puerto físico para el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md).  
  
-   Utilizar el modelo de canal WCF en una solución de programación, vea [crear un canal con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md).  
  
-   Utilizar el modelo de servicio WCF en una solución de programación, vea [configurar un cliente de enlace de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-a-client-binding-for-the-oracle-database.md).  
  
-   Utilice WCF ServiceModel Metadata Utility Tool (svcutil.exe), consulte [mediante la herramienta de utilidad de metadatos de ServiceModel con el adaptador de BizTalk para base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/use-the-servicemodel-metadata-utility-with-the-oracle-db-adapter-in-biztalk.md).  
  
## <a name="see-also"></a>Vea también  
[Crear una conexión a la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)   
 [Configurar al cliente de Oracle para el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md)