---
title: Adaptadores de BizTalk Server | Documentos de Microsoft
description: Lista completa de todos los adaptadores disponibles en BizTalk Server, incluidos los adaptadores integrados y adaptadores empresariales, BizTalk Adapter Pack
ms.custom: ''
ms.date: 10/16/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8fd279fb-2c68-4de4-a586-5a8e42a685ff
caps.latest.revision: 48
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7834fe9f7365e9ed94bce82f353e1cd305a2863c
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "23450301"
---
# <a name="adapters-in-biztalk-server"></a>Adaptadores de BizTalk Server
Uno de los principales objetivos del diseño de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es facilitar el intercambio de documentos empresariales entre socios comerciales. Para contribuir a lograr este objetivo, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] incluye varios adaptadores que proporcionan conectividad entre BizTalk Server y socios comerciales mediante los protocolos de datos y formatos de documento comúnmente reconocidos. Este tema explica lo que es un adaptador y por qué se utiliza.  
  
## <a name="what-is-an-adapter"></a>¿Qué es un adaptador?  
 Un adaptador es un componente de software que permite enviar y recibir mensajes fácilmente en BizTalk Server con un mecanismo de entrega que cumple un estándar ampliamente reconocido, como SMTP, POP3, FTP o Microsoft Message Queue Server (MSMQ). Conforme Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ha ido evolucionando, ha aumentado la necesidad de adaptadores que habiliten con rapidez la conectividad con las aplicaciones y tecnologías más utilizadas.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] incluye los siguientes adaptadores, que se conocen como los adaptadores "nativos" o "integrados": archivo, FTP, HTTP, MQSeries, MSMQ, POP3, SMTP, SOAP, Windows Sharepoint Services y los siete adaptadores WCF (WCF-WSHttp, WCF-BasicHttp, WCF-NetTcp, WCF-NetMsmq, WCF-NetNamedPipe, WCF-Custom y WCF-CustomIsolated). Los adaptadores nativos se instalan con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. También es posible crear adaptadores personalizados para sus soluciones específicas mediante el marco de trabajo de adaptadores de BizTalk.  
  
 Cada uno de los adaptadores nativos está asociado con una ubicación de recepción diseñada para escuchar mensajes de un transporte específico en una dirección determinada. Una vez recibido el mensaje en la ubicación de recepción, se pasa al adaptador. El adaptador adjunta la secuencia de datos al mensaje (normalmente en el cuerpo del mensaje), agrega los metadatos que pertenecen al extremo del que se recibieron los datos y envía el mensaje al motor de mensajería de BizTalk.  
  
 De manera predeterminada, cuando se ejecuta el Asistente para configuración de BizTalk, el asistente instala los adaptadores nativos y crea un controlador de adaptador con una configuración predeterminada para cada uno.  
  
 Con la consola de administración de BizTalk Server puede modificar la configuración predeterminada de los controladores de adaptadores, así como agregar, quitar y modificar los puertos de envío y las ubicaciones de recepción de los adaptadores. Para obtener más información acerca de estos procesos, vea los temas correspondientes de la sección Vea también.  
  
## <a name="why-use-an-adapter"></a>¿Por qué usar un adaptador?  
 El uso de adaptadores simplifica notablemente la transferencia de mensajes con BizTalk Server. Si su infraestructura utiliza alguno de los transportes para los que hay un adaptador de BizTalk, el proceso de envío o recepción de mensajes de BizTalk Server es tan simple como configurar el adaptador correspondiente para enviar o recibir mensajes con el correspondiente mecanismo de transporte.  
  
## <a name="functionality-support-in-built-in-adapters"></a>Compatibilidad con la funcionalidad de adaptadores integrados  
 La tabla siguiente enumera la ventaja principal de cada adaptador nativo y si el adaptador proporciona las siguientes características:  
  
-   **Compatibilidad con transacciones** : la capacidad para enviar y recibir documentos en el contexto de una transacción de DTC (Coordinador) de la transacción distribuida. Esta funcionalidad es necesaria para mantener una entrega ordenada de mensajes y garantizar que los documentos no se duplican ni se pierden.  
  
-   **Compatibilidad con comunicación bidireccional (solicitud/respuesta o petición-respuesta)** : la capacidad para enviar un documento y procesar un mensaje de respuesta de destino o para recibir un documento y enviar un mensaje de respuesta al origen.  
  
-   **Compatibilidad con recepción por orden** : la capacidad para publicar documentos recibidos en la base de datos de BizTalk MessageBox en el orden exacto en que se recibieron los documentos.  
  
-   **Compatibilidad con SSO** : la capacidad para utilizar la autenticación de SSO al enviar o recibir documentos con el adaptador.  
  
-   **Proceso de alojamiento** : el proceso en el que se ejecuta el adaptador. *BizTalk IP* se ejecuta en el proceso BTSNTSvc.exe, mientras que *IIS OOP* ejecutar fuera del proceso de BizTalk Server en el proceso de Internet Information Server (IIS).  
  
