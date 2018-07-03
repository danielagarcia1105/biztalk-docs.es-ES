---
title: Uso de ServiceModel Metadata Utility Tool con el adaptador de BizTalk para mySAP Business Suite | Microsoft Docs
description: 'Usar svcutil.exe para un enlace no predeterminado, o para crear una clase de cliente de WCF o un contrato de servicio WCF con el adaptador de SAP: módulo de adaptador de BizTalk (BAP)'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ServiceModel Metadata Utility Tool, creating a WCF Client Class or a WCF service contract with the tool
- ServiceModel Metadata Utility Tool, configuring the tool for the adapter
ms.assetid: 7ac08012-bb12-4983-9402-be84fe3997d8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a8bdbf2a3b3a3c359a4c3e4912e2b6e18928023
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003181"
---
# <a name="using-the-servicemodel-metadata-utility-tool-with-the-biztalk-adapter-for-mysap-business-suite"></a>Uso de ServiceModel Metadata Utility Tool con el adaptador de BizTalk para mySAP Business Suite
Puede utilizar ServiceModel Metadata Utility Tool (svcutil.exe) para generar una clase de cliente WCF o un contrato de servicio WCF (interfaz) para las operaciones que el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] expone. Después de ejecutar svcutil.exe para generar una clase de cliente WCF o un contrato de servicio WCF, puede incluir el archivo generado en el código y crear instancias de la clase generada o implementar un servicio WCF desde la interfaz generada para realizar operaciones en SAP sistema.  
  
 Uso de svcutil.exe requiere que proporcione un URI que contiene las credenciales de conexión. Dado que, de forma predeterminada, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] deshabilita las credenciales en el URI de conexión, debe configurar svcutil.exe para utilizar un enlace no predeterminado para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. También puede configurar otras propiedades de enlace en el enlace no predeterminado; Por ejemplo, para crear un cliente de WCF para operaciones de BAPI, debe establecer el **EnableSafeTyping** enlazar la propiedad a **true**.  
  
 Las secciones siguientes muestran cómo configurar svcutil.exe y cómo utilizar svcutil.exe para generar código de cliente WCF o un contrato de servicio WCF con el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
##  <a name="BKMK_ConfigureSvcutil"></a> Configuración de svcutil.exe para el adaptador de SAP  
 Para configurar svcutil.exe para utilizar un enlace no predeterminado, debe crear una copia local de svcutil.exe y, a continuación, crear o modificar una copia local del archivo de configuración svcutil.exe.config.  
  
1. Cree una carpeta y copie svcutil.exe en la nueva carpeta. Normalmente puede encontrar svcutil.exe en la ubicación de instalación de Windows SDK, específicamente, C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin.  
  
2. Cree un archivo denominado svcutil.exe.config en la nueva carpeta.  
  
3. Agregar un enlace y un punto de conexión de cliente en el archivo svcutil.exe.config. Debe ejecutar svcutil.exe desde la nueva carpeta para asegurarse de que se usa la configuración correcta.  
  
   > [!IMPORTANT]
   >  El atributo de nombre del punto de conexión de cliente debe especificar el esquema utilizado en el URI de conexión. Este valor distingue mayúsculas de minúsculas.  
  
   ```  
   <configuration>  
     <system.serviceModel>  
       <client>  
         <!-- the name should match the required scheme of the WS-Metadata Exchange endpoint   
         and the contract should be "IMetadataExchange" -->  
         <endpoint name="sap"  
                   binding="sapBinding"  
                   bindingConfiguration="SAPBinding"  
                   contract="IMetadataExchange" />  
       </client>  
       <bindings>  
         <sapBinding>  
           <binding name="SAPBinding" acceptCredentialsInUri="true"/>  
         </sapBinding>  
       </bindings>  
  
     </system.serviceModel>  
  
   </configuration>  
   ```  
  
   Puede establecer cualquiera de las propiedades de enlace de la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] en la configuración de enlace. Por ejemplo, puede especificar el enlace no predeterminado siguiente al utilizar svcutil.exe para generar a un cliente de WCF para operaciones de BAPI.  
  
