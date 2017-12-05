---
title: "Propiedades de configuración para los adaptadores integrados de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters, security
- adapters, passwords
- IReceiveLocation.CustomData property
- security, passwords
- ISendPort.CustomData property
- binding files, passwords
- adapters, properties
- binding files, security
ms.assetid: 4780a558-4322-428a-aa4a-0c32913faded
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 950f244c3a46af87164c4e276a50cd7a91fee14b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="configuration-properties-for-integrated-biztalk-adapters"></a>Propiedades de configuración para adaptadores integrados de BizTalk
El modelo de objetos del explorador de BizTalk expone la **IReceiveLocation.CustomData** y **ISendPort.CustomData** propiedades que contienen la bolsa de propiedades de configuración de adaptador en forma de un valor de nombre cadena XML de par. Esta cadena XML de par nombre/valor se almacena en un \<CustomProps\> elemento dentro de un \<TransportTypeData\> elemento en un archivo de enlace. La mayoría de la información de la \<CustomProps\> elemento corresponde a la información que se pueden establecer para un adaptador en la interfaz de usuario de BizTalk Server (por ejemplo, la consola de administración de BizTalk o el Explorador de BizTalk). Si estos valores se encuentran en un archivo de enlace, se aplicarán a la configuración del adaptador para las ubicaciones de recepción y los puertos de envío especificados cuando se importa el archivo de enlace. La información de configuración de todos los adaptadores se almacena en la base de datos de Inicio de sesión único.  
  
 En esta sección se describen las propiedades de configuración que se pueden definir para cada adaptador integrado de BizTalk.  
  
> [!NOTE]
>  Información de contraseña que se almacena en la \<TransportTypeData\> elemento de un archivo de enlace está enmascarada de modo que los datos confidenciales no se guardan en texto no cifrado. En función del transporte, la información de la contraseña se reemplaza con un valor nulo (NULL) o con asteriscos. Debe especificar manualmente esta información en el archivo de enlace para actualizar la configuración del adaptador antes de importar el archivo de enlace a la configuración del BizTalk Server de destino.  
  
 Los datos de configuración para adaptadores generada mediante el marco de trabajo se almacenan en un \<AdapterConfig\> elemento. Puesto que la \<AdapterConfig\> elemento especifica la VT_BSTR (vt = "8") tipo de datos, el  **\< \>**  caracteres contenidos en este elemento deben convertirse o se producirá un error cuando se intento de importar el archivo de enlace. Esto causa que el texto de los datos de configuración sea menos legible para las personas que si estos caracteres no estuvieran acompañados de marcas de escape. En el ejemplo siguiente se muestra el efecto de las marcas de escape de estos caracteres desde los datos de configuración de ejemplo para un puerto de envío enlazado al adaptador de POP3.  
  
 **Los datos de configuración de TransportTypeData que no se convierte los caracteres de <> utilizados en el \<AdapterConfig\> elemento**  
  
 Estos datos de configuración no están válidos porque la \<AdapterConfig\> elemento especifica la VT_BSTR (vt = "8") tipo de datos y la \< \> caracteres contenidos en el \<AdapterConfig\> elemento sin escape:  
  
```  
<TransportTypeData>  
<CustomProps>  
<AdapterConfig vt="8">  
<Config xmlns:xsi=http://www.w3.org/2001/XMLSchema-instance xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
<mailServer>test.microsoft.com</mailServer>  
<serverPort>0</serverPort>  
<userName>testuser</userName>  
<password>******</password>  
<authenticationScheme>Basic</authenticationScheme>  
<sslRequired>false</sslRequired>  
<applyMIME>true</applyMIME>  
<bodyPartContentType>text/xml</bodyPartContentType>  
<bodyPartIndex>1</bodyPartIndex>  
<errorThreshold>10</errorThreshold>  
<pollingInterval>5</pollingInterval>  
<pollingUnitOfMeasure>Minutes</pollingUnitOfMeasure>   
<uri>POP3://test.microsoft.com#testuser</uri>  
</Config>  
</AdapterConfig>  
</CustomProps>  
</TransportTypeData>  
```  
  
 **Los datos de configuración de TransportTypeData que convierte los caracteres de <> utilizados en el \<AdapterConfig\> elemento**  
  
 Puesto que la \<AdapterConfig\> elemento especifica la VT_BSTR (vt = "8") tipo de datos, el \< \> caracteres deben convertirse de la \<AdapterConfig\> elemento tal como se muestra a continuación:  
  
```  
<TransportTypeData>  
<CustomProps>  
<AdapterConfig vt="8">  
<Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
xmlns:xsd="http://www.w3.org/2001/XMLSchema"><mailServer>test  
microsoft.com</mailServer><serverPort>0</serverPort>&  
lt;userName>testuser</userName><password>******</pass  
word><authenticationScheme>Basic</authenticationScheme>&  
lt;sslRequired>false</sslRequired><applyMIME>true</ap  
plyMIME><bodyPartContentType>text/xml</bodyPartContentType&  
gt;<bodyPartIndex>1</bodyPartIndex><errorThreshold>10  
</errorThreshold><pollingInterval>5</pollingInterval>  
<pollingUnitOfMeasure>Minutes</pollingUnitOfMeasure><uri  
>POP3://test.microsoft.com#testuser</uri></Config>  
</AdapterConfig>  
</CustomProps>  
</TransportTypeData>  
```  
  
 Entre los adaptadores integrados que se han creado con el marco de trabajo de adaptadores se incluyen los siguientes:  
  
-   Adaptador de FTP  
  
-   Adaptador de MQSeries  
  
-   Adaptador de MSMQ  
  
-   Adaptador de POP3  
  
-   Adaptador de Windows Sharepoint Services  
  
 Para ver una cadena de ejemplo usada como los datos de configuración de TransportTypeData para cada adaptador integrado, consulte en esta sección el tema sobre propiedades de configuración asociado al adaptador que corresponda.  
  
## <a name="in-this-section"></a>En esta sección  
 [Tipos de variables de las propiedades de configuración](../core/configuration-property-variable-types.md)  
  
 [Propiedades de configuración del adaptador de archivo](../core/file-adapter-configuration-properties.md)  
  
 [Propiedades de configuración del adaptador de FTP](../core/ftp-adapter-configuration-properties.md)  
  
 [Propiedades de configuración del adaptador de HTTP](../core/http-adapter-configuration-properties.md)  
  
 [Propiedades de configuración del adaptador de MQSeries](../core/mqseries-adapter-configuration-properties.md)  
  
 [Propiedades de configuración del adaptador de MSMQ](../core/msmq-adapter-configuration-properties.md)  
  
 [Propiedades de configuración del adaptador de POP3](../core/pop3-adapter-configuration-properties.md)  
  
 [Propiedades de configuración del adaptador de SMTP](../core/smtp-adapter-configuration-properties.md)  
  
 [Propiedades de configuración del adaptador de SOAP](../core/soap-adapter-configuration-properties.md)  
  
 [Propiedades de configuración del adaptador de Windows SharePoint Services](../core/windows-sharepoint-services-adapter-configuration-properties.md)