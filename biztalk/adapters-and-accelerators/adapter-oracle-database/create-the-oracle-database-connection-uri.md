---
title: Crear el URI de conexión de base de datos de Oracle | Microsoft Docs
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
ms.openlocfilehash: dee680c0e27f0d5456c54701c4f385b2c629e146
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975877"
---
# <a name="create-the-oracle-database-connection-uri"></a>Crear el URI de conexión de base de datos de Oracle
El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] URI de conexión contiene propiedades que el adaptador utiliza para establecer una conexión a la base de datos de Oracle. En este tema se proporciona información sobre cómo especificar el URI de conexión para conectarse a la base de datos de Oracle mediante tnsnames.ora y sin utilizar tnsnames.ora. También proporciona información sobre cómo usar el URI de conexión para conectarse a la base de datos de Oracle.  

## <a name="connection-uri-to-connect-to-the-oracle-database-using-tnsnamesora"></a>URI de conexión para conectarse a la base de datos de Oracle mediante tnsnames.ora  

> [!IMPORTANT]
> - Este enfoque, debe agregar la entrada del nombre de servicio de red en el archivo tnsnames.ora en el equipo con el cliente de adaptador instalado. Para obtener más información acerca de la entrada de nombre de servicio de red, consulte [configurar el cliente de Oracle para el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md).  
>   -   Debido a una limitación del cliente de Oracle, el **DataSourceName** parámetro (nombre de servicio de red) en el URI de conexión no puede contener más de 39 caracteres si va a realizar operaciones en una transacción. Por lo tanto, asegúrese de que el valor especificado para el **DataSourceName** parámetro es menor o igual a 39 caracteres si va a realizar operaciones en una transacción.  

 Un punto de conexión típica dirección URI en [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] se representa como: `scheme://userauthparams@hostinfoparams?query_string`, donde:  

- esquema es el nombre de esquema.  

- userauthparams es una colección de nombre y valor de los parámetros necesarios para la autenticación de usuario por el punto de conexión.  

- hostinfoparams es la información necesaria para establecer la conexión al host; Por ejemplo, una ruta de acceso.  

- QUERY_STRING es una colección de nombre y valor opcional de parámetros que se delimitan mediante un signo de interrogación (?).  

  El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] conexión URI se adhiere a este formato básico y se implementa como sigue:  

```  
oracledb://User=[USER_NAME];Password=[PASSWORD]@[NET_SERVICE_NAME]?PollingId=[POLLING_ID]  
```  

 En la tabla siguiente se explica las propiedades contenidas en el URI de conexión.  


| Propiedad URI de conexión |    Categoría    |                                                                                                                                                                                                                                                                                                                                                                                           Descripción                                                                                                                                                                                                                                                                                                                                                                                            |
|-------------------------|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|       [NOMBREUSUARIO]       | userauthparams | El nombre de usuario que se usará para la autenticación en la base de datos de Oracle; Por ejemplo, SCOTT. Debe establecer el **AcceptCredentialsInUri** enlazar la propiedad a **true** para especificar el nombre de usuario y la contraseña en el URI de conexión.<br /><br /> **Tenga en cuenta** el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] conserva el caso del valor que especifique para el nombre de usuario cuando se abre una conexión en la base de datos de Oracle. Los nombres de usuario en la base de datos de Oracle distinguen mayúsculas de minúsculas. Debe asegurarse de que proporciona los nombres de usuario de Oracle para el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] en el caso esperado por la base de datos de Oracle. Normalmente, esto significa que el nombre de usuario de la credencial de SCOTT/TIGER debe ser letras mayúsculas: "SCOTT". |
|       [CONTRASEÑA]        | userauthparams |                                                                                                                                La contraseña que se utilizará para la autenticación en la base de datos de Oracle; Por ejemplo, TIGER. Debe establecer el **AcceptCredentialsInUri** enlazar la propiedad a **true** para especificar el nombre de usuario y la contraseña en el URI de conexión.<br /><br /> **Tenga en cuenta** el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] conserva el caso del valor que escriba la contraseña cuando se abre una conexión en la base de datos de Oracle. Para la versión 10g y versiones anteriores, las contraseñas en el sistema Oracle no distinguen mayúsculas de minúsculas.                                                                                                                                |
|   [NET_SERVICE_NAME]    | hostinfoparams |                                                                                                                                                                            Un nombre de servicio de red que se especifica en el archivo tnsnames.ora en el equipo donde el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] está instalado. Para obtener más información sobre los nombres de servicio de red y de tnsnames.ora, consulte [configurar el cliente de Oracle para el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md).                                                                                                                                                                             |
|      [POLLING_ID]       |  QUERY_STRING  |                                                                                                                                                                                                                     Una cadena opcional que se debe anexar el adaptador al espacio de nombres estándar de la operación POLLINGSTMT. Esto le permite especificar un espacio de nombres único para cada operación de sondeo cuando un proyecto contiene varias operaciones de sondeo. No es necesario especificar una cadena de PollingId si el proyecto contiene una única operación POLLINGSTMT.                                                                                                                                                                                                                      |

