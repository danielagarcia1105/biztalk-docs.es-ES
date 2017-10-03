---
title: Conectarse a Oracle E-Business Suite mediante el adaptador | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 80ff31d4-be4c-42d7-a321-8f01b40dd71e
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c8551c0f09d65d50b87248a6b0dc4030a612fc7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-oracle-e-business-suite-using-the-adapter"></a>Conectarse a Oracle E-Business Suite mediante el adaptador
El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] ODP.NET 11.1.0.7 se utiliza para conectarse a Oracle E-Business Suite. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] requiere que los clientes de adaptador proporcionar una cadena de conexión, llamada a la conexión Uniform Resource Identifier (URI), para conectarse a Oracle E-Business Suite. Internamente, el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] se conecta a la base de datos de Oracle subyacente a través de la dirección URI. Con un URI de conexión, los clientes de adaptador pueden especificar parámetros de conexión para conectarse a un sistema externo.  

## <a name="connectivity-to-oracle-ebs"></a>Conectividad con Oracle EBS  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] permite a los clientes de adaptador para conectarse a Oracle E-Business Suite en las siguientes dos maneras:  
  
-   **Usar tnsnames.ora**: el URI proporcionado por el cliente del adaptador de conexión contiene solo el nombre de servicio de red especificado en el archivo tnsnames.ora. El adaptador extrae los parámetros de conexión como nombre del servidor, nombre de servicio y el número de puerto de la entrada de nombre de servicio de red en el archivo tnsnames.ora. Para utilizar este enfoque, el equipo que ejecuta al cliente de Oracle debe configurarse para incluir el nombre de servicio de red para la base de datos de Oracle en el archivo tnsnames.ora.  
  
    > [!IMPORTANT]
    >  Debido a una limitación del cliente de Oracle, el **DataSourceName** parámetro (nombre de servicio de red) en el [crear el URI de conexión de SQL Server](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md) no puede contener más de 39 caracteres si va a realizar las operaciones en una transacción. Por lo tanto, asegúrese de que el valor especificado para la **DataSourceName** parámetro es menor o igual a 39 caracteres si va a realizar las operaciones en una transacción.  
  
-   **Sin usar tnsnames.ora**: el URI proporcionado por los clientes de adaptador de conexión contiene los parámetros de conexión como nombre del servidor, nombre de servicio y el número de puerto. En este caso, el nombre de servicio de red en el archivo tnsnames.ora, o en el archivo tnsnames.ora real, no necesita estar presente en el equipo cliente. Esto resulta útil si tiene un gran número de usuarios que se conectan a la base de datos de Oracle en su organización, y agregar o actualizar los servidores no lleva a agregar o actualizar manualmente los detalles de conexión en el archivo tnsnames.ora en cada equipo cliente.  
  
    > [!IMPORTANT]
    >  No se admite este modo de conectividad si va a realizar las operaciones en una transacción. Esto es debido a una limitación del cliente de Oracle.  
  
 Para obtener más información sobre cómo conectarse a Oracle E-Business Suite, consulte [crear una conexión a Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md).  
  
 Asegúrese de que cumple con las normas de seguridad al establecer una conexión con Oracle E-Business Suite. Vea [proteger la aplicación de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/secure-your-oracle-ebs-applications.md).
  
## <a name="enter-client-credentials"></a>Escriba las credenciales del cliente  
 En [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], puede proporcionar credenciales para conectarse a Oracle E-Business Suite en las dos ubicaciones siguientes:  
  
-   En el **seguridad** pestaña en el **configurar el adaptador** cuadro de diálogo. Puede encontrar este cuadro de diálogo en el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
-   En el **OracleUserName** y **OraclePassword** propiedades de enlace el **propiedades de enlace** pestaña en el **configurar el adaptador** cuadro de diálogo. Puede encontrar este cuadro de diálogo en el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. En este caso, las credenciales se almacenan en texto sin formato en el archivo de enlace.  
  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] expone la **ClientCredentialType** enlaza la propiedad que le permite especificar el conjunto de credenciales (Oracle E-Business Suite o base de datos de Oracle) que se usará para conectarse a Oracle E-Business Suite.  
  
-   Para conectarse utilizando las credenciales de la base de datos de Oracle, especifique la **ClientCredentialType** enlaza la propiedad como **base de datos**y, a continuación, en la **seguridad** ficha, especifique el las credenciales en la base de datos la **nombre de usuario** y **contraseña** cuadros de texto.  Si va a realizar operaciones en cualquiera de los artefactos de Oracle E-Business Suite (tabla de interfaz, vista de la interfaz, programa simultáneo, conjunto de solicitud o API de PL/SQL de Oracle E-Business Suite), también debe proporcionar las credenciales de Oracle E-Business Suite en el **OracleUserName** y **OraclePassword** propiedades de enlace.  
  
-   Para conectarse con credenciales de Oracle E-Business Suite, especifique la **ClientCredentialType** enlaza la propiedad como **EBusiness**y, a continuación, especifique las credenciales de Oracle E-Business Suite en el  **Nombre de usuario** y **contraseña** cuadros de texto en el **seguridad** ficha. También debe especificar las credenciales de la base de datos de Oracle para el **OracleUserName** y **OraclePassword** propiedades de enlace.  
  
 Para obtener más información acerca de cómo especificar las credenciales del cliente, consulte [configurar las credenciales de inicio de sesión para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-sign-in-credentials-for-the-oracle-e-business-suite.md).  
  
## <a name="using-windows-authentication"></a>Con la autenticación de Windows  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] es compatible con la autenticación de Windows al conectarse a Oracle E-Business Suite. Con la autenticación de Windows, los clientes de adaptador pueden determinar la identidad de un usuario en función de las credenciales de inicio de sesión de Windows y pueden aprovechar la seguridad integrada del entorno de Windows. Para obtener información sobre cómo conectarse a Oracle E-Business Suite mediante la autenticación de Windows, vea [conectarse a Oracle E-Business Suite Using Windows Authentication](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md).  
  
## <a name="see-also"></a>Vea también  
[Comprender el adaptador de BizTalk para Oracle E-Business palo](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)