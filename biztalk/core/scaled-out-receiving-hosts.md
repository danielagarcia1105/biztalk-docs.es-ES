---
title: "Hosts de recepción escalados | Documentos de Microsoft"
ms.custom: 
ms.date: 2016-03-17
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters, receive adapters
- high availability
- HTTP adapters, scaling
- receive adapters, scaling
- POP3 adapters, scaling
- MSMQ adapters, scaling
- EDI adapters, scaling
- Web services, scaling
- hosts, multiple
- MQSeries adapters, scaling
- adapters, Windows SharePoint Services
- scaling, hosts
- scaling, adapters
- SAP adapters
- FTP adapters
- scaling, receive adapters
- hosts, receiving
- adapters, Web services
- hosts, scaling
- SOAP adapters, scaling
- adapters, scaling
- SQL adapters, scaling
- Web services, adapters
- File adapters, scaling
- clustering
ms.assetid: 94f35426-37fa-4ad2-8e35-d82fdca02262
caps.latest.revision: "54"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b9bc048de978a6dfd7c28505c54cdaaaef64064
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="scaled-out-receiving-hosts"></a>Hosts de recepción escalados
Cuando un host contiene un elemento de recepción, como una canalización o una ubicación de recepción, actúa como un límite de seguridad y la descodificación y descifrado de mensajes tiene lugar en una canalización del host. Para lograr que la disponibilidad de los hosts de recepción sea muy alta, debe disponer de dos o más equipos con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que ejecuten instancias de cada host de recepción. Mediante el escalado horizontal de los hosts de recepción garantiza la disponibilidad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] las implementaciones que son de uso intensivo de mensajería. Si bien estas implementaciones llevan a cabo un procesamiento mínimo de orquestación, pueden enrutar muchos mensajes de varios tipos a gran velocidad y con gran confiabilidad.  
  
 Puede mejorar la seguridad y escalabilidad del entorno separando el host de recepción de los hosts que procesan orquestaciones y envían mensajes, porque puede proteger y escalar cada host de forma independiente de otros hosts. Por ejemplo, puede agregar dos equipos (instancias de host) al host de recepción sin agregar ningún equipo a los hosts de procesamiento o envío.  
  
## <a name="multiple-hosts-for-receiving-messages"></a>Varios hosts para recibir mensajes  
 La siguiente ilustración muestra un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementación que proporciona alta disponibilidad al host de recepción gracias a dos equipos que ejecutan instancias de host de recepción. Tenga en cuenta que, en esta ilustración, los hosts de procesamiento y envío no tienen una alta disponibilidad.  
  
 ![Host múltiple para recibir los mensajes](../core/media/tdi-ha-scalereceive.gif "TDI_HA_ScaleReceive")  
  
 Para implementaciones de gran tamaño, escenarios con varios asociados comerciales y escenarios en los que se utilizan diferentes protocolos, puede repartir la funcionalidad de recepción entre varios hosts de recepción. Por ejemplo, puede crear un host para recibir mensajes para cada adaptador, o diferentes hosts para recibir mensajes de asociados diferentes. Cuando se crean varios hosts de recepción, se pueden crear límites de seguridad y facilitar el uso y la escalabilidad del entorno; sin embargo, no se logra una alta disponibilidad del entorno.  
  
 Para lograr una alta disponibilidad del entorno, debe crear dos o más instancias de host para cada host de recepción que cree. Por ejemplo, puede crear tres hosts de recepción diferentes (A, B y C) para recibir mensajes de tres compañías diferentes. Para lograr que estos hosts tengan una alta disponibilidad, debe crear instancias de host de cada uno de los hosts en dos o más equipos. Tenga en cuenta que puede tener instancias de cada host en un equipo sin perder el límite de seguridad, la facilidad de uso o la escalabilidad.  
  
 La siguiente ilustración muestra un entorno BizTalk Server de tres equipos y una alta disponibilidad con hosts dedicados a recibir mensajes de diferentes compañías.  
  
 ![Instancias de recepción](../core/media/tdi-ha-receiveinstances2.gif "TDI_HA_ReceiveInstances2")  
  
 Para proporcionar alta disponibilidad en esta configuración, cada equipo ejecuta tres instancias de host: una instancia para cada una de las tres compañías. Las instancias de host de cada compañía contienen las canalizaciones y ubicaciones de recepción para comunicarse con esa compañía. Durante un funcionamiento normal, siempre que se haya realizado el trabajo necesario para escalar los adaptadores de recepción (por ejemplo, si configura el equilibrio de carga de red para HTTP), la carga de mensajería se distribuye entre las tres instancias de cada host. Si una instancia de host en un equipo da error, las instancias de host que se ejecutan en los otros dos equipos proporcionan redundancia y mantienen la disponibilidad del servicio.  
  
