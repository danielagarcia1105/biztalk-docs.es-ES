---
title: Configurar un cliente WCF para un sistema Siebel | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- how to, create a WCF client by specifying binding and endpoint address in a configuration file
- how to, create a WCF client by specifying binding and endpoint address in code
- WCF service model, configuring a WCF client for a Siebel system
ms.assetid: 6b4c5b06-d5ff-4dbf-8dc2-89c547a59864
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04d122c3300f3c1e52194a10332fbb7fb6c45d81
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963610"
---
# <a name="configure-a-wcf-client-for-a-siebel-system"></a>Configurar a un cliente WCF para un sistema Siebel
Una vez que haya generado la clase de cliente WCF, puede crear un cliente WCF (instancia) e invocar sus métodos para consumir el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]. Para obtener información sobre cómo generar el código de clase y la aplicación auxiliar de cliente WCF para las operaciones que el [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] expone, consulte [generar un cliente de WCF o un contrato de servicio WCF para la solución de Siebel artefactos](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md).  
  
 Para crear al cliente de WCF, debe especificar una dirección de extremo y un enlace. La dirección de punto de conexión debe contener una conexión válida de Siebel URI y el enlace debe ser una instancia de un enlace de Siebel (**SiebelBinding**). Para obtener más información sobre el URI de conexión de Siebel, consulte [conectar con el sistema Siebel en Visual Studio](../../adapters-and-accelerators/adapter-siebel/connect-to-the-siebel-system-in-visual-studio.md).  
  
 Puede especificar el enlace de Siebel y la dirección del extremo en el código o en un archivo de configuración. Cuando se usa el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar la clase de cliente WCF, también se crea un archivo de configuración (app.config) para el proyecto. Este archivo contiene los valores de configuración que reflejan la conexión y propiedades de información de enlace (excepto las credenciales) que especificó cuando se conecta al sistema Siebel con la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
## <a name="specifying-the-binding-and-endpoint-address-in-code"></a>Especificar el enlace y la dirección del extremo en el código  
 El código siguiente muestra cómo crear a un cliente de WCF especificando el enlace y la dirección del extremo en el código. Es recomendable para especificar las credenciales de Siebel mediante la **ClientCredentials** propiedad del cliente WCF, en lugar de en el URI proporcionado para la dirección del punto de conexión.  
  
```  
// A WCF client that targets the TimeStamp business service is created  
// by using a binding object and endpoint address  
SiebelBinding sblBinding = new SiebelBinding();  
EndpointAddress sblAddress = new EndpointAddress("siebel://Siebel_server:1234?SiebelObjectManager=obj_mgr&SiebelEnterpriseServer=ent_server&Language=enu");  
  
BusinessServices_TimeStamp_OperationClient client =   
    new BusinessServices_TimeStamp_OperationClient(sblBinding, sblAddress);  
  
    client.ClientCredentials.UserName.UserName = "SADMIN";  
    client.ClientCredentials.UserName.Password = "SADMIN";  
  
    client.Open();  
```  
  
## <a name="specifying-the-binding-and-endpoint-address-in-a-configuration-file"></a>Especificar el enlace y dirección de punto de conexión en un archivo de configuración  
 El código siguiente muestra cómo crear a un cliente de WCF especificando el enlace y dirección de punto de conexión en un archivo app.config.  
  
```  
// A WCF client that targets the TimeStamp business service is created  
// by specifying the client endpoint information in app.config  
BusinessServices_TimeStamp_OperationClient client =   
    new BusinessServices_TimeStamp_OperationClient("SiebelBinding_BusinessServices_TimeStamp_Operation");  
  
client.ClientCredentials.UserName.UserName = "SADMIN";  
client.ClientCredentials.UserName.Password = "SADMIN";  
  
client.Open();  
```  
  
### <a name="the-appconfig-file"></a>El archivo App.config  
 El siguiente XML muestra el archivo de configuración creado para el servicio de negocio de marca de tiempo por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Este archivo contiene la configuración de punto de conexión del cliente al que hace referencia en el ejemplo anterior.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    <system.serviceModel>  
        <bindings>  
            <siebelBinding>  
                <binding name="SiebelBinding" closeTimeout="00:01:00" openTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00" enableBizTalkCompatibilityMode="false"  
                    enablePerformanceCounters="false" enableConnectionPooling="true"  
                    maxConnectionsPerSystem="5" idleConnectionTimeout="00:01:00"  
                    acceptCredentialsInUri="false" />  
            </siebelBinding>  
        </bindings>  
        <client>  
            <endpoint address="siebel://Siebel_server:1234?SiebelObjectManager=obj_mgr&SiebelEnterpriseServer=ent_server&Language=enu"  
                binding="siebelBinding" bindingConfiguration="SiebelBinding"  
                contract="BusinessServices_TimeStamp_Operation" name="SiebelBinding_BusinessServices_TimeStamp_Operation" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
 Si un proyecto tiene más de un cliente WCF, habrá varios clientes entradas de punto de conexión definidas en el archivo de configuración. Cada entrada de cliente WCF tendrá un nombre único basado en su configuración de enlace y el artefacto de Siebel de destino; Por ejemplo, "SiebelBinding_BusinessServices_TimeStamp_Operation". Si se conectan a varias veces para crear los clientes de WCF en el proyecto, varias entradas de configuración de enlace se creará, uno para cada conexión. Estas entradas de configuración de enlace se denominará de la siguiente manera: SiebelBinding, SiebelBinding1, SiebelBinding2, y así sucesivamente. Cada entrada de punto de conexión de cliente creado durante una conexión de acceso hará referencia a la entrada de enlace creada durante esa conexión.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de Siebel mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)