---
title: "Adaptadores de recepción de la publicación de metadatos de servicio de WCF | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- publishing, WCF services
- WCF services, publishing
ms.assetid: 4df09e8f-e0c9-41c5-bd71-13bb0e96cd97
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d922c0acecf81a96b0e40cebf739e7b56c5ffd3e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="publishing-service-metadata-for-the-wcf-receive-adapters"></a>Publicar metadatos de servicio para los adaptadores de recepción WCF
Puede usar el Asistente para publicación de Servicio WCF de BizTalk para crear servicios WCF para la publicación de metadatos de servicio de las ubicaciones de recepción WCF existentes. Para generar el código de modelo de servicio de cliente de los documentos de metadatos publicados puede usar la herramienta Utilidad de metadatos del modelo de servicio (SvcUtil.exe) incluida en el [!INCLUDE[btsCoName](../includes/btsconame-md.md)] [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] Kit de desarrollo de Software (SDK) para [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] y [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] Componentes de tiempo de ejecución.  
  
> [!NOTE]
>  Antes de publicar los metadatos de servicio para los adaptadores de WCF, debe crear el WCF mediante la consola de administración de BizTalk o la herramienta de línea de comandos BTSTask incluida con las ubicaciones de recepción [!INCLUDE[btsCoName](../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información sobre cómo crear un WCF, ubicación de recepción, vea el tema correspondiente para cada adaptador WCF en [adaptadores de WCF](../core/wcf-adapters.md).  
  
 **Versiones de IIS**  
  
 El Servicio WCF que publica metadatos de servicio se puede ejecutar en las siguientes versiones de Servicios de Internet Information Server (IIS) en los sistemas operativos que aparecen a continuación:  
  
-   **IIS 7.0 y 7.5 en Windows Vista, Windows Server 2008 SP2 y Windows Server 2008 R2.** IIS 7.0 y 7.5 proporcionan el mismo modelo de proceso avanzado que IIS 6.0. Los servicios WCF de BizTalk publicados deben ejecutarse en el modo de compatibilidad ASP.NET de IIS 7.0 y 7.5. Se puede tener acceso a los metadatos de servicio publicados por las aplicaciones web en IIS 7.0 y 7.5 para los adaptadores de recepción WCF mediante el transporte HTTP.  
  
 **La publicación de metadatos de servicio para ubicaciones de recepción de WCF**  
  
 Para publicar los metadatos de servicio para las ubicaciones de recepción WCF, debe utilizar el Asistente para publicación de Servicio WCF de BizTalk con el objetivo de crear una aplicación Web para alojar servicios WCF que proporcionan metadatos de servicio. Esto permite llamar a una ubicación de recepción como si fuese un servicio WCF.  El Asistente para publicación de Servicio WCF de BizTalk genera los siguientes archivos en la carpeta raíz de la aplicación Web creada:  
  
|Archivo|Carpeta|Description|  
|----------|------------|-----------------|  
|Servicios WCF (archivos .svc)|\|Servicios WCF que publican metadatos de servicio para las ubicaciones de recepción WCF. Los servicios WCF publican metadatos de servicio para recuperarlos mediante una solicitud HTTP/GET.|  
|Web.config|\|Archivo de configuración de ASP.NET que contiene información de los comportamientos de la aplicación Web ASP.NET, los comportamientos de los servicios WCF publicados, el extremo de metadatos y la configuración específica de BizTalk. El asistente genera Web.config cuando el **httpGetEnabled** atributo de la  **\<serviceMetadata >** elemento está establecido en **true**. Puede usar una herramienta de importación de metadatos (como SvcUtil.exe) para generar el código de cliente necesario para llamar a este servicio en el entorno de desarrollo. La dirección en la que se publican los metadatos es la dirección del extremo del servicio WCF más una **? wsdl** cadena de consulta. **Nota:** el enlace de metadatos predeterminado generado por el Asistente para publicación de WCF de BizTalk no es seguro y permite el acceso anónimo a los metadatos. Los metadatos de servicio contienen una descripción detallada del servicio y es posible que contengan, de forma intencionada o involuntaria, información confidencial. Para evitar el acceso no autorizado a los metadatos de servicio, puede modificar Web.config para que utilice un enlace seguro para el extremo de metadatos.|  
|ServiceDescription.xml|\|Archivo XML que describe los contratos del Servicio WCF publicado incluidos los tipos de mensajes.|  
|Esquemas de BizTalk (archivos .xsd)|\App_Data|Esquemas XML que definen la estructura de mensajes de instancia XML, que se usan en la ubicación de recepción WCF.|  
|SchemaIndex.xml|\App_Data|Archivo XML que indica los archivos de esquema XML utilizados en la ubicación de recepción WCF.|  
|Serialization.xsd|\App_Data|Esquema XML exportado por [DataContractSerializer](http://go.microsoft.com/fwlink/?LinkId=81722) para los tipos, elementos y atributos del espacio de nombres, http://schemas.microsoft.com/2003/10/Serialization/.|  
|BindingInfo.xml|\App_Data\Temp|Archivo de enlace de BizTalk que puede importar la herramienta de línea de comandos de desarrollo o el asistente para la configuración de ubicaciones de recepción. Los servicios WCF publicados no usan este archivo ni la carpeta Temp en tiempo de ejecución.|  
|WcfServiceDescription.xml|\App_Data\Temp|Archivo XML que resume la configuración que se ha utilizado con el Asistente para publicación de Servicio WCF de BizTalk para crear esta aplicación Web. Los servicios WCF publicados no usan este archivo ni la carpeta Temp en tiempo de ejecución.|  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo usar el Asistente de publicación de servicios de WCF de BizTalk para publicar los metadatos del servicio de ubicación de recepción de WCF para enrutamiento por contenidos](../core/publish-service-metadata-for-a-wcf-receive-location-for-content-based-routing.md)  
  
-   [Cómo usar el Asistente de publicación de servicios de WCF de BizTalk para publicar los metadatos del servicio de ubicación de recepción WCF enlazada con un puerto de orquestación](../core/publish-receive-location-service-metadata-biztalk-wcf-service-publishing-wizard.md)  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: Publicar servicios WCF con el adaptador WCF-NetMsmq](../core/walkthrough-publishing-wcf-services-with-the-wcf-netmsmq-adapter.md)