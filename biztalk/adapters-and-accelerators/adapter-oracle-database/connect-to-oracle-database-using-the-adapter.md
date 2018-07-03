---
title: Conectarse a la base de datos de Oracle mediante el adaptador | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection string
- uniform resource identifier
- Oracle database, connecting to
- URI
- connection URI
ms.assetid: 5d5598e5-aba0-4c73-8e97-9156475b93c4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a645ae3a2db79e9e2b5b4e46c758e37dfb0a1a6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004325"
---
# <a name="connect-to-oracle-database-using-the-adapter"></a>Conectarse a la base de datos de Oracle mediante el adaptador
El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] ODP.NET 11.1.0.7 se utiliza para conectarse a la base de datos de Oracle. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] requiere que los clientes del adaptador proporcionar una cadena de conexión que se denomina conexión Uniform Resource Identifier (URI), para conectarse a la base de datos de Oracle. Internamente, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] asigna el identificador URI a una cadena de conexión de base de datos para conectarse a la base de datos de Oracle. Con un URI de conexión, los clientes del adaptador pueden especificar parámetros de conexión para conectarse a un sistema externo.  
  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] permite a los clientes del adaptador para conectarse a la base de datos de Oracle en los siguientes dos maneras:  
  
- **Uso de tnsnames.ora**: el URI proporcionado por el cliente del adaptador de conexión contiene únicamente el nombre de servicio de red especificado en el archivo tnsnames.ora. El adaptador extrae los parámetros de conexión, como el nombre del servidor, el nombre del servicio y el número de puerto de la entrada de nombre de servicio de red en el archivo tnsnames.ora. Para usar este enfoque, el equipo que ejecuta al cliente de Oracle debe configurarse para incluir el nombre de servicio de red para la base de datos de Oracle en el archivo tnsnames.ora.  
  
  > [!IMPORTANT]
  >  Debido a una limitación del cliente de Oracle, el **DataSourceName** parámetro (nombre de servicio de red) en el [configurar el URI de conexión para el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-connection-uri-for-the-oracle-database-adapter.md) no puede contener más de 39 caracteres si le realiza operaciones en una transacción. Por lo tanto, asegúrese de que el valor especificado para el **DataSourceName** parámetro es menor o igual a 39 caracteres si va a realizar operaciones en una transacción.  
  
- **Sin usar tnsnames.ora**: el URI proporcionado por los clientes del adaptador de conexión contiene los parámetros de conexión, como el nombre del servidor, el nombre del servicio y el número de puerto. En este caso, el nombre de servicio de red en el archivo tnsnames.ora, o el archivo tnsnames.ora real, no debe estar presente en el equipo cliente. Esto resulta útil cuando tiene un gran número de usuarios que se conectan a la base de datos de Oracle en su organización, y agregar o actualizar los servidores no lleva a agregar o actualizar manualmente los detalles de conexión en el archivo tnsnames.ora en todos los equipos cliente.  
  
  > [!IMPORTANT]
  >  No se admite este modo de conectividad si va a realizar operaciones en una transacción. Esto es debido a una limitación del cliente de Oracle.  
  
  Para obtener más información sobre cómo conectarse a la base de datos de Oracle, vea [crear una conexión a la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md).  
  
  Asegúrese de que cumple con las directrices de seguridad al establecer una conexión con la base de datos de Oracle. Para obtener más información sobre las directrices de seguridad, consulte [proteger las aplicaciones de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md).  
  
## <a name="windows-authentication"></a>Autenticación de Windows  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] admite la autenticación de Windows al conectarse a la base de datos de Oracle. Con la autenticación de Windows, los clientes del adaptador pueden determinar la identidad del usuario en función de las credenciales de inicio de sesión de Windows y pueden aprovechar la seguridad del entorno de Windows integrada. Para obtener información sobre cómo conectarse a la base de datos de Oracle mediante la autenticación de Windows, consulte [conectar con la autenticación de Windows de base de datos de Oracle utilizando](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md).  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre el adaptador de BizTalk para la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)