---
title: "Planeación para enviar y recibir | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d67e5f7-5127-4c1d-be20-8d8dbb538286
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca2b87964266b77629f7fa1d1156ace3cd048e7f
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="planning-for-sending-and-receiving"></a>Planeación para enviar y recibir
Casi todos los documentos que es procesado por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adaptador de recepción y se envían desde [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mediante un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] del adaptador de envío. Dado que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adaptadores de ilustración, por lo que de forma destacada en cualquier [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno, es importante planificar con antelación determinar qué adaptadores o aceleradores va a usar y cómo configurar correctamente estos adaptadores o aceleradores.  
  
## <a name="determining-which-adapters-and-accelerators-you-will-use"></a>Determinar qué adaptadores y aceleradores que se va a usar  
 Confiere a los socios comerciales de antemano para determinar qué adaptadores y aceleradores deberá facilitar enviar y recibir documentos entre su organización y sus socios comerciales y entre las aplicaciones de BizTalk y su propia aplicaciones de negocio. Diseño su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] partners de la arquitectura para ser lo suficientemente flexible como para dar cabida a agregar otros adaptadores o aceleradores en caso de que establecer relaciones con comerciales adicionales en el futuro.  
  
## <a name="functionality-supported-by-biztalk-adapters"></a>Funcionalidad compatible con los adaptadores de BizTalk  
 La tabla de esta sección enumera la ventaja principal de cada adaptador nativo y si el adaptador proporciona las siguientes características:  
  
