---
title: "Propiedades de configuración de adaptador de Windows Sharepoint Services | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code samples, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, properties
- receive locations, adapters
- Windows SharePoint Services adapters, code sample
- Windows SharePoint Services adapters, send ports
- Windows SharePoint Services adapters, receive locations
- Windows SharePoint Services adapters
- send ports, adapters
ms.assetid: 20b08959-75d3-4613-9cea-582ac2813415
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e6e26d51914211c5c51dfa232be4383d54f5e3c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="windows-sharepoint-services-adapter-configuration-properties"></a>Propiedades de configuración del adaptador de Windows SharePoint Services
En la siguiente tabla se enumeran las propiedades de configuración que se pueden definir para una ubicación de recepción del adaptador de Windows Sharepoint Services.  
  
|Nombre de la propiedad|Tipo|Description|Restricciones|Comentarios|  
|-------------------|----------|-----------------|------------------|--------------|  
|SiteUrl|VT_BSTR|Especifica la dirección URL completa del sitio Web de Windows SharePoint Services.|La URI de un puerto de envío o ubicación de recepción no puede superar los 256 caracteres.|Ninguno|  
|WssLocation|VT_BSTR|Especifica la dirección URL de la biblioteca de documentos de Windows SharePoint Services, asociada al sitio SharePoint, en la que se recuperan los documentos.|No se pueden recibir mensajes de una lista o carpeta de SharePoint.|A veces, la biblioteca de documentos de SharePoint no coincide con el nombre del elemento. Compruebe la barra de direcciones de Internet Explorer para conocer la dirección URL correcta.|  
|ViewName|VT_BSTR|Especifica la vista de Windows SharePoint Services que se utiliza para filtrar los documentos procesados por el adaptador.|Ninguno|Se procesarán todos los mensajes de una vista plana.|  
|ArchiveLocation|VT_BSTR|Especifica la dirección URL de la carpeta de Windows SharePoint Services, relativa al sitio de SharePoint donde se archivan los archivos procesados.|Ninguno|A veces, la URL de la biblioteca de documentos (o carpeta) de SharePoint no coincide con el nombre del elemento. Compruebe la barra de direcciones de Internet Explorer para conocer la dirección URL correcta.|  
|NamespaceAliases|VT_BSTR|Especifica una lista separada por comas o punto y coma de definiciones de alias de espacios de nombres.|Ninguno|Ninguno|  
|ArchiveFileName|VT_BSTR|Especifique el nombre de archivo de Windows SharePoint Services de archivo almacenado.|Este campo no admite las macros "%SendingOrchestrationID%" ni "%SendingOrchestrationType%".|Ninguno|  
|Sobrescribir|VT_BSTR|Especifica si deben o no sobrescribirse los archivos almacenados.|Los valores válidos son:<br /><br /> -Sí<br />-ninguna|El valor predeterminado es no.|  
|ErrorThreshold|VT_BSTR|Especifica el número máximo de errores de sondeo consecutivos que ha detectado el adaptador hasta que se deshabilita la ubicación de recepción.|Los valores válidos son de 0 a 2147483647.|Defina esta propiedad como 0 para no deshabilitar nunca la ubicación de recepción.<br /><br /> El valor predeterminado es 10.|  
|PollingInterval|VT_BSTR|Especifica el intervalo de tiempo, en segundos, entre dos consultas consecutivas realizadas por el adaptador para determinar si hay mensajes nuevos por procesar.|Los valores válidos son de 1 a 2147483647.|Un valor bajo mejora el rendimiento y el tiempo de respuesta del adaptador.<br /><br /> El valor predeterminado es 60.|  
|BatchSize|VT_BSTR|Especifica el número máximo de documentos que procesará en un solo lote el servicio web del adaptador de mensajería de Windows SharePoint Services.|Los valores válidos son de 1 a 2147483647.|Un lote procesado podría contener menos mensajes de los definidos en el tamaño del lote, pero nunca podrá contener más mensajes.<br /><br /> El valor predeterminado es 20.|  
|OfficeIntegration|VT_BSTR|Especifique el nivel de integración con Microsoft Office.|Los valores válidos son:<br /><br /> -   **opcional** : intenta quitar las instrucciones de procesamiento de InfoPath si es posible o procesar como es si no es posible.<br />-   **ya no** -procesar el documento "tal"cual.<br />-   **Sí** : quitar las instrucciones de procesamiento de InfoPath u omitir el mensaje si se produce un error.|El valor predeterminado es opcional.|  
|Timeout|VT_BSTR|Especifique el tiempo de espera, en milisegundos, para las llamadas de servicio de Web de adaptador en tiempo de ejecución realizadas en el servicio Web del adaptador de Windows SharePoint Services.|Los valores válidos son de 1000 a 2147483647.|El valor predeterminado es 100000.|  
|AdapterWSPort|VT_BSTR|Especifica el puerto HTTP del sitio Web de IIS donde está instalado el servicio web del adaptador de Windows SharePoint Services.|Ninguno|El valor predeterminado es 80.|  
|uri|VT_BSTR|Especifica la ruta completa a la biblioteca de documentos de Windows SharePoint Services.|La URI de un puerto de envío o ubicación de recepción no puede superar los 256 caracteres.|Ninguno|  
  
 En el siguiente código se muestra el formato de la cadena que se utiliza para establecer las propiedades:  
  