```  
<bindings>  
  <sapBinding>  
    <binding name="SAPBinding" acceptCredentialsInUri="true"/>  
  </sapBinding>  
</bindings>  
```  
  
 Para obtener más información acerca de cómo configurar un enlace no predeterminado para svcutil.exe, vea el [extremo de metadatos personalizada Secure](https://msdn.microsoft.com/library/aa395212.aspx).
  
## <a name="creating-a-wcf-client-class-or-a-wcf-service-contract-with-svcutilexe"></a>Creación de una clase de cliente WCF o un contrato de servicio WCF con svcutil.exe  
 Para utilizar svcutil.exe para generar código de cliente WCF o un contrato de servicio WCF (interfaz) para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], debe proporcionar una conexión de URI que especifica un punto de conexión de WS-Metadata Exchange (MEX) y la o las operaciones que se desea svcutil.exe para generar código. También debe especificar las credenciales de conexión para el sistema SAP en el URI de conexión.  
  
> [!NOTE]
>  Para poder usar svcutil.exe con la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], debe configurarlo para usar un valor no predeterminado enlace; para obtener información acerca de cómo hacerlo, consulte [configuración de svcutil.exe para el adaptador SAP](#BKMK_ConfigureSvcutil).  
  
 Especifique un operaciones de punto de conexión y de destino MEX en el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] URI de conexión de la siguiente manera:  
  
- Debe incluir el parámetro "wsdl" en la cadena de consulta. Si es el primer parámetro de la cadena de consulta, se especifica justo después del signo de interrogación (?). Si no es el primer parámetro, debe ir precedida por una y comercial (&).  
  
- Debe seguir el parámetro "wsdl" por uno o varios parámetros "op". Cada parámetro de "op" está precedido por una y comercial (&) y especifica el identificador de nodo de una operación de destino.  
  
  Los tres ejemplos siguientes muestran cómo tener como destino varias operaciones mediante svcutil.exe.  
  
  En este ejemplo se crea una clase de cliente WCF para RFC_CALCULATE_TAXES.  
  
  **. \svcutil "sap://User=YourUserName; Passwd = Su_contraseña; Cliente = 800; Lang = EN; @a/YourSAPHost/00? wsdl & op =http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CALCULATE_TAXES"**  
  
  Este ejemplo crea una clase de cliente WCF SALESORDER_CREATEFROMDAT201 tanto SALESORDER_CREATEFROMDAT202 IDOC.  
  
  **. \svcutil "sap://User=YourUserName; Passwd = Su_contraseña; Cliente = 800; Lang = EN; @a/YourSAPHost/00? wsdl & op =http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Send&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT202//620/Send"**  
  
  Este ejemplo crea un contrato de servicio WCF para recibir los IDOC SALESORDER_CREATEFROMDAT201 desde el sistema SAP. El identificador de nodo especifica una operación de recepción. Dado que este ejemplo está relacionada con la recuperación de metadatos, no hay ninguna necesidad para especificar los parámetros de agente de escucha en el query_string del URI de conexión.  
  
  **. \svcutil "sap://User=YourUserName; Passwd = Su_contraseña; Cliente = 800; Lang = EN; @a/YourSAPHost/00? wsdl & op =http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Receive"**  
  
> [!IMPORTANT]
>  Debe colocar el URI de conexión entre comillas en la línea de comandos. En caso contrario, svcutil.exe intenta recuperar metadatos para las operaciones que el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] no admite. Los resultados de un intento de este tipo son indefinidos.  
  
 De forma predeterminada, svcutil.exe coloca el código generado en el archivo output.cs; Sin embargo, puede cambiar el nombre del archivo de salida y muchas otras opciones que svcutil.exe utiliza estableciendo los modificadores de línea de comandos. Para obtener más información acerca de las opciones que svcutil.exe admite, consulte la [ServiceModel Metadata Utility Tool (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx).
  
 Svcutil.exe no proporciona la capacidad de búsqueda para las operaciones (por ejemplo, mediante el uso de caracteres comodín). Debe especificar explícitamente los identificadores de nodo para las operaciones específicas que desea dirigirse. El identificador de nodo de una operación es equivalente a la cadena de acción del mensaje. No se puede especificar identificadores que hacen referencia solo a las categorías de nodo. Para obtener más información acerca de los identificadores de nodo que la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] superficies, consulte [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md).  
  
 El [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] proporciona exploración avanzada y capacidades de búsqueda que pueden simplificar en gran medida la generación de una clase de cliente WCF y el contrato de servicio WCF. Para obtener más información sobre la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], consulte [generar un cliente de WCF o un contrato de servicio WCF para artefactos de la solución SAP](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).  
  