|Adaptador|Ventaja principal|Compatibilidad con transacciones|Compatibilidad con comunicación bidireccional|Compatibilidad con recepción por orden|Compatibilidad con SSO|Proceso de alojamiento|  
|---|---|---|---|---|---|---|  
|Personalizado|Compatible con su sistema.|Sí, requiere código personalizado.|Sí, requiere código personalizado.|Sí, requiere código personalizado.|Sí, requiere código personalizado.|IP de BizTalk|  
|Archivo|Facilidad de uso.|no|No|No|no|IP de BizTalk|  
|FTP|Se usa ampliamente para comunicaciones de negocio a negocio.|no|No|No|Sí|IP de BizTalk|  
|HTTP(s)|Se usa ampliamente para comunicaciones de negocio a negocio.|no|Solicitud - respuesta y petición - respuesta|no|Sí|OOP de IIS|  
|MSMQ|Admite entrega de una sola vez garantizada de mensajes entre BizTalk Server y Microsoft Message Queue Server.|Sí|No|Sí|no|IP de BizTalk|  
|Aplicación lógica| Recibir de y enviar a una aplicación de lógica de Azure. Para local y la nube entornos, utilizar este adaptador para tener acceso a muchos servicios de Azure | Sí | Depende de su diseño de flujo de trabajo| | |De recepción: IP de BizTalk<br/>Envío: OOP de IIS| 
|MQ Series|Admite entrega de una sola vez garantizada de mensajes entre BizTalk Server e IBM WebSphere MQ para plataformas Windows.|Sí|No|Sí|Sí|IP de BizTalk|  
|POP3|Admite la recepción de documentos por correo electrónico.|no|No|No|no|IP de BizTalk|  
|SMTP|Admite el envío de documentos por correo electrónico.|no|No|No|no|IP de BizTalk|  
|SOAP|Admite el uso de servicios Web.|no|Solicitud - respuesta y petición - respuesta|no|Sí|OOP de IIS|  
|Windows SharePoint Services|Permite el intercambio de mensajes XML y binarios entre BizTalk Server y las bibliotecas de documentos de SharePoint.|no|No|No|no|IP de BizTalk| 
|WCF-WSHttp|Admite los estándares WS-* a través de transporte HTTP.|Sí, las transacciones se admiten en WsHTTP (sólo las transacciones WS)|Solicitud - respuesta y petición - respuesta|no|Sí|OOP de IIS|  
|WCF-BasicHttp|Se comunica con servicios y clientes web basados en ASMX y con otros servicios compatibles con el Perfil básico de servicios web WS-I, versión 1.1 mediante HTTP o HTTPS.|no|Solicitud - respuesta y petición - respuesta|no|Sí|OOP de IIS|  
|WCF-NetTcp|Admite los estándares WS-* a través de transporte TCP.|Sí|Solicitud - respuesta y petición - respuesta|no|Sí|IP de BizTalk|  
|WCF-NetMsmq|Admite las colas mediante la utilización de Microsoft Message Queue Server (MSMQ) como transporte.|Sí|No|Sí|Sí|IP de BizTalk|  
|WCF-NetNamedPipe|Ofrece un transporte rápido para comunicaciones entre procesos en el mismo equipo (sólo para aplicaciones WCF).|Sí|Solicitud - respuesta y petición - respuesta|no|Sí|IP de BizTalk|  
|WCF-Custom|permite el uso de características de extensibilidad de WCF.|Sí|Sí|Sí, siempre que lo admita el enlace.|Sí|IP de BizTalk|  
|WCF-CustomIsolated|permite el uso de características de extensibilidad de WCF a través del transporte HTTP.|Sí|Sí|No|Sí|OOP de IIS|  
  
## <a name="enterprise-adapters"></a>Adaptadores de Enterprise  
 A continuación se muestra una lista de los adaptadores para línea empresarial (LOB) que proporciona Microsoft.  
  
|Adaptador|Description|Versiones admitidas|  
|---|---|---|  
|PeopleSoft Enterprise|Habilita el intercambio de mensajes de interfaz de componentes entre el servidor BizTalk Server y un sistema PeopleSoft.|[Línea de negocio (LOB) y los sistemas empresariales compatibles](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)|  
|JD Edwards OneWorld XE|Habilita el intercambio de mensajes de funciones empresariales entre el servidor BizTalk Server y un sistema JD Edwards OneWorld.|[Línea de negocio (LOB) y los sistemas empresariales compatibles](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)|  
|JD Edwards EnterpriseOne|Habilita el intercambio de mensajes de funciones empresariales entre el servidor BizTalk Server y un sistema EnterpriseOne.|[Línea de negocio (LOB) y los sistemas empresariales compatibles](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)|  
|TIBCO Rendezvous|Habilita el intercambio de mensajes con formato de datos XML y binarios entre el servidor BizTalk Server y TIBCO Rendezvous.|[Línea de negocio (LOB) y los sistemas empresariales compatibles](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)|  
|TIBCO Enterprise Message Service|Habilita el intercambio de mensajes con formato de datos XML y binarios entre el servidor BizTalk Server y un servidor TIBCO EMS proporcionando una infraestructura de aplicación de confianza y estrechamente integrada.|[Línea de negocio (LOB) y los sistemas empresariales compatibles](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)|  

## <a name="biztalk-adapter-pack"></a>BizTalk Adapter Pack  
 También puede usar los adaptadores que se suministran con [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] para conectar con distintos sistemas de línea de negocio. Para obtener más información acerca de [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], consulte [BizTalk Adapter Pack](../adapters-and-accelerators/biztalk-adapter-pack.md).
  
## <a name="see-also"></a>Vea también  
 [Prácticas recomendadas para proteger los adaptadores](../core/best-practices-for-securing-adapters.md)   
 [Crear y eliminar controladores de adaptador](../core/creating-and-deleting-adapter-handlers.md)   
 [Implementación de Enterprise Single Sign-On](../core/implementing-enterprise-single-sign-on.md)