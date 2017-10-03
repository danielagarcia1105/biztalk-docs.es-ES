---
title: Configurar un cliente de enlace de la base de datos de Oracle | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- client binding, specifying in code
- WCF client, creating
- client binding, specifying in configuration file
ms.assetid: f18c7296-c28a-4dec-9514-5299c8c2dffe
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7de5eeb9a7b0022ce4da5f56591e863f48bd0b61
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-a-client-binding-for-the-oracle-database"></a>Configurar a un cliente de enlace de la base de datos de Oracle
Una vez que haya generado la clase de cliente WCF, puede crear un cliente WCF (instancia) e invocar sus métodos para consumir el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Para obtener información sobre cómo generar el código de clase y la aplicación auxiliar de cliente WCF para las operaciones que el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] expone, consulte [generar un cliente de WCF o un contrato de servicio de WCF para artefactos de solución de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md).  
  
 Para crear al cliente de WCF, debe especificar una dirección de extremo y un enlace. La dirección de punto de conexión debe contener un URI de conexión de Oracle válido y el enlace debe ser una instancia de un enlace de la base de datos de Oracle (**OracleDBBinding**). Para obtener más información sobre el URI de conexión de Oracle, vea [crear el URI de conexión de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md). Se recomienda que no especifique las credenciales de usuario como parte del URI de conexión. Puede utilizar el **ClientCredentials** propiedad del cliente WCF, como se explica en este tema.  
  
 Puede especificar el enlace de la base de datos de Oracle y la dirección del extremo en el código o en un archivo de configuración. Cuando se usa el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar la clase de cliente WCF, también se crea un archivo de configuración (app.config) para el proyecto. Este archivo contiene los valores de configuración que reflejan la conexión y propiedades de información de enlace (excepto las credenciales) que especificó cuando se conecta a la base de datos de Oracle con el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
## <a name="specifying-the-binding-and-endpoint-address-in-code"></a>Especificar el enlace y la dirección del extremo en el código  
 El código siguiente muestra cómo crear a un cliente de WCF especificando el enlace y la dirección del extremo en el código. Es recomendable para especificar las credenciales de Oracle mediante la **ClientCredentials** propiedad del cliente WCF, en lugar de en el URI proporcionado para la dirección del punto de conexión.  
  
```  
// A WCF client that targets the /SCOTT/EMP table is created  
// by using a binding object and endpoint address  
OracleDBBinding odbBinding = new OracleDBBinding();  
EndpointAddress odbAddress = new EndpointAddress("OracleDb://ADAPTER");  
  
SCOTTTableEMPClient empClient = new SCOTTTableEMPClient(odbBinding, odbAddress);  
  
empClient.ClientCredentials.UserName.UserName = "SCOTT";  
empClient.ClientCredentials.UserName.Password = "TIGER";  
  
empClient.Open();  
```  
  
## <a name="specifying-the-binding-and-endpoint-address-in-a-configuration-file"></a>Especificar el enlace y dirección de punto de conexión en un archivo de configuración  
 El código siguiente muestra cómo crear a un cliente de WCF especificando el enlace y dirección de punto de conexión en un archivo app.config.  
  
```  
// A WCF client that targets the /SCOTT/EMP table is created  
// by specifying the client endpoint information in app.config  
SCOTTTableEMPClient empClient = new SCOTTTableEMPClient("OracleDBBinding_SCOTT.Table.EMP");  
  
empClient.ClientCredentials.UserName.UserName = "SCOTT";  
empClient.ClientCredentials.UserName.Password = "TIGER";  
  
empClient.Open();  
```  
  
 El siguiente XML muestra el archivo de configuración creado para la tabla EMP por la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Este archivo contiene la configuración de punto de conexión del cliente al que hace referencia en el ejemplo anterior.  
  
```  
\<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    \<system.serviceModel>  
        <bindings>  
            <oracleDBBinding>  
                <binding name="OracleDBBinding" closeTimeout="00:01:00" openTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00"  
                    dataFetchSize="65536" metadataPooling="true" statementCachePurge="false"  
                    statementCacheSize="10" longDatatypeColumnSize="32767" pollingStatement=""  
                    postPollStatement="" pollingInterval="500" useOracleConnectionPool="false"  
                    minPoolSize="1" maxPoolSize="100" incrPoolSize="5" decrPoolSize="1"  
                    connectionLifetime="0" transactionIsolationLevel="ReadCommitted"  
                    enablePerformanceCounters="false" acceptCredentialsInUri="false"  
                    enableBizTalkCompatibilityMode="false" />  
            </oracleDBBinding>  
        </bindings>  
        <client>  
            <endpoint address="oracledb://adapter/" binding="oracleDBBinding"  
                bindingConfiguration="OracleDBBinding" contract="SCOTTTableEMP"  
                name="OracleDBBinding_SCOTT.Table.EMP" />  
        </client>  
    \</system.serviceModel>  
</configuration>  
```  
  
 Si un proyecto tiene más de un cliente WCF, habrá varios clientes entradas de punto de conexión definidas en el archivo de configuración. Cada entrada de cliente WCF tendrá un nombre único basado en su configuración de enlace y el artefacto de base de datos de Oracle de destino; Por ejemplo, "OracleDBBinding_SCOTT. Table.EMP". Si se conectan a varias veces para crear los clientes de WCF en el proyecto, varias entradas de configuración de enlace se creará, uno para cada conexión. Estas entradas de configuración de enlace se denominará de la siguiente manera: OracleDBBinding1, OracleDBBinding2, y así sucesivamente. Cada entrada de punto de conexión de cliente creado durante una conexión de acceso hará referencia a la entrada de enlace creada durante esa conexión.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)   
 [Generar un cliente WCF o un contrato de servicio WCF para los artefactos de solución de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)   
 [Crear el URI de conexión de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)   
 [Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)