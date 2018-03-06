---
title: "Publicar los metadatos del servicio para adaptadores de recepción WCF | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4df09e8f-e0c9-41c5-bd71-13bb0e96cd97
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f6962ec3068694223bd6ca214d2d7500e0d5316
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
---
# <a name="publishing-service-metadata-for-the-wcf-receive-adapters"></a>Publicar metadatos de servicio para los adaptadores de recepción WCF
Puede usar el Asistente para publicación de Servicio WCF de BizTalk para crear servicios WCF para la publicación de metadatos de servicio de las ubicaciones de recepción WCF existentes. Para generar el código de modelo de servicio de cliente de los documentos de metadatos publicados, que puede usar la herramienta Utilidad de metadatos del modelo de servicio (SvcUtil.exe) incluida en el Kit de desarrollo de Software (SDK) de Windows y componentes de tiempo de ejecución de .NET Framework.  
  
> [!NOTE]
>  Antes de publicar los metadatos de servicio para los adaptadores de WCF, debe crear el WCF ubicaciones de recepción mediante la consola de administración de BizTalk o la herramienta de línea de comandos BTSTask incluida con BizTalk Server. Para obtener más información sobre cómo crear un WCF, ubicación de recepción, vea el tema correspondiente para cada adaptador WCF en [adaptadores de WCF](../core/wcf-adapters.md).  
  
## <a name="iis-versions"></a>Versiones de IIS
  
 El servicio WCF que publica los metadatos del servicio se puede ejecutar en el la versión IIS incluida con el sistema operativo.
  
-   **IIS** proporciona el modelo de proceso avanzado. Los servicios de WCF de BizTalk publicados deben ejecutarse en modo de compatibilidad de ASP.NET. Pueden tener acceso a los metadatos del servicio publicados por las aplicaciones Web en IIS para adaptadores de recepción de WCF mediante el transporte HTTP.  
  
## <a name="publish-service-metadata-for-the-wcf-receive-locations"></a>Publicar metadatos de servicio para ubicaciones de recepción de WCF
  
 Para publicar los metadatos de servicio para las ubicaciones de recepción WCF, debe utilizar el Asistente para publicación de Servicio WCF de BizTalk con el objetivo de crear una aplicación Web para alojar servicios WCF que proporcionan metadatos de servicio. Esto permite llamar a una ubicación de recepción como si fuese un servicio WCF.  El Asistente para publicación de Servicio WCF de BizTalk genera los siguientes archivos en la carpeta raíz de la aplicación Web creada:  
  
|Archivo|Carpeta|Description|  
|----------|------------|-----------------|  
|Servicios WCF (archivos .svc)|\|Ubicaciones de recepción de los servicios WCF que publican metadatos del servicio de WCF. Los servicios WCF publican metadatos de servicio para recuperarlos mediante una solicitud HTTP/GET.|  
|Web.config|\|Archivo de configuración de ASP.NET que contiene información para los comportamientos de la aplicación Web de ASP.NET, los comportamientos del servicio WCF publicados, el extremo de metadatos y la configuración específica de BizTalk. El asistente genera Web.config cuando el **httpGetEnabled** atributo de la  **\<serviceMetadata\>**  elemento está establecido en **true**. Puede usar una herramienta de importación de metadatos (como SvcUtil.exe) para generar el código de cliente necesario para llamar a este servicio en el entorno de desarrollo. La dirección en la que se publican los metadatos es la dirección del extremo del servicio WCF más una **? wsdl** cadena de consulta. **Nota:** el enlace de metadatos predeterminado generado por el Asistente para publicación de WCF de BizTalk no es seguro y permite el acceso anónimo a los metadatos. Los metadatos de servicio contienen una descripción detallada del servicio y es posible que contengan, de forma intencionada o involuntaria, información confidencial. Para evitar el acceso no autorizado a los metadatos de servicio, puede modificar Web.config para que utilice un enlace seguro para el extremo de metadatos.|  
|ServiceDescription.xml|\|Archivo XML que describe el servicio WCF publicado los contratos incluidos los tipos de mensaje.|  
|Esquemas de BizTalk (archivos .xsd)|\App_Data|Esquemas XML que definen la estructura de mensajes de instancia XML, que se usan en la ubicación de recepción WCF.|  
|SchemaIndex.xml|\App_Data|Archivo XML que indica los archivos de esquema XML utilizados en la ubicación de recepción WCF.|  
|Serialization.xsd|\App_Data|Esquema XML exportado por [DataContractSerializer](https://msdn.microsoft.com/library/system.runtime.serialization.datacontractserializer.aspx) para los tipos, elementos y atributos del espacio de nombres, http://schemas.microsoft.com/2003/10/Serialization/.|  
|BindingInfo.xml|\App_Data\Temp|Archivo de enlace de BizTalk que puede importar la herramienta de línea de comandos de desarrollo o el asistente para la configuración de ubicaciones de recepción. Los servicios WCF publicados no usan este archivo ni la carpeta Temp en tiempo de ejecución.|  
|WcfServiceDescription.xml|\App_Data\Temp|Archivo XML que resume la configuración que se ha utilizado con el Asistente para publicación de Servicio WCF de BizTalk para crear esta aplicación Web. Los servicios WCF publicados no usan este archivo ni la carpeta Temp en tiempo de ejecución.|  
  
## <a name="next-steps"></a>Pasos siguientes
  
-   [Usar el Asistente para publicación de servicios WCF de BizTalk para publicar metadatos de servicio para un ubicación de recepción WCF para enrutamiento por contenidos](../core/publish-service-metadata-for-a-wcf-receive-location-for-content-based-routing.md)  
  
-   [Usar el Asistente para publicación de servicios WCF de BizTalk para publicar metadatos de servicio para un ubicación de recepción WCF enlazada con un puerto de orquestación](../core/publish-receive-location-service-metadata-biztalk-wcf-service-publishing-wizard.md)  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: Publicación de servicios WCF con el adaptador WCF-NetMsmq](../core/walkthrough-publishing-wcf-services-with-the-wcf-netmsmq-adapter.md)