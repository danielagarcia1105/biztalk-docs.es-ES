---
title: Crear el URI de conexión de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 688e2215-a4d8-4f55-a37c-7d91c3de080f
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c58812b9fc3404b9922cf05c84717f3c95e05435
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007581"
---
# <a name="create-the-sql-server-connection-uri"></a>Crear el URI de conexión de SQL Server
El [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] URI de conexión contiene propiedades que el adaptador utiliza para establecer una conexión a la base de datos de SQL Server. En este tema se proporciona información sobre el URI de conexión de SQL Server y proporciona vínculos a otros temas que explican cómo especificar un URI en diferentes situaciones de programación.  
  
##  <a name="FailoverPartner"></a> El URI de conexión del adaptador de SQL  
 Una dirección de punto de conexión típica URI en WCF se representa como: `scheme://hostinfoparams?query_string`, donde:  
  
- esquema es el nombre de esquema.  
  
- hostinfoparams es la información necesaria para establecer la conexión al host; Por ejemplo, un nombre de servidor.  
  
- QUERY_STRING es una colección de nombre y valor opcional de parámetros que se delimitan mediante un signo de interrogación (?).  
  
  El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] conexión URI se adhiere a este formato básico y se implementa como sigue:  
  
```  
  
mssql://[Server_Name[:Portno]]/[Database_Instance_Name]/[Database_Name]?FailoverPartner=[Partner_Server_Name]&InboundId=[Inbound_ID]  
```  
  
 donde, `mssql` es el esquema para el URI de conexión de SQL Server.  
  
 En la tabla siguiente se explica las propiedades contenidas en el URI de conexión.  
  
|Propiedad URI de conexión|Categoría|Descripción|  
|-----------------------------|--------------|-----------------|  
|[NOMBREDESERVIDOR]|hostinfoparams|Nombre del servidor donde está instalado SQL Server. Si no especifica un valor, el adaptador asume el nombre del servidor como "localhost" y establece una conexión con la base de datos de SQL Server en el servidor local.|  
|[PORTNO]|hostinfoparams|El número de puerto donde se establece la conexión. Si no especifica un valor, el adaptador se conecta a través del puerto predeterminado.|  
|[NOMBRE_INSTANCIA_BASEDEDATOS]|hostinfoparams|Nombre de la instancia de SQL Server para conectarse a. Si no especifica un valor, el adaptador se conecta a la instancia de base de datos predeterminada.|  
|[DATABASE_NAME]|hostinfoparams|Nombre de la base de datos al que conectarse. Si no especifica un valor, el adaptador se conecta a la base de datos de forma predeterminada.|  
|[PARTNER_SERVER_NAME]|QUERY_STRING|Nombre de la base de datos de SQL Server de conmutación por error para conectarse como si la base de datos principal de SQL Server no está disponible. Para obtener más información sobre la alta disponibilidad con respecto a SQL Server, vea [creación de reflejo de base de datos en SQL Server](https://msdn.microsoft.com/library/5h52hef8.aspx).|  
|[INBOUND_ID]|QUERY_STRING|Un identificador que se agrega a la conexión URI para que sea único. Debe proporcionar este parámetro de conexión si desea generar los metadatos para el **TypedPolling** operación entrante. Además, en una aplicación de BizTalk, si tiene varias ubicaciones de sondeo de la misma base de datos de recepción el Id. de entrada realiza la conexión URI único, lo que permite a los clientes del adaptador recibir mensajes de sondeo de la misma base de datos en diferentes ubicaciones de recepción. Para obtener más información, consulte [de recepción de sondeo mensajes a través de varios puertos de recepción de SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md).|  
  
> [!NOTE]
>  Para obtener más información acerca de estas propiedades de cadena de conexión, consulte [propiedad SqlConnection.ConnectionString](https://msdn.microsoft.com/library/system.data.sqlclient.sqlconnection.connectionstring.aspx).
  
## <a name="sql-server-credentials-and-the-connection-uri"></a>Credenciales de SQL Server y el URI de conexión  
 El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] no admite especificar credenciales en el URI de conexión. Para obtener más información acerca de cómo especificar credenciales en las aplicaciones que usan el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], consulte [proteger las aplicaciones SQL](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md).  
  
## <a name="using-special-characters-in-the-connection-uri"></a>Uso de caracteres especiales en el URI de conexión  
 El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] no admite la especificación de un URI que incluye caracteres especiales para cualquiera de los valores de parámetro de conexión. Si los valores de parámetro de conexión contienen caracteres especiales, asegúrese de que se realice una de las siguientes acciones:  
  
- Si va a especificar el URI en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] mediante [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], deberá especificarlos como-está en el **propiedades de URI** pestaña, es decir, sin usar cualquier carácter de escape. Si especifica el URI directamente en el **configurar un URI** campo y los parámetros de conexión contienen caracteres especiales, debe especificar los parámetros de conexión con los caracteres de escape adecuados.  
  
   Por ejemplo, si el URI de conexión tiene un parámetro con nombre `sql server`, debe especificarlo como `sql%20server`.  
  
- Si se especifica el URI al crear un envío o recepción de puerto en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración y los parámetros de conexión contienen caracteres especiales, debe especificar los parámetros de conexión con los caracteres de escape adecuados.  
  
## <a name="using-the-connection-uri-to-connect-to-the-sql-server-database"></a>Usar el URI de conexión para conectarse a la base de datos SQL Server  
 El siguiente es un URI de conexión de ejemplo para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
```  
mssql://sql_server/sql_server_instance//  
```  
  
 En el ejemplo anterior, "sql_server" es el nombre del equipo donde está instalado SQL Server, mientras que "instancia_sql_server" es el nombre de la instancia de base de datos al que conectarse. Porque se especificó ningún nombre de base de datos, el adaptador se conectará a la base de datos de forma predeterminada.  
  
 El siguiente es un ejemplo de una conexión de URI donde la base de datos de SQL Server está instalado en el mismo equipo que el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. En este ejemplo, el adaptador se conecta a la base de datos "my_database" para la instancia de base de datos "instancia_sql_server" en el equipo local.  
  
```  
mssql://localhost/sql_server_instance/my_database/  
```  
  
 En este ejemplo, el adaptador se conecta a la base de datos predeterminada para la instancia predeterminada que se ejecutan en el equipo local.  
  
```  
mssql://localhost///  
```  
  
 Para obtener información sobre cómo especificar una conexión a SQL Server de base de datos cuando le:  
  
- Use la [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] o [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], consulte [conectar con SQL Server en Visual Studio mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-sql-adapter.md).  
  
- Configurar un puerto de envío o recepción puerto (ubicación) en una solución de BizTalk Server, vea [configurar manualmente un enlace de puerto físico al adaptador de SQL](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md).
  
- Utilizar el modelo de canal WCF en una solución de programación, vea [crean un canal mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/create-a-channel-using-the-sql-adapter.md).  
  
- Utilizar el modelo de servicio WCF en una solución de programación, vea [configurar un enlace de cliente para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).  
  
## <a name="see-also"></a>Vea también  
[Desarrollar las aplicaciones SQL](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)