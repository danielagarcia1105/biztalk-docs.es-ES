---
title: Conectarse a la base de datos de Oracle mediante el adaptador | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- connection string
- uniform resource identifier
- Oracle database, connecting to
- URI
- connection URI
ms.assetid: 5d5598e5-aba0-4c73-8e97-9156475b93c4
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01b04a615d0b0b8cd83b9ed7516cd096b2c85a54
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-oracle-database-using-the-adapter"></a>Conectarse a la base de datos de Oracle mediante el adaptador
El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] ODP.NET 11.1.0.7 se utiliza para conectarse a la base de datos de Oracle. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] requiere que los clientes de adaptador proporcionar una cadena de conexión, llamada a la conexión Uniform Resource Identifier (URI), para conectarse a la base de datos de Oracle. Internamente, la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] asigna el URI en una cadena de conexión de base de datos para conectarse a la base de datos de Oracle. Con un URI de conexión, los clientes de adaptador pueden especificar parámetros de conexión para conectarse a un sistema externo.  
  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] permite a los clientes de adaptador para conectarse a la base de datos de Oracle en los siguientes dos maneras:  
  
-   **Usar tnsnames.ora**: el URI proporcionado por el cliente del adaptador de conexión contiene solo el nombre de servicio de red especificado en el archivo tnsnames.ora. El adaptador extrae los parámetros de conexión como nombre del servidor, nombre de servicio y el número de puerto de la entrada de nombre de servicio de red en el archivo tnsnames.ora. Para utilizar este enfoque, el equipo que ejecuta al cliente de Oracle debe configurarse para incluir el nombre de servicio de red para la base de datos de Oracle en el archivo tnsnames.ora.  
  
    > [!IMPORTANT]
    >  Debido a una limitación del cliente de Oracle, el **DataSourceName** parámetro (nombre de servicio de red) en el [configurar el URI de conexión para el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-connection-uri-for-the-oracle-database-adapter.md) no puede contener más de 39 caracteres si se está realizando operaciones en una transacción. Por lo tanto, asegúrese de que el valor especificado para la **DataSourceName** parámetro es menor o igual a 39 caracteres si va a realizar las operaciones en una transacción.  
  
-   **Sin usar tnsnames.ora**: el URI proporcionado por los clientes de adaptador de conexión contiene los parámetros de conexión como nombre del servidor, nombre de servicio y el número de puerto. En este caso, el nombre de servicio de red en el archivo tnsnames.ora, o en el archivo tnsnames.ora real, no necesita estar presente en el equipo cliente. Esto resulta útil si tiene un gran número de usuarios que se conectan a la base de datos de Oracle en su organización, y agregar o actualizar los servidores no lleva a agregar o actualizar manualmente los detalles de conexión en el archivo tnsnames.ora en cada equipo cliente.  
  
    > [!IMPORTANT]
    >  No se admite este modo de conectividad si va a realizar las operaciones en una transacción. Esto es debido a una limitación del cliente de Oracle.  
  
 Para obtener más información sobre cómo conectarse a la base de datos de Oracle, vea [crear una conexión a la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md).  
  
 Asegúrese de que cumple con las normas de seguridad al establecer una conexión con la base de datos de Oracle. Para obtener más información acerca de las instrucciones de seguridad, consulte [proteger sus aplicaciones de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md).  
  
## <a name="windows-authentication"></a>Autenticación de Windows  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] es compatible con la autenticación de Windows al conectarse a la base de datos de Oracle. Con la autenticación de Windows, los clientes de adaptador pueden determinar la identidad de un usuario en función de las credenciales de inicio de sesión de Windows y pueden aprovechar la seguridad integrada del entorno de Windows. Para obtener información sobre cómo conectarse a la base de datos de Oracle mediante la autenticación de Windows, vea [conectar con la autenticación de Windows de base de datos de Oracle utilizando](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md).  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre el adaptador de BizTalk para base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)