> [!NOTE]
>  Parámetros de consulta también se usan en el URI de conexión cuando se especifica una dirección de punto de conexión para un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] cliente de intercambio de metadatos.  

## <a name="connection-uri-to-connect-to-the-oracle-database-without-using-tnsnamesora"></a>URI de conexión para conectarse a la base de datos de Oracle sin usar tnsnames.ora  

> [!IMPORTANT]
> - Este enfoque, el nombre de servicio de red en el archivo tnsnames.ora, o el propio archivo tnsnames.ora real no necesita estar presente en el equipo cliente.  
>   -   No se admite este modo de conectividad si va a realizar operaciones en una transacción. Esto es debido a una limitación del cliente de Oracle.  

 Un punto de conexión típica dirección URI en [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] se representa como: `scheme://userauthparams@hostinfoparams?query_string`, donde:  

- esquema es el nombre de esquema.  

- userauthparams es una colección de nombre y valor de los parámetros necesarios para la autenticación de usuario por el punto de conexión.  

- hostinfoparams es la información necesaria para establecer la conexión al host; Por ejemplo, nombre del servidor, número de puerto, etcetera.  

- QUERY_STRING es una colección de nombre y valor opcional de parámetros que se delimitan mediante un signo de interrogación (?).  

  El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] conexión URI se adhiere a este formato básico y se implementa como sigue:  

```  
oracledb://User=[USER_NAME];Password=[PASSWORD]@[SERVER_NAME]:[PORT_NUMBER]/[SERVICE_NAME]/SERVICE_TYPE]?PollingId=[POLLING_ID]  
```  

 En la tabla siguiente se explica las propiedades contenidas en el URI de conexión.  


| Propiedad URI de conexión |    Categoría    |                                                                                                                                                                                                                                                                                                                                                                                           Descripción                                                                                                                                                                                                                                                                                                                                                                                            |
|-------------------------|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|       [NOMBREUSUARIO]       | userauthparams | El nombre de usuario que se usará para la autenticación en la base de datos de Oracle; Por ejemplo, SCOTT. Debe establecer el **AcceptCredentialsInUri** enlazar la propiedad a **true** para especificar el nombre de usuario y la contraseña en el URI de conexión.<br /><br /> **Tenga en cuenta** el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] conserva el caso del valor que especifique para el nombre de usuario cuando se abre una conexión en la base de datos de Oracle. Los nombres de usuario en la base de datos de Oracle distinguen mayúsculas de minúsculas. Debe asegurarse de que proporciona los nombres de usuario de Oracle para el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] en el caso esperado por la base de datos de Oracle. Normalmente, esto significa que el nombre de usuario de la credencial de SCOTT/TIGER debe ser letras mayúsculas: "SCOTT". |
|       [CONTRASEÑA]        | userauthparams |                                                                                                                                La contraseña que se utilizará para la autenticación en la base de datos de Oracle; Por ejemplo, TIGER. Debe establecer el **AcceptCredentialsInUri** enlazar la propiedad a **true** para especificar el nombre de usuario y la contraseña en el URI de conexión.<br /><br /> **Tenga en cuenta** el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] conserva el caso del valor que escriba la contraseña cuando se abre una conexión en la base de datos de Oracle. Para la versión 10g y versiones anteriores, las contraseñas en el sistema Oracle no distinguen mayúsculas de minúsculas.                                                                                                                                |
|      [NOMBREDESERVIDOR]      | hostinfoparams |                                                                                                                                                                                                                                                                                                                                                          Nombre del servidor en el que se está ejecutando la base de datos de Oracle. Esto es obligatorio.                                                                                                                                                                                                                                                                                                                                                          |
|      [PORT_NUMBER]      | hostinfoparams |                                                                                                                                                                                                                                                                                                                                                El puerto de escucha de Oracle Net. Si se especifica ningún valor, el adaptador toma el valor predeterminado 1521.                                                                                                                                                                                                                                                                                                                                                 |
|     [SERVICE_NAME]      | hostinfoparams |                                                                                                                                                                                                                                                                                                                                                                       El nombre de servicio de base de datos de Oracle. Esto es obligatorio.                                                                                                                                                                                                                                                                                                                                                                       |
|     [SERVICE_TYPE]      | hostinfoparams |                                                                                                                                                                                                                                                  El tipo de servicio de Oracle. Los valores posibles son **dedicado** o **Shared**. Un servicio dedicado, utiliza un proceso de servidor dedicado para atender el proceso de un solo usuario. Un servicio compartido utiliza un proceso de servidor compartido que puede que puede atender varios procesos de usuario. El valor predeterminado es **dedicado**.                                                                                                                                                                                                                                                   |
|      [POLLING_ID]       |  QUERY_STRING  |                                                                                                                                                                                                                     Una cadena opcional que se debe anexar el adaptador al espacio de nombres estándar de la operación POLLINGSTMT. Esto le permite especificar un espacio de nombres único para cada operación de sondeo cuando un proyecto contiene varias operaciones de sondeo. No es necesario especificar una cadena de PollingId si el proyecto contiene una única operación POLLINGSTMT.                                                                                                                                                                                                                      |

