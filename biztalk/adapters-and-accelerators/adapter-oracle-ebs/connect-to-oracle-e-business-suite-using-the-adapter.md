---
title: Conectarse a Oracle E-Business Suite mediante el adaptador | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80ff31d4-be4c-42d7-a321-8f01b40dd71e
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7ef5a7dc47b135cbeeec348c2af2d5054163d33
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980701"
---
# <a name="connect-to-oracle-e-business-suite-using-the-adapter"></a>Conectarse a Oracle E-Business Suite mediante el adaptador
El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] ODP.NET 11.1.0.7 se utiliza para conectarse a Oracle E-Business Suite. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] requiere que los clientes del adaptador proporcionar una cadena de conexión que se denomina conexión Uniform Resource Identifier (URI), para conectarse a Oracle E-Business Suite. Internamente, el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] se conecta a la base de datos de Oracle subyacente a través del URI. Con un URI de conexión, los clientes del adaptador pueden especificar parámetros de conexión para conectarse a un sistema externo.  

## <a name="connectivity-to-oracle-ebs"></a>Conectividad con Oracle EBS  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] permite a los clientes del adaptador para conectarse a Oracle E-Business Suite en las siguientes dos maneras:  
  
- **Uso de tnsnames.ora**: el URI proporcionado por el cliente del adaptador de conexión contiene únicamente el nombre de servicio de red especificado en el archivo tnsnames.ora. El adaptador extrae los parámetros de conexión, como el nombre del servidor, el nombre del servicio y el número de puerto de la entrada de nombre de servicio de red en el archivo tnsnames.ora. Para usar este enfoque, el equipo que ejecuta al cliente de Oracle debe configurarse para incluir el nombre de servicio de red para la base de datos de Oracle en el archivo tnsnames.ora.  
  
  > [!IMPORTANT]
  >  Debido a una limitación del cliente de Oracle, el **DataSourceName** parámetro (nombre de servicio de red) en el [crear el URI de conexión de SQL Server](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md) no puede contener más de 39 caracteres si va a realizar las operaciones en una transacción. Por lo tanto, asegúrese de que el valor especificado para el **DataSourceName** parámetro es menor o igual a 39 caracteres si va a realizar operaciones en una transacción.  
  
- **Sin usar tnsnames.ora**: el URI proporcionado por los clientes del adaptador de conexión contiene los parámetros de conexión, como el nombre del servidor, el nombre del servicio y el número de puerto. En este caso, el nombre de servicio de red en el archivo tnsnames.ora, o el archivo tnsnames.ora real, no debe estar presente en el equipo cliente. Esto resulta útil cuando tiene un gran número de usuarios que se conectan a la base de datos de Oracle en su organización, y agregar o actualizar los servidores no lleva a agregar o actualizar manualmente los detalles de conexión en el archivo tnsnames.ora en todos los equipos cliente.  
  
  > [!IMPORTANT]
  >  No se admite este modo de conectividad si va a realizar operaciones en una transacción. Esto es debido a una limitación del cliente de Oracle.  
  
  Para obtener más información sobre cómo conectarse a Oracle E-Business Suite, consulte [crear una conexión a Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md).  
  
  Asegúrese de que cumple con las directrices de seguridad al establecer una conexión con Oracle E-Business Suite. Consulte [proteger su aplicación de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/secure-your-oracle-ebs-applications.md).
  
## <a name="enter-client-credentials"></a>Escriba las credenciales del cliente  
 En [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], puede proporcionar credenciales para conectarse a Oracle E-Business Suite en los dos lugares siguientes:  
  
- En el **seguridad** pestaña en el **configurar el adaptador** cuadro de diálogo. Puede encontrar este cuadro de diálogo en el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
- En el **OracleUserName** y **OraclePassword** propiedades de enlace el **propiedades de enlace** pestaña en el **configurar el adaptador** cuadro de diálogo. Puede encontrar este cuadro de diálogo en el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. En este caso, las credenciales se almacenan en texto sin formato en el archivo de enlace.  
  
  El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] expone el **ClientCredentialType** enlaza la propiedad que le permite especificar el conjunto de credenciales (Oracle E-Business Suite u Oracle database) que se usará para conectarse a Oracle E-Business Suite.  
  
- Para conectar con las credenciales de la base de datos de Oracle, especifique el **ClientCredentialType** enlaza la propiedad como **base de datos**y, a continuación, en el **seguridad** ficha, especifique el las credenciales en la base de datos la **nombre de usuario** y **contraseña** cuadros de texto.  Si va a realizar operaciones en cualquiera de los artefactos de Oracle E-Business Suite (tabla de interfaz, vista de interfaz, programa simultáneo, el conjunto de solicitud o API de PL/SQL de Oracle E-Business Suite), también debe proporcionar las credenciales de Oracle E-Business Suite en el **OracleUserName** y **OraclePassword** propiedades de enlace.  
  
- Para conectarse con credenciales de Oracle E-Business Suite, especifique el **ClientCredentialType** enlaza la propiedad como **EBusiness**y, a continuación, especifique las credenciales de Oracle E-Business Suite en el  **Nombre de usuario** y **contraseña** cuadros de texto en el **seguridad** ficha. También debe especificar las credenciales de la base de datos de Oracle para el **OracleUserName** y **OraclePassword** propiedades de enlace.  
  
  Para obtener más información acerca de cómo especificar las credenciales del cliente, consulte [configurar las credenciales de inicio de sesión para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-sign-in-credentials-for-the-oracle-e-business-suite.md).  
  
## <a name="using-windows-authentication"></a>Con la autenticación de Windows  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] admite la autenticación de Windows al conectarse a Oracle E-Business Suite. Con la autenticación de Windows, los clientes del adaptador pueden determinar la identidad del usuario en función de las credenciales de inicio de sesión de Windows y pueden aprovechar la seguridad del entorno de Windows integrada. Para obtener información sobre cómo conectarse a Oracle E-Business Suite mediante la autenticación de Windows, consulte [conectarse a Oracle E-Business Suite Using Windows Authentication](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md).  
  
## <a name="see-also"></a>Vea también  
[Comprender el adaptador de BizTalk para Oracle E-Business palo](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)