---
title: Configurar un cliente de enlace de Oracle E-Business Suite | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1347cbca-5567-43f8-a75e-a23b108692bc
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a1f3eafdf423926dab4cf48efae8db3044aba9b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962594"
---
# <a name="configure-a-client-binding-for-the-oracle-e-business-suite"></a>Configurar a un cliente de enlace de Oracle E-Business Suite
Una vez que haya generado la clase de cliente WCF, puede crear un cliente WCF (instancia) e invocar sus métodos para consumir el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  
  
 Para crear al cliente de WCF, debe especificar una dirección de extremo y un enlace. La dirección de punto de conexión debe contener un URI de conexión de Oracle E-Business Suite válido y el enlace debe ser una instancia de un enlace de Oracle E-Business Suite (**OracleEBSBinding**). Para obtener más información sobre el URI de conexión de Oracle E-Business Suite, consulte [crear una conexión a Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md). Se recomienda que no especifique las credenciales de usuario como parte del URI de conexión. Puede utilizar el **ClientCredentials** propiedad del cliente WCF, como se explica en este tema.  
  
 Puede especificar el enlace de Oracle E-Business Suite y la dirección del extremo en el código o en un archivo de configuración. Cuando se usa el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar la clase de cliente WCF, también se crea un archivo de configuración (app.config) para el proyecto. Este archivo contiene los valores de configuración que reflejan la conexión y propiedades de información de enlace (excepto las credenciales) que especificó cuando se conecta a Oracle E-Business Suite con la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
## <a name="specifying-the-binding-and-endpoint-address-in-code"></a>Especificar el enlace y la dirección del extremo en el código  
 El código siguiente muestra cómo crear un cliente de WCF mediante la especificación de la dirección de enlace y el punto de conexión en el código mediante el **ClientCredentials** propiedad del cliente WCF.  
  
```  
//Create an Oracle EBS binding and set the binding properties  
OracleEBSBinding binding = new OracleEBSBinding();  
binding.OracleUserName = "myOracleEBSUser";  
binding.OraclePassword = "myOracleEBSPassword";  
binding.OracleEBSResponsibilityName = "Responsibility";  
binding.OracleEBSOrganizationId = "204";  
  
//Create the client endpoint   
EndpointAddress address = new EndpointAddress("oracleebs://<oracleebs_instance_name>/");  
  
//Create the client and specify the credentials  
ConcurrentPrograms_ARClient client = new ConcurrentPrograms_ARClient(binding,address);  
client.ClientCredentials.UserName.UserName = "myuser";  
client.ClientCredentials.UserName.Password = "mypassword";  
  
//Open the client  
client.Open();  
```  
  
## <a name="specifying-the-binding-and-endpoint-address-in-a-configuration-file"></a>Especificar el enlace y dirección de punto de conexión en un archivo de configuración  
 El código siguiente muestra cómo crear a un cliente de WCF especificando el enlace y dirección de punto de conexión en un archivo app.config.  
  
```  
//Create the client by specifying the endpoint name in the app.config. In this case, the binding properties  
//must also be specified in the app.config.  
ConcurrentPrograms_ARClient client = new ConcurrentPrograms_ARClient("OracleEBSBinding_ConcurrentPrograms_AR");  
  
//Specify the credentials   
client.ClientCredentials.UserName.UserName = "myuser";  
client.ClientCredentials.UserName.Password = "mypassword";  
  
client.Open();  
```  
  
 El siguiente XML muestra el archivo de configuración creado para el **interfaz cliente** programa simultáneo por la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Este archivo contiene la configuración de punto de conexión del cliente al que hace referencia en el ejemplo anterior.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    <system.serviceModel>  
        <bindings>  
            <oracleEBSBinding>  
                <binding openTimeout="00:05:00" name="OracleEBSBinding" closeTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00" clientCredentialType="Database"  
                    inboundOperationType="Polling" metadataPooling="true" statementCachePurge="false"  
                    statementCacheSize="10" pollWhileDataFound="false" pollingInterval="30"  
                    useOracleConnectionPool="true" minPoolSize="1" maxPoolSize="100"  
                    incrPoolSize="5" decrPoolSize="1" connectionLifetime="0" acceptCredentialsInUri="false"  
                    useAmbientTransaction="true" notifyOnListenerStart="true"  
                    notificationPort="-1" dataFetchSize="65536" longDatatypeColumnSize="32512"  
                    skipNilNodes="true" maxOutputAssociativeArrayElements="32"  
                    enableSafeTyping="false" insertBatchSize="20" useSchemaInNameSpace="true"  
                    enableBizTalkCompatibilityMode="true">  
                    <mlsSettings language="" dateFormat="" dateLanguage="" numericCharacters=""  
                        sort="" territory="" comparison="" currency="" dualCurrency=""  
                        iSOCurrency="" calendar="" lengthSemantics="" nCharConversionException="true"  
                        timeStampFormat="" timeStampTZFormat="" timeZone="" />  
                </binding>  
            </oracleEBSBinding>  
        </bindings>  
        <client>  
            <endpoint address="oracleebs://ebs-70-12/" binding="oracleEBSBinding"  
                bindingConfiguration="OracleEBSBinding" contract="ConcurrentPrograms_AR"  
                name="OracleEBSBinding_ConcurrentPrograms_AR" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
 Si un proyecto tiene más de un cliente WCF, habrá varios clientes entradas de punto de conexión definidas en el archivo de configuración. Cada entrada de cliente WCF tendrá un nombre único basado en su configuración de enlace y el artefacto de Oracle E-Business Suite de destino. Si se conectan a varias veces para crear los clientes de WCF en el proyecto, varias entradas de configuración de enlace se creará, uno para cada conexión. Estas entradas de configuración de enlace se denominará de la siguiente manera: OracleEBSBinding, OracleEBSBinding1, y así sucesivamente. Cada entrada de punto de conexión de cliente creado durante una conexión de acceso hará referencia a la entrada de enlace creada durante esa conexión.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)