```  
<CustomProps><AdapterConfig vt="8"><ReceiveLocation xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><SiteUrl>http://BTS2006/sites/BASSite/</SiteUrl><WssLocation>Shared Docs</WssLocation><ViewName>Approved</ViewName><ArchiveLocation>Archive</ArchiveLocation><NamespaceAliases>po='http://POProcess/POrder'</NamespaceAliases><ArchiveFileName>PurchaseOrder0001.xml</ArchiveFileName><Overwrite>no</Overwrite><ErrorThreshold>10</ErrorThreshold><PollingInterval>60</PollingInterval><BatchSize>20</BatchSize><OfficeIntegration>optional</OfficeIntegration><Timeout>100000</Timeout><AdapterWSPort>80</AdapterWSPort><uri>wss://bts2006:80/sites/BASSite/Shared+Docs?ViewName=Approved</uri></ReceiveLocation></AdapterConfig></CustomProps>  
```  
  
 En la siguiente tabla se enumeran las propiedades de configuración que se pueden definir para un puerto de envío del adaptador de Windows Sharepoint Services.  
  
|Nombre de la propiedad|Tipo|Description|Restricciones|Comentarios|  
|-------------------|----------|-----------------|------------------|--------------|  
|SiteUrl|VT_BSTR|Especifique la dirección URL completa del sitio Web de Windows SharePoint Services|La URI de un puerto de envío o ubicación de recepción no puede superar los 256 caracteres.|Ninguno|  
|WssLocation|VT_BSTR|Especifica la dirección URL de la carpeta de destino de Windows SharePoint Services, relativa al sitio de SharePoint.|Ninguno|A veces, la dirección URL de la biblioteca de documentos, la lista o la carpeta de SharePoint es diferente del nombre de ese elemento. Compruebe la barra de dirección de Internet Explorer para ver la dirección URL correcta.|  
|Sobrescribir|VT_BSTR|Especifica si se sobrescriben los archivos existentes.|Los valores válidos son:<br /><br /> -ninguna<br />-orquestación<br />-cambiar el nombre<br />-Sí|El valor predeterminado es no.|  
|NamespaceAliases|VT_BSTR|Especifica una lista separada por comas o punto y coma de definiciones de alias de espacios de nombres.|Ninguno|Utilice este campo para definir los alias de espacios de nombres utilizados en las consultas XPATH que se han especificado en los campos.<br /><br /> Esta propiedad no anula la propiedad de contexto de mensaje WSS.ConfigNamespacesAliases definida por la orquestación. En su lugar se combinan los dos valores.|  
|FileName|VT_BSTR|Especifica el nombre del archivo de Windows SharePoint Services.|Ninguno|Cuando se envían mensajes a una lista, se omite el valor especificado en la propiedad Nombre de archivo y no se guarda en ninguna columna de SharePoint. Las listas de SharePoint no tienen una columna Nombre de archivo. En su lugar actualice la columna Título con alguna de las 16 columnas disponibles.|  
|OfficeIntegration|VT_BSTR|Especifica un valor para cambiar el documento de manera que se abra automáticamente en una aplicación de Office como InfoPath o para guardar el documento tal cual si no se encuentra ninguna solución de InfoPath.|Los valores válidos son:<br /><br /> -ninguna<br />-opcional<br />-orquestación<br />-Sí<br />-yesformlibrary|El valor predeterminado es opcional.|  
|TemplatesDocLib|VT_BSTR|Especifica el nombre de una biblioteca de documentos de SharePoint donde estén almacenadas las soluciones de InfoPath.|Esta propiedad debe contener un valor si la propiedad TemplatesNamespaceCol contiene uno.|La biblioteca de documentos debe tener al menos una columna de SharePoint del tipo Una línea de texto que se rellena con el espacio de nombres y el nodo raíz de los documentos XML que se pueden abrir con esta solución de InfoPath, o solo el nodo raíz.|  
|TemplatesNamespaceCol|VT_BSTR|Especifica el nombre de la columna de SharePoint Biblioteca de documentos de reserva de plantillas que almacena el espacio de nombres de la solución de InfoPath.|Esta propiedad debe contener un valor si la propiedad TemplatesDocLib contiene uno.<br /><br /> Este campo distingue mayúsculas de minúsculas.|Ninguno|  
|CustomTemplatesDocLib|VT_BSTR|Especifica el nombre de una biblioteca de documentos de SharePoint donde estén almacenadas las soluciones de InfoPath.|Esta propiedad debe contener un valor si la propiedad CustomTemplatesNamespaceCol contiene uno.<br /><br /> Este campo distingue mayúsculas de minúsculas.|Ninguno|  
|CustomTemplatesNamespaceCol|VT_BSTR|Especifica el nombre de la columna de SharePoint Biblioteca de documentos de plantillas que almacena el espacio de nombres de la solución de InfoPath.|Esta propiedad debe contener un valor si la propiedad CustomTemplatesDocLib contiene uno.<br /><br /> Este campo distingue mayúsculas de minúsculas.|Ninguno|  
|PropertyName(n)|VT_BSTR|Especifica el nombre de la columna de Windows SharePoint Services que existe en la biblioteca de documentos de destino.|Este campo distingue mayúsculas de minúsculas.|Puede especificar hasta 16 columnas.|  
|PropertySource(n)|VT_BSTR|Especifica el valor de la columna que se va a definir para este mensaje.|Ninguno|Puede especificar hasta 16 valores de columna.|  
|Timeout|VT_BSTR|Especifica el tiempo de espera, en milisegundos, de las llamadas del servicio web de tiempo de ejecución del adaptador que se realizan al servicio web del adaptador de Windows SharePoint Services.|Los valores válidos son de 1000 a 2147483647.|El valor predeterminado es 100000.|  
|AdapterWSPort|VT_BSTR|Especifica el puerto HTTP del sitio Web de IIS donde está instalado el servicio web del adaptador de Windows SharePoint Services.|Ninguno|El valor predeterminado es 80.|  
|uri|VT_BSTR|Especifica la ruta completa de la dirección URL correspondiente a la carpeta de destino de Windows SharePoint Services.|La URI de un puerto de envío o ubicación de recepción no puede superar los 256 caracteres.|Ninguno|  
  
 En el siguiente código se muestra el formato de la cadena que se utiliza para establecer las propiedades:  
  
