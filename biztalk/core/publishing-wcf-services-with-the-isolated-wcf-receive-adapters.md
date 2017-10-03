---
title: "Publicar servicios WCF con WCF aislado adaptadores de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive adapters, WCF services
- publishing, WCF services
- WCF services, receive adapters
- WCF services, publishing
ms.assetid: 62ebf373-075c-4c98-8130-ac2cf06e4a70
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c5305560713771e7279eb013d26ff267aa21a74
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="publishing-wcf-services-with-the-isolated-wcf-receive-adapters"></a>Publicar servicios WCF con WCF aislado adaptadores de recepción
Permitir que los adaptadores de BizTalk Windows Communication Foundation (WCF) [!INCLUDE[btsCoName](../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para comunicarse con aplicaciones basadas en WCF. Los adaptadores de BizTalk WCF son siete adaptadores físicos. Cada adaptador, excepto el adaptador WCF-CustomIsolated, consta adaptadores de envío y recepción.  
  
 Adaptadores de recepción de WCF se proporcionan en dos tipos de adaptadores: aisladas adaptadores de WCF y adaptadores de WCF en curso. Mientras que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administra los adaptadores en curso, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no puede crear instancias de los adaptadores. En cambio, se crean instancias de ellos y se alojan en otro proceso. Los adaptadores de WCF aislados se alojan en aplicaciones Web que se ejecutan en Servicios de Internet Information Server (IIS).  
  
> [!NOTE]
>  Antes de publicar un Servicio WCF con los adaptadores de WCF aislados, debe estar familiarizado con el modo en que los servicios WCF se alojan en Servicios de Internet Information Server (IIS). Para obtener más información acerca de los servicios WCF que se hospedan en IIS, vea "Hosting in IIS" en [http://go.microsoft.com/fwlink/?LinkID=75700](http://go.microsoft.com/fwlink/?LinkID=75700).  
  
 **Versiones de IIS**  
  
 Los tres adaptadores de WCF aislados (WCF-CustomIsolated, WCF-BasicHttp y WCF-WSHttp) se pueden hospedar en las siguientes versiones de IIS en los sistemas operativos que aparecen a continuación:  
  
-   **IIS 7.0 y 7.5 en Windows Vista y Windows Server 2008.** IIS 7.0 y 7.5 proporciona el mismo modelo de proceso avanzado que IIS 6.0. Los servicios WCF de BizTalk publicados deben ejecutarse en el modo de compatibilidad ASP.NET de IIS 7.0 y 7.5.  
  
> [!NOTE]
>  Aunque el Servicio de activación del proceso de Windows (WAS) en IIS 7.0 o 7.5 permite la activación y la comunicación de red mediante protocolos distintos a HTTP, los adaptadores de WCF aislados solo admiten el transporte HTTP.  
  
 **Adaptadores de WCF aislados**  
  
 A continuación se presenta la lista de los adaptadores de WCF aislados:  
  
-   **Adaptador de WCF-WSHttp**. proporciona compatibilidad de los estándares WS-* a través de transporte HTTP. Este adaptador implementa las especificaciones siguientes: WS-Transaction para las interacciones de transacciones entre aplicaciones externas y la base de datos de cuadro de mensaje y WS-Security para la seguridad y la autenticación de mensajes. El transporte es HTTP o HTTPS y los mensajes tienen codificación de texto o de Message Transmission Optimization Mechanism (MTOM).  
  
-   **Adaptador de WCF-BasicHttp**. Se comunica con servicios Web basados en ASMX y clientes y con otros servicios que cumplan con WS-I Basic Profile 1.1. El transporte es HTTP o HTTPS y los mensajes tienen una codificación de texto o MTOM.  
  
-   **Adaptador de WCF-CustomIsolated**. permite el uso de características de extensibilidad de WCF a través del transporte HTTP. El adaptador permite seleccionar y configurar enlaces de WCF y la información de comportamiento de la ubicación de recepción que se ejecuta en un host aislado.  
  
 **Publicar servicios WCF con adaptadores de WCF aislados**  
  
 Para publicar servicios WCF con los adaptadores de recepción WCF aislados, debe usar el Asistente para publicación de Servicio WCF de BizTalk para crear una aplicación Web que aloje los adaptadores de WCF aislados. Además, el Asistente para publicación de Servicio WCF de BizTalk genera los siguientes archivos en la carpeta raíz de la aplicación Web creada:  
  
|Archivo|Carpeta|Description|  
|----------|------------|-----------------|  
|Servicios WCF (archivos .svc)|\|Servicios WCF para las ubicaciones de recepción WCF publicadas con los adaptadores de WCF aislados.|  
|Web.config|\|Archivo de configuración de ASP.NET que contiene información de los comportamientos de la aplicación Web ASP.NET, los comportamientos de los servicios WCF publicados, el extremo de metadatos y la configuración específica de BizTalk. El enlace de metadatos predeterminado generado por el Asistente para publicación de Servicio WCF de BizTalk no es seguro y permite el acceso anónimo a los metadatos. Los metadatos de servicio contienen una descripción detallada del servicio y es posible que contengan, de forma intencionada o involuntaria, información confidencial. Para evitar el acceso no autorizado a los metadatos de servicio, puede modificar Web.config para que utilice un enlace seguro para el extremo de metadatos. **Nota:** no todas las combinaciones de los enlaces de extremo de metadatos y los enlaces de extremo de servicio son válidas. En algunos casos, las configuraciones de enlace de un extremo de metadatos deben coincidir con las configuraciones de enlace de su extremo de servicio. Por ejemplo, el extremo de metadatos no se puede configurar con un modo de seguridad que requiera el transporte HTTP si el extremo del modo de seguridad de su servicio se basa en HTTPS.|  
|ServiceDescription.xml|\|Archivo XML que describe los contratos del Servicio WCF publicado incluidos los tipos de mensajes.|  
|Esquemas de BizTalk (archivos .xsd)|\App_Data|Esquemas XML que definen la estructura de mensajes de instancia XML, que se publican con los adaptadores de WCF aislados.|  
|SchemaIndex.xml|\App_Data|Archivo XML que indica los archivos de esquema XML usados en los servicios WCF publicados.|  
|Serialization.xsd|\App_Data|Esquema XML exportado por [DataContractSerializer](http://go.microsoft.com/fwlink/?LinkId=81722) para los tipos, elementos y atributos del espacio de nombres, http://schemas.microsoft.com/2003/10/Serialization/.|  
|BindingInfo.xml|\App_Data\Temp|Archivo de enlace de BizTalk para crear las ubicaciones de recepción WCF que corresponden a los servicios WCF publicados. La herramienta de desarrollo de línea de comandos o el asistente pueden importar el archivo BindingInfo.xml para crear las ubicaciones de recepción necesarias. Los servicios WCF publicados no usan este archivo ni la carpeta Temp en tiempo de ejecución.|  
|WcfServiceDescription.xml|\App_Data\Temp|Archivo XML que resume la configuración que se ha utilizado con el Asistente para publicación de Servicio WCF de BizTalk para crear esta aplicación Web. Los servicios WCF publicados no usan este archivo ni la carpeta Temp en tiempo de ejecución.|  
  
 Además, puede usar el Asistente para publicación de Servicio WCF de BizTalk para crear ubicaciones de recepción WCF y metadatos de servicio para las ubicaciones de recepción que ejecutan los adaptadores de WCF aislados.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo usar el Asistente de publicación de servicios de WCF de BizTalk para publicar orquestaciones como servicios WCF](../core/publish-orchestrations-as-wcf-services--biztalk-wcf-service-publishing-wizard.md)  
  
-   [Cómo usar el Asistente de publicación de servicios de WCF de BizTalk para publicar esquemas como servicios WCF](../core/publish-schemas-as-wcf-services--use-the-biztalk-wcf-service-publishing-wizard.md)  
  
-   [Configurar IIS para WCF aislado adaptadores de recepción](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md)  
  
-   [Cómo configurar los servicios WCF publicados con el Asistente de publicación de servicios de WCF de BizTalk](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md)  
  
-   [Cómo crear una aplicación .NET para probar un servicio WCF publicado con el Asistente de publicación de servicios de WCF de BizTalk](../core/use-net-application-to-test-wcf-service-published-with-wcf-service-publishing.md)  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: Publicar servicios WCF con el adaptador WCF-BasicHttp](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)