> [!NOTE]
>  Parámetros de consulta también se usan en el URI de conexión cuando se especifica una dirección de punto de conexión para un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] cliente de intercambio de metadatos.  

## <a name="oracle-database-credentials-and-the-connection-uri"></a>Credenciales de base de datos de Oracle y el URI de conexión  
 De forma predeterminada, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] produce una excepción cuando se especifican las credenciales de la base de datos de Oracle en el URI de conexión. Esto es porque estas credenciales se representan como texto sin formato en el URI de conexión, y esto supone un riesgo de seguridad. Puede establecer el **AcceptCredentialsInUri** enlaza la propiedad para controlar si el URI de conexión puede contener credenciales para la base de datos de Oracle. Si el **AcceptCredentialsInUri** propiedad es **false**, [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] produce una excepción si el URI de conexión contiene credenciales de base de datos de Oracle; si la propiedad es **true** , se produce ninguna excepción. Hay algunos escenarios limitados en el que es necesario especificar credenciales en la conexión URI; Por ejemplo, para recibir la entrada POLLINGSTMT operación al usar WCF servicio modelo o el modelo de canal WCF. Sin embargo, para la mayoría de los casos, debe evitar proporcionar credenciales en el URI de conexión. Para obtener más información acerca de cómo proporcionar una forma más segura credenciales para la base de datos de Oracle, vea [proteger las aplicaciones de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md).  

> [!IMPORTANT]
>  Debido a los riesgos de seguridad que surgen pasando las credenciales en las cadenas como texto sin formato, no debe especificar las credenciales de conexión de base de datos de Oracle en el URI de conexión.  

## <a name="using-reserved-characters-in-the-connection-uri"></a>Utilizar caracteres reservados en el URI de conexión  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite la especificación de un URI que incluye caracteres especiales para cualquiera de los valores de parámetro de conexión. Si los valores de parámetro de conexión contienen caracteres especiales, asegúrese de que se realice una de las siguientes acciones:  

- Si va a especificar el URI en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] mediante [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], deberá especificarlos como-está en el **propiedades de URI** pestaña, es decir, sin usar cualquier carácter de escape. Si especifica el URI directamente en el **configurar un URI** campo y los parámetros de conexión contienen caracteres reservados, debe especificar los parámetros de conexión con los caracteres de escape adecuados.  

- Si se especifica el URI al crear un envío o recepción de puerto en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración y los parámetros de conexión contienen caracteres reservados, debe especificar los parámetros de conexión con los caracteres de escape adecuados.  

## <a name="using-the-connection-uri-to-connect-to-the-oracle-database"></a>Usar el URI de conexión para conectarse a la base de datos de Oracle  
 El siguiente es un ejemplo de un URI de conexión para [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  

|Uso de tnsnames.ora|Sin usar tnsnames.ora|  
|------------------------|--------------------------------|  
|`oracledb://ADAPTER`<br /><br /> En este ejemplo, el adaptador es un nombre de servicio de red que está asociado con la información de conexión y el nombre del servicio para la base de datos de Oracle de destino en tnsnames.ora.|`oracledb://yourOracleServer:1521/yourOracleDatabaseServiceName/Dedicated`<br /><br /> En este ejemplo, el nombre del servidor es "yourOracleServer" y el nombre del servicio es "yourOracleDatabaseServiceName".|  

 El siguiente es un ejemplo de un URI de conexión para una operación POLLINGSTMT. Este URI incluye un parámetro de PollingId para modificar el espacio de nombres de la operación POLLINGSTMT.  

|Uso de tnsnames.ora|Sin usar tnsnames.ora|  
|------------------------|--------------------------------|  
|`oracledb://ADAPTER?PollingId=MyPollingNotification1`|`oracledb://yourOracleServer:1521/yourOracleDatabaseServiceName/Dedicated? PollingId=MyPollingNotification1`|  

 Para la conexión anterior URI, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] crea el siguiente espacio de nombres para la operación POLLINGSTMT.  

```  
http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTMyPollingNotification1  
```  

 Para obtener información acerca de cómo establecer una conexión a Oracle base de datos cuando le:  

- Use la [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] o [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], consulte [conectar con base de datos de Oracle en Visual Studio mediante Consume Adapter Service](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service.md).  

- Configurar un puerto de envío o recepción (ubicación) del puerto en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución, consulte [configurar manualmente un enlace de puerto físico para el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md).  

- Utilizar el modelo de canal WCF en una solución de programación, vea [crear un canal con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md).  

- Utilizar el modelo de servicio WCF en una solución de programación, vea [configurar un cliente de enlace de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-a-client-binding-for-the-oracle-database.md).  

- Utilice WCF ServiceModel Metadata Utility Tool (svcutil.exe), consulte [uso ServiceModel Metadata Utility Tool con el adaptador de BizTalk para Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/use-the-servicemodel-metadata-utility-with-the-oracle-db-adapter-in-biztalk.md).  

## <a name="see-also"></a>Vea también  
[Crear una conexión a la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)   
 [Configurar al cliente de Oracle para el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md)