> [!NOTE]
>  Las definiciones de PropertyName2 y  PropertySource2 hasta PropertyName16 y PropertySource16 se han omitido de esta cadena.  
  
```  
<CustomProps><AdapterConfig vt="8"><SendPort xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><SiteUrl>http://BizTalkServer/sites/BASSite/</SiteUrl><WssLocation>Shared Documents/Purchase Orders</WssLocation><Overwrite>yes</Overwrite><NamespaceAliases>po='http://OrderProcess/POrder'</NamespaceAliases><FileName>PurchaseOrder0001.xml</FileName><OfficeIntegration>yesformlibrary</OfficeIntegration><TemplatesDocLib>Templates</TemplatesDocLib><TemplatesNamespaceCol>NamespaceFallback</TemplatesNamespaceCol><CustomTemplatesDocLib>Shared Documents</CustomTemplatesDocLib><CustomTemplatesNamespaceCol>Namespace</CustomTemplatesNamespaceCol><PropertyName1>Column1</PropertyName1><PropertySource1>Column1 Value</PropertySource1><Timeout>100000</Timeout><AdapterWSPort>80</AdapterWSPort><uri>wss://biztalkserver:80/sites/BASSite/Shared%20Documents/Purchase%20Orders</uri></SendPort></AdapterConfig></CustomProps>  
```  
  
> [!NOTE]
>  Al especificar los datos de configuración de TransportTypeData para un adaptador que se genera utilizando el marco de trabajo, los pares de nombre/valor que se usan todos se almacenarán en el \<AdapterConfig > elemento. Puesto que la \<AdapterConfig > elemento especifica la VT_BSTR (vt = "8"), a continuación, el tipo de datos de la \< > caracteres en los datos deben convertirse.