-   **Compatibilidad con transacciones** la capacidad de enviar y recibir documentos en el contexto de una transacción de DTC (Coordinador) de la transacción distribuida. Esta funcionalidad es necesaria para mantener una entrega ordenada de mensajes y garantizar que los documentos no se duplican ni se pierden.  
  
    > [!NOTE]  
    >  Si tiene problemas con MSDTC, vea el tema [solución de problemas con MSDTC](http://go.microsoft.com/fwlink/?LinkID=154693) (http://go.microsoft.com/fwlink/?LinkID=154693).  
  
-   **Compatibilidad con comunicación bidireccional (solicitud/respuesta o petición-respuesta)** la capacidad para enviar un documento y procesar un mensaje de respuesta de destino o para recibir un documento y enviar un mensaje de respuesta al origen.  
  
-   **Compatibilidad con recepción por orden.** La capacidad para publicar documentos recibidos en la base de datos de cuadro de mensajes en el orden exacto en que se recibieron los documentos.  
  
    > [!NOTE]  
    >  Determinados adaptadores pueden exigir entrega ordenada de documento en el nivel de ubicación de recepción, mientras que otros adaptadores no. Entrega ordenada todavía se puede aplicar en el nivel de puerto de envío para esos adaptadores que no admiten la entrega del documento en el nivel de la ubicación de recepción ordenada, pero al hacerlo por lo que puede suponer una reducción del rendimiento. Para obtener más información sobre la entrega ordenada de mensajes, vea el tema [ordenada de mensajes de entrega](http://go.microsoft.com/fwlink/?LinkId=155751) (http://go.microsoft.com/fwlink/?LinkId=155751).  
  
-   **Compatibilidad con SSO.** Capacidad para usar autenticación de SSO cuando se envían o reciben documentos con el adaptador.  
  
|Adaptador|Principales ventajas|Compatibilidad con transacciones|Compatibilidad con comunicación bidireccional|Compatibilidad con recepción por orden|Compatibilidad con SSO|  
|-------------|---------------------|-------------------------|------------------------------------|-------------------------------|-----------------|  
|Archivo|Fácil de usar|no|No|No|no|  
|FTP|Se usa ampliamente para comunicaciones de negocio a negocio|no|No|No|Sí|  
|HTTP(s)|Se usa ampliamente para comunicaciones de negocio a negocio|no|Solicitud - respuesta y petición - respuesta|no|Sí|  
|SOAP|Admite el uso de servicios Web|no|Solicitud - respuesta y petición - respuesta|no|Sí|  
|MSMQ|Admite una sola vez entrega garantizada de mensajes entre BizTalk Server y Microsoft Message Queue Server|Sí|No|Sí|no|  
|MQ Series|Admite una sola vez entrega garantizada de mensajes entre BizTalk Server e IBM WebSphere MQ para plataformas de Windows|Sí|No|Sí|Sí|  
|SQL|Admite comunicación directa entre las bases de datos de BizTalk Server y SQL Server|Sí|Sólo petición - respuesta|no|no|  
|Windows SharePoint Services|Permite el intercambio de mensajes XML y binarios entre BizTalk Server y las bibliotecas de documentos de SharePoint|no|No|No|no|  
|POP3|Admite la recepción de documentos por correo electrónico|no|No|No|no|  
|SMTP|Admite el envío de documentos por correo electrónico|no|No|No|no|  
|ENRUTAMIENTO|Admite el procesamiento de documentos empresariales que se ajusta al estándar EDI|no|No|No|no|  
|Personalizado|Es compatible con el sistema heredado|Sí, requiere código personalizado.|Sí, requiere código personalizado.|Sí, requiere código personalizado.|Sí, requiere código personalizado.|  
|WCF-WSHttp|Es compatible con WS-* estándares mediante el transporte HTTP|Sí, las transacciones se admiten en WsHTTP (sólo las transacciones WS)|Solicitud - respuesta y petición - respuesta|no|Sí|  
|WCF-BasicHttp|Se comunica con servicios Web basados en ASMX y clientes y otros servicios que cumplan con WS-I Basic Profile 1.1 mediante HTTP o HTTPS|no|Solicitud - respuesta y petición - respuesta|no|Sí|  
|WCF-NetTcp|Es compatible con WS-* estándares a través del transporte TCP|Sí|Solicitud - respuesta y petición - respuesta|no|Sí|  
|WCF-NetMsmq|Permite poner en cola aprovechando Microsoft Message Queuing (MSMQ) como transporte|Sí|No|Sí|Sí|  
|WCF-NetNamedPipe|Proporciona un transporte rápido para la comunicación entre procesos en el mismo equipo (sólo para aplicaciones WCF)|Sí|Solicitud - respuesta y petición - respuesta|no|Sí|  
|WCF-Custom|Habilita el uso de características de extensibilidad WCF|Sí.|Sí.|Sí, siempre que lo admita el enlace.|Sí.|  
|WCF-CustomIsolated|Habilita el uso de características de extensibilidad WCF mediante el transporte HTTP|Sí.|Sí.|No.|Sí.|  
  
## <a name="line-of-business-adapters"></a>Línea de adaptadores empresariales  
 A continuación se muestra una lista de los adaptadores para línea empresarial (LOB) que proporciona Microsoft.  
  
> [!NOTE]  
>  Con la excepción de la Microsoft BizTalk Adapter v2.0 para mySAP™ Business Suite (el adaptador), ninguno de los adaptadores de línea de negocio se admiten en Windows Vista.  
  
|Adaptador|Description|Versiones admitidas|  
|-------------|-----------------|------------------------|  
|SAP (también denominada "adaptador")|Habilita el intercambio de documentos intermedios (IDOC), BAPI y mensajes de llamada (RFC) de una función remota entre BizTalk Server y un sistema SAP R/3®.|SAP R/3 4.x y R/3 6.20 (empresas)|  
|PeopleSoft Enterprise|Habilita el intercambio de mensajes de interfaz de componentes entre el servidor BizTalk Server y un sistema PeopleSoft.|PeopleTools Versiones 8.17.02, 8.43, 8.45, 8.46 y 8.48|  
|JD Edwards OneWorld XE|Habilita el intercambio de mensajes de funciones empresariales entre el servidor BizTalk Server y un sistema JD Edwards OneWorld.|B7.3.3.3 con SP23 y JDE 8.0 (B7.3.3.4)|  
|JD Edwards EnterpriseOne|Habilita el intercambio de mensajes de funciones empresariales entre el servidor BizTalk Server y un sistema EnterpriseOne.|8.10 & 8.11 con Tools Release 8.93, 8.94, 8.95 y 8.96|  
|Adaptador ODBC para bases de datos de Oracle|Habilita la lectura y la escritura de información de y en la base de datos de un servidor Oracle.|Oracle 8i (8.1.6.0), 9i (9.2.0.1), o 10g|  
|Aplicaciones Siebel eBusiness|Habilita el intercambio de mensajes de servicios empresariales y componentes empresariales entre el servidor BizTalk Server y una aplicación Siebel eBusiness.|7.0 y 7.5. *, 7.7. \*y 7.8.\*|  
|TIBCO Rendezvous|Habilita el intercambio de mensajes con formato de datos XML y binarios entre el servidor BizTalk Server y TIBCO Rendezvous.|7.3|  
|TIBCO Enterprise Message Service|Habilita el intercambio de mensajes con formato de datos XML y binarios entre el servidor BizTalk Server y un servidor TIBCO EMS proporcionando una infraestructura de aplicación de confianza y estrechamente integrada.|4.2|  
|WebSphere MQ|Habilita el intercambio de mensajes entre el servidor BizTalk Server e IBM WebSphere MQ.|5.3 con Fix Pack 10 o posterior y 6.0 con Fix Pack 1.1 o posterior|  
  
 Para obtener más información acerca de los adaptadores LOB disponibles con BizTalk Server, vea [adaptadores incluidos con BizTalk Server 2010](http://go.microsoft.com/fwlink/?LinkId=152664) (http://go.microsoft.com/fwlink/?LinkId=152664).  
  
## <a name="biztalk-adapter-pack"></a>BizTalk Adapter Pack  
 Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] contiene adaptadores basados en WCF para proporcionar conectividad a las aplicaciones de LOB, como la base de datos Oracle, Oracle E-Business Suite, SAP, Siebel y SQL Server. Para obtener una lista de adaptadores disponibles con [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], consulte [BizTalk Adapter Pack](http://go.microsoft.com/fwlink/?LinkId=152665) (http://go.microsoft.com/fwlink/?LinkId=152665).  
  
> [!IMPORTANT]  
>  Puede usar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] herramienta de migración para migrar los proyectos de BizTalk para adaptadores LOB a los proyectos de BizTalk para adaptadores basados en WCF LOB disponibles con la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]. Puede descargar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] herramienta de migración de [herramienta de migración de módulo de adaptador de BizTalk](http://go.microsoft.com/fwlink/?LinkID=153328) (http://go.microsoft.com/fwlink/?LinkID=153328). Para obtener más información acerca de los adaptadores LOB migrar a adaptadores basados en WCF LOB incluidos con el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], consulte el [notas sobre la migración de Microsoft BizTalk adaptador 2.0](http://go.microsoft.com/fwlink/?LinkId=158848) (http://go.microsoft.com/fwlink/?LinkId=158848).  
  
## <a name="biztalk-accelerators"></a>Aceleradores de BizTalk  
 Mientras que los adaptadores de BizTalk trabajar con documentos de envío y recepción con un protocolo determinado, aceleradores de BizTalk están diseñados para albergar el intercambio de documentos de acuerdo con un estándar del sector determinado. Para obtener una lista de los aceleradores de BizTalk disponibles, consulte [Acelerador de Microsoft BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=103609) (http://go.microsoft.com/fwlink/?LinkId=103609).  
  
##  <a name="BKMK_InternetTrans"></a>Configurar el dominio al exponer transportes a Internet  
 Para facilitar el envío y recepción de documentos entre su organización y los socios comerciales externos, puede ser necesario exponer los transportes en un sitio orientados al público que sea accesible desde Internet. En estos casos, se recomienda la configuración de dominio siguientes:  
  
-   **Emplear un dominio de red perimetral (también conocida como zona desmilitarizada (DMZ) o subred filtrada) a servidores de enrutamiento para proporcionar Internet relacionadas con servicios para su organización**  
  
     El dominio de red perimetral debe contener los servidores que alojan las ubicaciones físicas donde transportes orientados a Internet enrutan documentos entre equipos que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y sus socios comerciales. El servidor de seguridad de la red perimetral sólo debe abrir los puertos necesarios para permitir la comunicación hacia y desde Internet con conexión a los transportes. No debería haber ningún equipos que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ubicaciones de recepción ni equipos Enterprise Single Sign-On server en el dominio de la red perimetral. Se deberían enrutar documentos enviados o recibidos de transportes en el dominio de red perimetral del Firewall de conexión a Internet al firewall que protege el dominio de procesamiento con Internet Security and Acceleration Server (ISA) Server Web Publishing y Publicación de servidor. Para obtener más información sobre el uso de Web del servidor ISA y el servidor de publicación, vea [conceptos de publicación en ISA Server 2006](http://go.microsoft.com/fwlink/?LinkID=86359) (http://go.microsoft.com/fwlink/?LinkID=86359).  
  
    > [!NOTE]  
    >  Documentar a medida que una medida adicional de seguridad, considere el uso de certificados digitales de infraestructura de clave pública (PKI) para los fines de cifrado y descifrado, firma y comprobación (sin repudio) para los documentos enviados o recibidos de los comerciales socios comerciales a través de Internet con conexión a los transportes de este dominio.  
  
     Los siguientes transportes utilizan normalmente en el dominio de red perimetral que sea accesible desde Internet:  
  
    -   FTP: para recibir documentos mediante el protocolo FTP  
  
    -   SMTP - para enviar documentos mediante el protocolo SMTP  
  
    -   HTTP - para recibir documentos mediante el protocolo HTTP  
  
    -   SOAP - para recibir documentos mediante SOAP  
  
    -   POP3 - para recibir documentos mediante el protocolo POP3  
  
-   **Emplear un dominio de procesamiento para alojar servidores que contienen el servidor BizTalk Server reciban y envían controladores y un servidor del portal de BAM**  
  
     Flujo de documentos entre los transportes con orientación externos en el dominio perimetral y adaptadores de BizTalk en el dominio de procesamiento debe enrutarse a través de un firewall entre estos dominios. El dominio de procesamiento debe alojar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puertos, ubicaciones de recepción, canalizaciones, asignaciones, esquemas y ensamblados que se utiliza para recibir, enrutar y enviar mensajes. El dominio de procesamiento también debe contener los servidores del portal de BAM. El número de equipos que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el dominio de procesamiento dependerán del número de hosts y alojar instancias necesarios para satisfacer las necesidades de rendimiento de su organización.  
  
    > [!IMPORTANT]  
    >  Asegúrese de que crea instancias de host aislado suficientes en el dominio de procesamiento para dar cabida a tráfico que fluye entre los transportes HTTP y SOAP en el dominio de perímetro y los adaptadores HTTP y SOAP en el dominio de procesamiento. Si una gran parte del tráfico entre su organización y sus socios comerciales documento fluye a través de los transportes HTTP y SOAP, debe haber suficiente ancho de banda de procesamiento en el dominio de procesamiento para controlar el flujo de documentos.  
  
-   **Emplear dominios adicionales para proporcionar más niveles de aislamiento y seguridad para su entorno**  
  
     Deben incluir estos dominios:  
  
    -   Un dominio de servicios que es de confianza para el dominio de procesamiento y que es necesario para procesar los mensajes correctamente. Servidores en el dominio de servicios suelen ejecutan orquestaciones de BizTalk, canalizaciones, servicios de inicio de sesión único (SSO) empresarial, el motor de reglas de negocios y pueden incluir otros procesos empresariales.  
  
    -   Un dominio de datos para los equipos que ejecutan SQL Server utilizado por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
    -   Un dominio corporativo para servidores y equipos de escritorio para proporcionar servicios a los trabajadores de información de su organización.  
  
     Para obtener más información sobre las topologías de dominio que se recomienda para los distintos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] arquitecturas, consulte [arquitecturas de servidor de BizTalk de ejemplo](http://go.microsoft.com/fwlink/?LinkId=155750) (http://go.microsoft.com/fwlink/?LinkId=155750).  
  
## <a name="high-availability-considerations"></a>Consideraciones sobre alta disponibilidad  
 Puede proporcionar alta disponibilidad para la mayoría de los adaptadores mediante la ejecución de instancias de host de controlador de adaptador en varios servidores de BizTalk en un grupo de BizTalk. De este modo, si se produce un error en una instancia de host de controlador de adaptador, otra instancia de host de controlador de adaptador está disponible para seguir procesándose. Sin embargo, hay excepciones a esto. En algunos casos ejecuta el adaptador de varias instancias de host de controlador puede causar problemas con la contención. Por ejemplo pueden producirse problemas de contención al ejecutar varias instancias de los adaptadores de POP3 y FTP. En estas circunstancias, puede proporcionar alta disponibilidad para el adaptador mediante la ejecución de la instancia de host de controlador de adaptador en un host de BizTalk.  
  
 Para obtener más información acerca de cómo proporcionar alta disponibilidad para una instancia de host de controlador de adaptador a través de clústeres de host, consulte [consideraciones para ejecutar controladores de adaptador dentro de un Host en clúster](http://go.microsoft.com/fwlink/?LinkID=151284) (http://go.microsoft.com/fwlink/?LinkID=151284). Para obtener más información acerca de cómo proporcionar alta disponibilidad para los hosts de BizTalk, consulte [alta disponibilidad para los Hosts de BizTalk](../technical-guides/high-availability-for-biztalk-hosts.md).  
  
## <a name="performance-considerations"></a>Consideraciones de rendimiento  
 **Consideraciones de rendimiento del adaptador SOAP**  
  
 Para obtener información acerca de cómo optimizar el rendimiento del adaptador de SOAP, vea [parámetros de configuración que afectan al rendimiento del adaptador](http://go.microsoft.com/fwlink/?LinkID=154200) (http://go.microsoft.com/fwlink/?LinkID=154200).  
  
 **Consideraciones de rendimiento del adaptador de MQSeries**  
  
 **Deshabilite la compatibilidad con transacciones y entrega ordenada si no es necesario para MQSeries de ubicaciones de recepción del adaptador** cuando recibe un adaptador de MQSeries ubicación se configura con el **admite transacción** opción establecida en  **Sí**, o la **ordenados** opción establecida en **orden con pausa**, a continuación, cada mensaje recogido la ubicación de recepción se procesarán en el contexto de un Microsoft Distributed Transacción de Transaction Coordinator (MSDTC). Porque no hay más sobrecarga que se produce al procesar los mensajes en el contexto de una transacción MSDTC, estas opciones no se deberían habilitar si entrega ordenada o compatibilidad con transacciones no se requiere para MQSeries adaptador de ubicación de recepción.  
  
## <a name="planning-for-ordered-message-delivery"></a>Planeación de entrega ordenada de mensajes  
 Entrega ordenada de mensajes garantiza que los mensajes que se publican en la base de datos de cuadro de mensajes en un orden determinado se entreguen a los suscriptores correspondientes en el mismo orden. Se aplican las consideraciones siguientes al implementar la entrega ordenada de mensajes:  
  
 **Configuración de entrega ordenada de mensajes**  
  
 La entrega ordenada de mensajes se puede configurar en los siguiente lugares:  
  
-   Forma Recepción de una orquestación  
  
-   Ubicación de determinados adaptadores de recepción  
  
-   Puerto de envío  
  
 **Entrega ordenada con transportes existentes**  
  
 Los protocolos empleados en determinados transportes, como ARCHIVO y HTTP, no son coherentes con la noción de entrega ordenada. Sin embargo, incluso con este tipo de transportes, si el puerto enlazado con el transporte está marcado para entrega ordenada, BizTalk Server aplica la característica de entrega ordenada y, de este modo, garantiza que el transporte no obtenga el siguiente mensaje de salida hasta que no se haya enviado correctamente el actual. Para lograr esto, BizTalk Server pasa cada mensaje al adaptador del transporte en un único lote y espera hasta que el adaptador ha eliminado correctamente el mensaje de la base de datos de cuadro de mensajes antes de entregar el mensaje siguiente, en otro lote al adaptador.  
  
 **Entrega ordenada con adaptadores personalizados**  
  
 Adaptador para conservar el orden de mensajes cuando se envíen al servidor BizTalk Server de recepción para un personalizado, el adaptador debe haber sido desarrollado con la siguiente funcionalidad:  
  
-   Después de enviar un lote de mensajes, de recepción personalizada de su adaptador debe esperar la llamada BatchComplete desde BizTalk Server antes de enviar el siguiente lote. Para obtener más información, consulte [Interfaces para un adaptador de recepción de Batch-Supported](http://go.microsoft.com/fwlink/?LinkId=155752) (http://go.microsoft.com/fwlink/?LinkId=155752).  
  
-   Si se produce un error en un mensaje en la canalización, se debe suspender, preferiblemente como no reanudables. Utilice el BTS. Propiedad de contexto de mensaje SuspendAsNonResumable en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para marcar el mensaje correctamente.  
  
    > [!NOTE]  
    >  El orden de los mensajes se puede interrumpir si un mensaje suspendido se reanuda después. Si no desea este comportamiento, suspender mensajes con errores como no reanudables.  
  
 **Condiciones para to-End ordenan el procesamiento de mensajes**  
  
 Para proporcionar una entrega ordenada de extremo a extremo, deben cumplirse las siguientes condiciones:  
  
-   Los mensajes se tienen que recibir con un adaptador que conserve el orden de los mensajes cuando se envíen al servidor BizTalk Server. En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], ejemplos de estos adaptadores son MSMQ y MQSeries. Además, se pueden usar adaptadores HTTP o SOAP para enviar los mensajes de manera ordenada, aunque en ese caso el cliente HTTP o SOAP necesita aplicar el orden al enviar los mensajes de uno en uno.  
  
-   Debe suscribirse a estos mensajes con un puerto de envío que tiene la **entrega ordenada** opción establecida en **True**.  
  
-   Si una orquestación se utiliza para procesar los mensajes, una sola instancia de la orquestación deben usarse, la orquestación debe estar configurada para utilizar un convoy secuencial y la **entrega ordenada** propiedad de la puerto de recepción de la orquestación debe establecerse en **True**.  
  
## <a name="see-also"></a>Vea también  
 [Planificación del entorno de BizTalk Server](../technical-guides/planning-the-environment-for-biztalk-server.md)