## <a name="scaling-the-biztalk-server-receive-adapters"></a>Escala de adaptadores de recepción de BizTalk Server  
 Además de las instancias de host, el proceso de escalar y proporcionar alta disponibilidad a los hosts de recepción depende también de los adaptadores específicos que implemente. Cada adaptador tiene características específicas del protocolo que hacen que el planeamiento y la implementación sean diferentes en cada caso. Sin embargo, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] le permite aplicar la misma solución de alta disponibilidad para todos los adaptadores, principalmente a través de otros equipos e instancias de host.  
  
 Dependiendo del protocolo específico que se utilice, algunos adaptadores de recepción requieren un mecanismo adicional para distribuir los mensajes entrantes entre varios equipos host con el fin de proporcionar una alta disponibilidad. Por ejemplo, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] soluciones que utilizan el adaptador HTTP o SOAP (también conocido como el adaptador de servicios Web) requieren un equilibrador de carga como red equilibrio de carga (NLB) para distribuir la carga de trabajo de recepción. La tabla siguiente resume las directrices de alta disponibilidad para los adaptadores más comunes en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
|**Adaptador**|**Directrices de alta disponibilidad**|  
|-----------------|---------------------------------------|  
|HTTP|Agregar varios equipos al host de recepción y configurar NLB para distribuir los mensajes entrantes entre los diferentes equipos host.|  
|SOAP|Agregar varios equipos al host de recepción y configurar NLB para distribuir los mensajes entrantes entre los diferentes equipos host.|  
|Archivo|Agregar varios equipos al host de recepción con la ubicación de recepción en cada equipo host haciendo referencia a la misma carpeta de archivos o ruta de acceso UNC (Convención de nomenclatura universal). Para lograr una solución de alta disponibilidad completa, debe asegurarse de que la ubicación de archivos a la que hace referencia la ruta de acceso UNC tenga una alta disponibilidad (o que sea al menos confiable).|  
|FTP|Configurar el adaptador de recepción FTP para ejecutarlo en un host de BizTalk agrupado. Para obtener más información, consulte [consideraciones para ejecutar controladores de adaptador dentro de un Host en clúster](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).|  
|POP3|Configurar el adaptador de recepción POP3 para ejecutarlo en un host de BizTalk agrupado. Para obtener más información, consulte [consideraciones para ejecutar controladores de adaptador dentro de un Host en clúster](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).|  
|MSMQ|Configurar el MSMQ para el adaptador de recepción para ejecutarse en un host de BizTalk en clúster de Windows. Para obtener más información, consulte [consideraciones para ejecutar controladores de adaptador dentro de un Host en clúster](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md). Si la recepción de MSMQ ubicaciones usa las colas en un MSMQ server remoto, no es necesario incluir en el clúster el host de BizTalk.  En este escenario, ejecute MSMQ host en varios equipos de BizTalk en el grupo de recepción.|  
|MQSeries|Agregar varios equipos al host de recepción para este adaptador, utilizar administradores de cola agrupados en MQSeries para Windows y agrupar el servidor MQSeries Server para Windows.|  
|Windows SharePoint Services|Agregar varios equipos al host de recepción y configurar NLB para distribuir los mensajes entrantes entre los diferentes equipos host.|  
|-WCF-NetTcp<br />-WCF-Custom|Agregar varios equipos al host de recepción y configurar NLB para distribuir los mensajes entrantes entre estos equipos host.<br /><br /> - o bien-<br /><br /> Clúster que usó el host mediante el controlador de recepción del adaptador.|  
|-WCF-NetNamedPipe<br />-WCF-BasicHttp<br />-WCF-WSHttp<br />-WCF-CustomIsolated|Agregar varios equipos al host de recepción y configurar NLB para distribuir los mensajes entrantes entre estos equipos host.|  
|WCF-NetMsmq|Clúster que usó el host mediante el controlador de recepción del adaptador.|  
  
