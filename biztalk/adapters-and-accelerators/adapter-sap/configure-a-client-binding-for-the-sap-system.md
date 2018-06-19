---
title: Configurar un enlace para el sistema SAP del cliente | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- proxy programming, creating a proxy
- creating a proxy
- how to, create a proxy
ms.assetid: bceef132-29ff-4207-a37d-bf94fab484dd
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1e9a4f84dbf98a17b2c1a918e30ab85b8e86c13
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963858"
---
# <a name="configure-a-client-binding-for-the-sap-system"></a>Configurar un enlace para el sistema SAP de cliente
Una vez que haya generado la clase de cliente WCF, puede crear un cliente WCF (instancia) e invocar sus métodos para consumir el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]. Para obtener información sobre cómo generar el código de clase y la aplicación auxiliar de cliente WCF para las operaciones que el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone, consulte [generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución SAP](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).  
  
 Para crear al cliente de WCF, debe especificar una dirección de extremo y un enlace. La dirección de punto de conexión debe contener un URI de conexión válida de SAP y el enlace debe ser una instancia de un enlace de SAP (**SAPBinding**). Para obtener más información sobre el URI de conexión de SAP, consulte [crear la conexión del sistema SAP URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).  
  
 Puede especificar el enlace de SAP y la dirección del extremo en el código o en un archivo de configuración. Cuando se usa el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar la clase de cliente WCF, también se crea un archivo de configuración (app.config) para el proyecto. Este archivo contiene los valores de configuración que reflejan la conexión y propiedades de información de enlace (excepto las credenciales) que especificó cuando se conecta al sistema SAP con el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
## <a name="specifying-the-binding-and-endpoint-address-in-code"></a>Especificar el enlace y la dirección del extremo en el código  
 El código siguiente muestra cómo crear a un cliente de WCF especificando el enlace y la dirección del extremo en el código. Es recomendable para especificar las credenciales del sistema SAP mediante la **ClientCredentials** propiedad del cliente WCF, en lugar de en el URI proporcionado para la dirección del punto de conexión.  
  
```  
// A WCF client that targets an RFC is created  
// by using a binding object and endpoint address  
SAPBinding sapBinding = new SAPBinding();  
EndpointAddress sapAddress = new EndpointAddress("sap://CLIENT=800;LANG=EN;@a/YourSAPHost/00");  
  
RfcClient rfcClient = new RfcClient(sapBinding, sapAddress);  
  
rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
  
rfcClient.Open();  
```  
  
## <a name="specifying-the-binding-and-endpoint-address-in-a-configuration-file"></a>Especificar el enlace y dirección de punto de conexión en un archivo de configuración  
 El código siguiente muestra cómo crear a un cliente de WCF especificando el enlace y dirección de punto de conexión en un archivo app.config.  
  
```  
// A WCF client that targets an RFC is created  
// by specifying the client endpoint information in app.config  
RfcClient rfcClient = new RfcClient("SAPBinding_Rfc");  
  
rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
  
rfcClient.Open();  
```  
  
 El siguiente XML muestra el archivo de configuración creado para la tabla EMP por la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Este archivo contiene la configuración de punto de conexión del cliente al que hace referencia en el ejemplo anterior.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    <system.serviceModel>  
        <bindings>  
            <sapBinding>  
                <binding name="SAPBinding" closeTimeout="00:01:00" openTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00" receiveIdocFormat="Typed"  
                    generateFlatFileCompatibleIdocSchema="true" maxConnectionsPerSystem="50"  
                    enableConnectionPooling="true" idleConnectionTimeout="00:15:00"  
                    flatFileSegmentIndicator="SegmentDefinition" enablePerformanceCounters="false"  
                    autoConfirmSentIdocs="false"  
                    acceptCredentialsInUri="false" padReceivedIdocWithSpaces="false"  
                    enableBizTalkCompatibilityMode="false" />  
            </sapBinding>  
        </bindings>  
        <client>  
            <endpoint address="sap://CLIENT=800;LANG=EN;@a/YourSAPHost/00?RfcSdkTrace=False&AbapDebug=False&UseSapGui=Without"  
                binding="sapBinding" bindingConfiguration="SAPBinding" contract="Rfc"  
                name="SAPBinding_Rfc" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
 Si un proyecto tiene más de un cliente WCF, habrá varios clientes entradas de punto de conexión definidas en el archivo de configuración. Cada entrada de cliente WCF tendrá un nombre único basado en su configuración de enlace y los artefactos del sistema SAP de destino (por ejemplo, Rfc y Trfc); Por ejemplo, "SAPBinding_Rfc". Si se conectan a varias veces para crear los clientes de WCF en el proyecto, varias entradas de configuración de enlace se creará, uno para cada conexión. Estas entradas de configuración de enlace se denominará de la siguiente manera: SAPBinding1, SAPBinding2, y así sucesivamente. Cada entrada de punto de conexión de cliente creado durante una conexión de acceso hará referencia a la entrada de enlace creada durante esa conexión.  
  
> [!IMPORTANT]
>  El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Emerge artefactos SAP diferentes del mismo tipo (por ejemplo, RFC, TRFC y IDOC) como operaciones diferentes del mismo contrato de servicio. Por ejemplo, dos RFC diferentes, RFC_EXAMPLE_A y RFC_EXAMPLE_B, ambos se expone en el mismo contrato de servicio ("Rfc"). Esto significa que ambos RFC invocará la misma clase de cliente WCF, **RfcClient**, y que se va a declarar los parámetros para ambos RFC en el mismo espacio de nombres. Por lo tanto, debe generar el cliente WCF para ambos RFC durante el mismo [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] sesión (conexión) para evitar experimentando una colisión de espacio de nombres al compilar la solución.  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de SAP mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)   
 [Generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución SAP](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)   
 [Crear el URI de conexión de sistema SAP](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)