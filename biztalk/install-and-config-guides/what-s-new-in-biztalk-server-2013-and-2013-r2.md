---
title: Novedades de BizTalk Server 2013 y 2013 R2 | Documentos de Microsoft
description: "Lista completa de nuevas características y cambios en BizTalk Server 2013 R2 y 2013"
caps.latest.revision: "67"
author: MandiOhlinger
manager: anneta
ms.custom: 
ms.date: 2017-08-10
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bdb841f7-4aa9-45c9-a6f1-d527089fcc09
ms.author: mandia
ms.openlocfilehash: 49a4e668f1c5e23169464fdbc4b4f0464a062628
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="whats-new-in-biztalk-server-2013-and-2013-r2"></a>Novedades de BizTalk Server 2013 y 2013 R2
Consulte las novedades y lo que está en desuso en [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)] y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013.
  
##  <a name="BKMK_NewR2"></a> Novedades de BizTalk Server 2013 R2  
  
|Característica|Descripción|  
|-------------|-----------------|  
|Compatibilidad con nuevas versiones de Windows OS, SQL Server y Visual Studio|Consulte [Requisitos de hardware y software de BizTalk Server 2013 y 2013 R2](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md).|  
|Compatibilidad con JSON|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ahora admite el envío y la recepción de mensajes JSON. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] incluye un asistente para generar esquemas XSD a partir de instancias JSON, y un componente de codificador y descodificador para usarlo con canalizaciones personalizadas. Para obtener más información, consulte [Procesamiento de mensajes JSON con BizTalk Server](../core/processing-json-messages-using-biztalk-server.md).|  
|Actualizaciones del adaptador SB-Messaging|El adaptador SB-Messaging se ha mejorado para que admita autenticación basada en SAS (Firma de acceso compartido), además de ACS.  Con esta mejora, BizTalk Server puede interactuar también con la edición local de Service Bus. Para obtener más información, consulte [Adaptador SB-Messaging](../core/sb-messaging-adapter.md).|  
|Actualizaciones del adaptador SFTP|El adaptador SFTP admite ahora autenticación en dos fases y proporciona una opción para especificar una carpeta temporal cuando se cargan y descargan archivos de gran tamaño. También se puede seleccionar el valor de cifrado específico del servidor de destino. Para obtener más información, consulte [Adaptador SFTP](../core/sftp-adapter.md).|  
|Actualizaciones del acelerador para HL7|Ahora el acelerador para HL7 admite lo siguiente:<br /><br /> - Proporciona funcionalidad para incluir datos de texto libre como parte del mensaje que pueden procesar las canalizaciones para HL7.<br /><br /> - Compatibilidad con 64 bits para hospedar el adaptador HL7.<br /><br /> Consulte [What's New in BizTalk Accelerator for HL7](http://msdn.microsoft.com/library/ee409458\(v=bts.80\).aspx) (Novedades en el Acelerador de BizTalk para HL7).|  
|BizTalk Health Monitor|BizTalk Health Monitor es un nuevo complemento de BizTalk que permite hacer un seguimiento del estado del entorno de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Este complemento se puede agregar a la consola de administración de BizTalk o ejecutarse por separado. BizTalk Health Monitor cuenta con las siguientes características:<br /><br /> - Generar y ver informes de mantenimiento.<br /><br /> - Vista de panel del mantenimiento global del entorno de BizTalk.<br /><br /> - Enviar notificaciones por correo electrónico.<br /><br /> - Programar la recopilación de informes.<br /><br /> - Integración de monitores de rendimiento con contadores de rendimiento basados en el escenario y cargados previamente.<br /><br /> - Supervisar varios entornos de BizTalk.<br /><br /> - Administración de informes.<br /><br /> Para obtener más información sobre BizTalk Health Monitor, consulte [Getting Started with BizTalk Health Monitor](http://go.microsoft.com/fwlink/?LinkId=403315) (Introducción a BizTalk Health Monitor) y [Overview of BizTalk Health Monitor](http://go.microsoft.com/fwlink/?LinkId=403316) (Información general sobre BizTalk Health Monitor).|  
  
### <a name="deprecated-list"></a>Lista desusada  
  
|del usuario|Estado|Sustituta|  
|-------------|------------|-----------------|  
|RFID Mobile|se quita.|Ninguno|  
|Servidor RFID|Obsoleto|Ninguno|  
|Adaptador del Servicio web o SSOM de SharePoint|Obsoleto|Use la opción CSOM (Modelo de objetos del lado cliente).<br /><br /> [Adaptador de Windows SharePoint Services](../core/windows-sharepoint-services-adapter.md)<br /><br /> [Apéndice B: Instalar el adaptador de Microsoft SharePoint](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)|  
|Adaptador de SOAP|Obsoleto|[Adaptador de WCF-BasicHttp](../core/wcf-basichttp-adapter.md)|  
|Antiguo adaptador de SQL|Obsoleto|Adaptador de SQL basado en WCF en [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]|  
|UDDI|Obsoleto|Ninguno|  
  
> [!IMPORTANT]
>  Algunas de estas características en desuso pueden encontrarse en las versiones más recientes de BizTalk. En estas situaciones, considere lo siguiente:  
>   
>  -   La característica puede utilizarse internamente en BizTalk y no está diseñada para utilizarse en soluciones de cliente. No se admite en soluciones de cliente.  
> -   Microsoft ha modificado las interfaces y es posible que no estén disponibles públicamente.  
  
##  <a name="BKMK_New"></a> Novedades de BizTalk Server 2013  
 En BizTalk Server 2013, se han incorporado las siguientes características.  
  
 **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en Azure IaaS**  
  
|Característica|Descripción|  
|-------------|-----------------|  
|Configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en una [!INCLUDE[vm](../includes/vm-md.md)] de [!INCLUDE[winazure](../includes/winazure-md.md)]|Consulte [Crear una máquina virtual de BizTalk en Azure](http://msdn.microsoft.com/library/jj572843.aspx).|  
|Crear un grupo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en una [!INCLUDE[vm](../includes/vm-md.md)] de [!INCLUDE[winazure](../includes/winazure-md.md)]|Consulte [Crear los requisitos previos del grupo de BizTalk](http://msdn.microsoft.com/library/jj248711.aspx) y [Configurar el grupo de BizTalk](http://msdn.microsoft.com/library/jj572845.aspx).|  
  
 **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en entornos locales**  
  
|Característica|Descripción|  
|-------------|-----------------|  
|Modelo de licencias por núcleo|Las licencias de BizTalk Server 2013 son por núcleo. Las de SQL Server 2012 también son por núcleo. Las licencias de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2010 y versiones anteriores son por procesador.<br /><br /> Cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se ejecuta en procesadores con cuatro núcleos o menos, el coste de la licencia es coherente con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2010. El precio de las licencias por núcleo es una cuarta parte del coste de una licencia por procesador. Cuando se ejecutan servidores con procesadores de mayor capacidad, el coste de las licencias aumenta debido a la mayor capacidad del hardware.<br /><br /> Para ayudarle a determinar el número de licencias que necesita, hay disponible un cmdlet de PowerShell en *C:\Archivos de programa (x86)\Microsoft BizTalk Server 20xx\SDK\Utilities\LicenseUsageTracking*.<br /><br /> Vínculos útiles:<br /><br /> [Precios y ediciones de BizTalk Server 2013](http://www.microsoft.com/biztalk/pricing.aspx)<br /><br /> [Understand BizTalk Server 2013 Licensing](http://blogs.biztalk360.com/understand-biztalk-server-2013-licensing/) (Descripción de las licencias de BizTalk Server 2013)|  
|Compatibilidad con nuevos adaptadores|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] permite a los nuevos adaptadores ampliar la conectividad de las aplicaciones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] a [!INCLUDE[winazure](../includes/winazure-md.md)]. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] también ofrece actualizaciones para los adaptadores de SharePoint que permiten a los usuarios elegir entre el modelo de objetos del cliente o del servidor para la conexión a un servidor de SharePoint. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] incluye un nuevo adaptador que permite el envío y la recepción de mensajes desde un servidor SFTP.|  
|Dependencias de seguimiento entre artefactos|La consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se ha actualizado en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para ofrecer una experiencia basada en la interfaz de usuario que permite ver las dependencias entre los distintos artefactos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] como, por ejemplo, las orquestaciones, los puertos de envío, las ubicaciones de recepción, etc. Para obtener más información, consulte [Seguimiento de dependencias entre artefactos en una aplicación de BizTalk Server](../core/tracking-dependencies-between-artifacts-in-a-biztalk-server-application.md).|  
|Kit de herramientas ESB integrado|El kit de herramientas de ESB está integrado ahora en la instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Asimismo, la configuración del kit de herramientas ESB se ha simplificado con el fin de reducir el tiempo que necesitan los usuarios para comenzar a utilizar el kit. Para obtener más información, consulte [Instalar y configurar el kit de herramientas de Microsoft BizTalk ESB](../esb-toolkit/install-and-configure-the-microsoft-biztalk-esb-toolkit.md).|  
|Compatibilidad con nuevas versiones de Windows OS, SQL Server y Visual Studio|Consulte [Requisitos de hardware y software de BizTalk Server 2013 y 2013 R2](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md).|  
|Actualizaciones a los esquemas EDI compatibles|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] introduce compatibilidad con los siguientes esquemas EDI:<br /><br /> -                     **X12:** 5040, 5050, 6020, 6030<br /><br /> - **EDIFACT:** D06A, D06B, D07A, D07B, D08A, D08B, D09A, D09B, D10A, D10B<br /><br /> -                     **HL7:** se ha agregado compatibilidad con los mensajes de la versión 2.51<br /><br /> -                     **SWIFT:** 2012 Message Pack<br /><br /> Los esquemas están incluidos en el paquete de instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Puede descargar el paquete de instalación de [http://go.microsoft.com/fwlink/p/?LinkId=258228](http://go.microsoft.com/fwlink/p/?LinkId=258228).|  
|El Asignador usa XSLCompiledTransform|El Asignador usa la clase XSLCompiledTransform. En las versiones anteriores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se usaba la clase XslTransform, que es obsoleta. La clase XSLCompiledTransform proporciona mejoras de rendimiento, entre las que se incluye:<br /><br /> - Cuando el método Load se complete correctamente, el método Transform se puede llamar simultáneamente desde varios subprocesos.<br /><br /> - El nuevo procesador XSLT compila la hoja de estilo XSLT en un formato intermedio común. Una vez compilada la hoja de estilo, esta se puede almacenar en caché y volver a utilizar.<br /><br /> Puede obtener más información en [What the Mapper Updates Mean for You](http://www.quicklearn.com/blog/2013/05/24/what-the-biztalk-server-2013-mapper-updates-mean-for-you/) (Qué conllevan para usted las actualizaciones del Asignador) y [Clase XslCompiledTransform](https://msdn.microsoft.com/library/system.xml.xsl.xslcompiledtransform.aspx).|  
|Controlador de puerto de envío dinámico configurable|Al crear un puerto de envío dinámico, puede configurar un controlador de envío de adaptador para *cada* adaptador instalado. Incluye los puertos dinámicos Unidireccional y Petición-respuesta. En versiones anteriores de BizTalk, un puerto de envío dinámico usa el host predeterminado del adaptador.<br /><br /> En [El controlador de puerto de envío dinámico es configurable](../core/dynamic-send-port-handler-is-configurable.md) encontrará más información.|  
|Entrega ordenada|En versiones anteriores de BizTalk con escenarios donde la entrega ordenada usa varios extremos, el tipo de adaptador más lento es la velocidad máxima. Este comportamiento afecta directamente a las soluciones HL7. Cuando se usa el adaptador MLLP, se requieren confirmaciones (ACK). Puede haber retrasos porque debe recibirse una confirmación antes de enviar el siguiente mensaje.<br /><br /> En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], el siguiente mensaje se puede enviar sin esperar confirmación del mensaje anterior. Cuando llega la confirmación, se correlaciona o conecta internamente con su mensaje.|  
|Herramientas de soporte|Las herramientas de soporte se instalan automáticamente con BizTalk: *C:\Archivos de programa (x86)\Microsoft BizTalk Server 20xx\SDK\Utilities\Support Tools*.<br /><br /> Las herramientas incluyen:<br /><br /> - Comprobador de ensamblados de BizTalk<br /><br /> - MsgBox Viewer<br /><br /> - PSSDiagForBizTalk<br /><br /> - Acceso directo de Internet a la descarga del terminador de BizTalk|  
|Proveedor de PowerShell|El proveedor de PowerShell de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se encuentra en la carpeta *C:\Archivos de programa (x86)\Microsoft BizTalk Server 2013\SDK\Utilities\PowerShell*.<br /><br /> Para versiones anteriores de BizTalk, hay un proveedor de PowerShell de CodePlex en [http://psbiztalk.codeplex.com/](http://psbiztalk.codeplex.com/).|  
|Alertas de BAM|Si BizTalk Server 2013 usa [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)], se necesita Correo electrónico de base de datos para usar alertas de BAM. Si BizTalk Server usa SQL Server 2008 R2, se necesita SQL Server Notification Services para usar alertas de BAM.<br /><br /> Las [alertas de BAM](../install-and-config-guides/prepare-your-computer-for-installation.md#BKMK_BAMAlerts) proporcionan más información.|  
  
> [!IMPORTANT]
>  Cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] se instalan en equipos independientes, el Coordinador de transacciones distribuidas (MS DTC) controla las transacciones entre los equipos. Como resultado, la característica AlwaysOn de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] no se admite con [!INCLUDE[bts2013r2](../includes/bts2013r2-md.md)] y 2013. A partir de [!INCLUDE[bts2016](../includes/bts2016-md.md)], **se admite** la característica AlwaysOn. Consulte [What's New in BizTalk Server 2016](../install-and-config-guides/what-s-new-in-biztalk-server-2016.md) (Novedades de BizTalk Server 2016) para obtener detalles.  
  
### <a name="known-issues"></a>Problemas conocidos  
 [Problemas conocidos de BizTalk Server 2013](http://support.microsoft.com/kb/2954101)