### <a name="http-adapter"></a>Adaptador de HTTP  
 Adaptador de recepción de HTTP [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es una extensión de Internet Server API (ISAPI) (BTSHTTPReceive.dll) que se ejecuta como una instancia de host en cada equipo de host de recepción. Cuando un asociado envía un mensaje a BizTalk Server utilizando el protocolo HTTP, el mensaje suele llegar a una dirección URL específica en el equipo con BizTalk Server que tiene instalado Internet Information Services (IIS). Cree una instancia de host en BizTalk Server con una ubicación de recepción suscrita a esta dirección URL. Cuando llegan los mensajes a la dirección URL, BizTalk Server los recupera y los envía a la base de datos de cuadro de mensajes.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Proporciona alta disponibilidad para el HTTP permitiendo crear varias instancias de host del mismo host de recepción del adaptador de recepción. Estas instancias de host están suscritas a una dirección URL específica que puede ser una dirección IP de clúster compartida si utiliza NLB para distribuir los mensajes entrantes entre varios hosts de recepción. Estos hosts sirven a la dirección IP virtual del clúster, de manera que, si da error un miembro del clúster, los demás pueden continuar sirviendo a esta dirección IP.  
  
### <a name="soap-adapter-web-services-adapter"></a>Adaptador de SOAP (adaptador de servicios web)  
 A diferencia del adaptador de recepción HTTP, el adaptador de recepción para servicios Web no implica una extensión ISAPI. Recibe los mensajes entrantes a través de una dirección URL que especifique utilizando el Asistente para publicación de servicios Web de BizTalk. Este asistente exporta un servicio Web y crea un directorio virtual que funciona como ubicación de recepción.  
  
 Para proporcionar una alta disponibilidad al adaptador de servicios Web, agregue varios equipos al host de recepción y utilice NLB para distribuir los mensajes entrantes. Cuando un cliente envía un mensaje a BizTalk Server a través del adaptador de servicios Web, NLB mantiene el equilibrio de carga enviando el mensaje a uno de los hosts de recepción y la instancia de host correspondiente que se ejecuta en el host envía el mensaje a la base de datos de cuadro de mensajes.  
  
### <a name="file-adapter"></a>adaptador de archivo  
 El adaptador de recepción de archivo recupera los mensajes de una carpeta de archivos o una ruta de acceso UNC. Este adaptador se utiliza con frecuencia dentro de compañías en lugar de escenarios de empresa a empresa, porque ambas partes requieren permisos para la ruta y las compañías no suelen compartir los sistemas de archivos. Debe configurar el controlador de recepción de archivos para suscribirlo a la ruta de acceso de forma que BizTalk Server recupere el mensaje cuando llega a la ubicación de recepción.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Proporciona alta disponibilidad para el archivo de adaptador de recepción que le permite crear instancias de host en varios equipos host que se suscriben a la misma ruta de acceso UNC. Si una instancia de host que se ejecute en un equipo host encuentra errores, la misma instancia de host que se ejecute en otro equipo host puede recuperar el mensaje y enviarlo a la base de datos de cuadro de mensajes.  
  
### <a name="ftp-adapter"></a>Adaptador de FTP  
 El adaptador de recepción FTP no debe estar configurado para ejecutarse en varios hosts, porque este adaptador utiliza el protocolo FTP para recuperar archivos del sistema de destino y este protocolo no tiene ninguna noción de bloqueo de archivos para garantizar que no se recuperan varias copias del mismo archivo simultáneamente cuando se ejecutan varias instancias del adaptador de recepción FTP. Este adaptador debe configurarse para ejecutarlo en un host de BizTalk agrupado. Para obtener más información, consulte [consideraciones para ejecutar controladores de adaptador dentro de un Host en clúster](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).  
  
### <a name="pop3-adapter"></a>Adaptador de POP3  
 El adaptador de recepción POP3 se puede configurar para ejecutarlo en varios hosts a menos que el servidor POP3 del que lee el adaptador permita varias conexiones concurrentes al mismo buzón. Si el servidor POP3 al que está conectado el adaptador de POP3 permite varias conexiones concurrentes a los buzones, la alta disponibilidad del adaptador de POP3 se logra configurando los controladores de recepción del adaptador de POP3 para ejecutarlos en una instancia de host de BizTalk que se haya agrupado. Para obtener más información, consulte [consideraciones para ejecutar controladores de adaptador dentro de un Host en clúster](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).  
  
### <a name="msmq-adapter"></a>Adaptador de MSMQ  
 Para lograr una alta disponibilidad, ejecutar el MSMQ para el adaptador de recepción en un host de BizTalk en clúster de Windows que se encuentra en el mismo grupo de clústeres que el recurso MSMQ agrupado. Para obtener más información, consulte [consideraciones para ejecutar controladores de adaptador dentro de un Host en clúster](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).  
  
 Si la ubicación de recepción de MSMQ es **sólo** recibir desde las colas MSMQ de un MSMQ server remoto, a continuación, se puede conseguir alta disponibilidad mediante la ejecución de MSMQ de recepción host en varios equipos de BizTalk del grupo de BizTalk.  Para proporcionar alta disponibilidad para MSMQ, debe asegurarse que el servidor MSMQ remoto está usando la conmutación por error de Windows.  Si usa las colas transaccionales, el servidor MSMQ remoto debe ejecutar MSMQ 4.0 (Windows Server 2008) o superior.  
  
### <a name="mqseries-adapter"></a>Adaptador de MQSeries  
 El adaptador de Microsoft BizTalk para MQSeries actúa como puente entre [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y servidores IBM MQSeries Server. Para proporcionar una solución de alta disponibilidad cuando utilice este adaptador, debe tener varias instancias del host que ejecuta el adaptador de MQSeries, utilizar administradores de cola agrupados en MQSeries para Windows y agrupar el servidor MQSeries Server para Windows. Para obtener más información acerca de la agrupación en clúster del administrador de cola y del servidor MQSeries Server, consulte la documentación de IBM WebSphere MQ. Para obtener más información sobre cómo lograr alta disponibilidad para el adaptador de MQSeries, consulte "Alta disponibilidad" en la Ayuda del adaptador de Microsoft BizTalk para MQSeries.  
  
### <a name="windows-sharepoint-services-adapter"></a>Adaptador de Windows SharePoint Services  
 El adaptador de Windows SharePoint Services recupera mensajes de SharePoint llamando al servicio Web de Windows SharePoint Services instalado por BizTalk en el equipo con SharePoint. El adaptador utiliza un mecanismo de desprotección para garantizar que varias instancias de host no procesarán el mismo mensaje. Esto permite que el adaptador de recepción escalar horizontalmente mediante la adición de más instancias de host. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Proporciona alta disponibilidad para el adaptador de recepción de SharePoint que le permite ejecutar la misma ubicaciones de recepción en varias instancias de host que se suscriben a la misma dirección URL de HTTP que apunta a una instalación de NLB de SharePoint.  
  
### <a name="wcf-nettcp-adapter"></a>Adaptador de WCF-NetTcp  
 Se puede equilibrar la carga de NetTcpBinding mediante técnicas de equilibrio de carga de capa IP. Sin embargo, NetTcpBinding agrupa conexiones TCP de forma predeterminada para reducir la latencia de la conexión. Esto es una optimización que interfiere con el mecanismo básico de equilibrio de carga. El valor de configuración principal para optimizar NetTcpBinding es el tiempo de espera de conexión, que forma parte de la configuración del grupo de conexión. La agrupación de conexiones hace que las conexiones de cliente se asocien a servidores específicos dentro de la granja. A medida que la duración de estas conexiones aumenta (un factor controlado por la configuración de tiempo de espera de concesión), la distribución de la carga entre los distintos servidores de la granja se desequilibra. Como resultado aumenta el tiempo promedio de la llamada. Por lo tanto, cuando se usa NetTcpBinding en escenarios con la carga equilibrada, considere la posibilidad de reducir el tiempo de espera de concesión predeterminado usado por el enlace. Un tiempo de espera de concesión de 30 segundos es un punto de inicio razonable para escenarios con la carga equilibrada, aunque el valor óptimo depende de la aplicación. Para obtener más información sobre el tiempo de espera de concesión de canal y otras cuotas de transporte, consulte las cuotas de transporte.  
  
## <a name="see-also"></a>Vea también  
 [Proporcionar alta disponibilidad a hosts de BizTalk](../core/providing-high-availability-for-biztalk-hosts.md)