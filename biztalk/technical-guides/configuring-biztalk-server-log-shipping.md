---
title: "Trasvase de registros de configuración de BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bcef31f7-30d1-4ada-b627-2a5c9ec7e43e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3209d96c4516c603510f3cbb7fb48e3b1eb3209
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-biztalk-server-log-shipping"></a>Trasvase de registros de configuración de BizTalk Server
El trabajo de copia de seguridad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se usa para hacer copia de seguridad de todas las bases de datos del sistema de origen de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], excepto por algunas bases de datos usadas por la supervisión de la actividad económica (BAM). El sistema de origen es el servidor o grupo de servidores que contiene datos activos. Dado que algunas de las bases de datos BAM tienen copia de seguridad diferente y requisitos de restauración, estas bases de datos copia de seguridad y restauran mediante otros métodos.  
  
 La copia de seguridad y restauración de las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implica los pasos siguientes:  
  
1.  **Configurar el trabajo de copia de seguridad de BizTalk Server**  
  
     Antes de que resulte posible efectuar una copia de seguridad de las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], tendrá que configurar primero el trabajo de copia de seguridad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el sistema de origen; con ello, se establece que las copias de seguridad se escriban automáticamente en una carpeta en la que puedan utilizarse para restaurar las bases de datos en el sistema de destino. El sistema de destino es el servidor o grupo de servidores que se utilizará para restaurar las copias de seguridad de base de datos generadas por el sistema de origen. Para obtener más información acerca de este paso, consulte [cómo configurar un trabajo de copia de seguridad de BizTalk Server](../technical-guides/how-to-configure-a-backup-biztalk-server-job.md).  
  
2.  **Configurar el sistema de destino de trasvase de registros**  
  
     También es preciso configurar el sistema de destino para el envío de registros, con lo que se proporcionan capacidades de servidor en espera y se reduce el tiempo de inactividad en el caso de que se produzca un error del sistema. Para obtener más información acerca de este paso, consulte [cómo configurar el sistema de destino](../technical-guides/how-to-configure-the-destination-system.md).  
  
3.  **Restaurar las bases de datos**  
  
     Cuando se produce un error de hardware, es posible restaurar las bases de datos mediante las copias de seguridad y los registros enviados al sistema de destino. Para obtener más información acerca de este paso, consulte [cómo restaurar bases de datos en el trabajo de copia de seguridad de BizTalk Server](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md).  
  
## <a name="biztalk-server-databases"></a>Bases de datos de BizTalk Server  
 Las tablas siguientes describen las bases de datos que utiliza [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] e identifican los métodos que se utilizan para realizar una copia de seguridad de las bases de datos.  
  
### <a name="databases-backed-up-by-the-backup-biztalk-server-job"></a>Bases de datos de copia de seguridad realizada mediante el trabajo de copia de seguridad de BizTalk Server  
 En la tabla siguiente se enumeran las bases de datos de las que se ha realizado una copia de seguridad y que se han restaurado como parte del trabajo de copia de seguridad de BizTalk Server. Al agregar bases de datos personalizadas a la tabla adm_OtherBackupDatabases, podrá modificar el trabajo de copia de seguridad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para realizar una copia de seguridad de aquéllas. Para obtener más información, consulte [cómo volver de seguridad de la bases de datos personalizado](http://go.microsoft.com/fwlink/?LinkID=151569) (http://go.microsoft.com/fwlink/?LinkID=151569).  
  
|Base de datos|Nombre predeterminado de la base de datos|Description|  
|--------------|---------------------------|-----------------|  
|Base de datos de importación principal de BAM|BAMPrimaryImport|Ésta es la base de datos en la que Supervisión de la actividad económica (BAM) recopila los datos de seguimiento sin procesar.|  
|Base de datos de la aplicación de servicios de notificación de BAM|BAMAlertsApplication|Esta base de datos contiene información de alertas para notificaciones de BAM. Por ejemplo, al crear una alerta utilizando el portal de BAM, las entradas se insertan en la base de datos especificando las condiciones y eventos a los que pertenece la alerta, así como otros datos complementarios relativos a ésta.|  
|Base de datos de instancia de servicios de notificación de BAM|BAMAlertsNSMain|Esta base de datos contiene información de la instancia que especifica el modo en que los servicios de notificación se conectan con el sistema supervisado por BAM.|  
|Base de datos de seguimiento de BizTalk|BizTalkDTADb|Esta base de datos almacena datos de supervisión de estado de cuyo seguimiento se ocupa el motor de seguimiento de BizTalk Server.|  
|Base de datos de administración de BizTalk|BizTalkMgmtDb|Esta base de datos es el almacén central de metainformación para todas las instancias de BizTalk Server.|  
|Base de datos de BizTalk MessageBox|BizTalkMsgBoxDb|El motor de BizTalk Server usa esta base de datos para el enrutamiento, la puesta en cola, la administración de instancias y otras tareas.|  
|Base de datos del motor de reglas|BizTalkRuleEngineDb|Esta base de datos es un repositorio para lo siguiente:<br /><br /> -Directivas, que son conjuntos de reglas relacionadas.<br />-Vocabularios, que son colecciones de nombres descriptivos y específico de dominio para referencias de datos de reglas.|  
|base de datos de SSO|SSODB|Esta base de datos Enterprise Single Sign-On almacena de forma más segura la configuración de información de las ubicaciones de recepción.|  
  
### <a name="databases-backed-up-when-backing-up-the-bam-analysis-and-tracking-analysis-server-databases"></a>Copia de seguridad al realizar copias de seguridad el análisis de seguimiento y análisis de BAM bases de datos del servidor de bases de datos  
 En la tabla siguiente se enumera las bases de datos que se copian con los procedimientos de [copia el análisis de BAM y base de datos de seguimiento de Analysis Server](http://msdn.microsoft.com/library/aa578580\(v=bts.70\).aspx):  
  
|Base de datos|Nombre predeterminado de la base de datos|Description|  
|--------------|---------------------------|-----------------|  
|Esquema de estrella de BAM|BAMStarSchema|Esta base de datos contiene la tabla provisional y las tablas de dimensiones y medidas.|  
|Análisis de BAM|BAMAnalysis|Esta base de datos contiene cubos BAM OLAP para el análisis en línea y fuera de línea.|  
|Archivo de BAM|BAMArchive|Esta base de datos archiva datos antiguos de actividad económica. Cree una base de datos de archivo de BAM para reducir al mínimo la acumulación de datos de actividad económica en la base de datos de importación principal de BAM.|  
|Servidor de análisis de seguimiento|BizTalkAnalysisDb|Esta base de datos almacena cubos OLAP (procesamiento analítico en línea) de supervisión de estado.|  
  
 Esta sección de la Guía de operaciones describen los pasos adicionales que debe seguir para configurar BizTalk Server trasvase de registros.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Configurar el sistema de origen](../technical-guides/configuring-the-source-system.md)  
  
-   [Cómo configurar el sistema de destino](../technical-guides/how-to-configure-the-destination-system.md)  
  
-   [Configurar el servidor BizTalk Server trasvase de registros para las bases de datos adicionales](../technical-guides/configuring-biztalk-server-log-shipping-for-additional-databases.md)  
  
-   [Trasvase de registros de supervisión de BizTalk Server](../technical-guides/monitoring-biztalk-server-log-shipping.md)