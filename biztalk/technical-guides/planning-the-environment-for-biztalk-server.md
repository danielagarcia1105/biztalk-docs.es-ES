---
title: Planificación del entorno de BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e9ef0b4-eccb-47e2-bbb5-e859ffa0468c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d92039b397053d24909d6ade75797c9f68d06172
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977741"
---
# <a name="planning-the-environment-for-biztalk-server"></a>Planificación del entorno de BizTalk Server
La sección de planeación de la Guía de operaciones describe funciones y responsabilidades asociadas con un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno. Incluye recomendaciones para los niveles de aplicación y datos de planear una [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno y proporciona recomendaciones de planificación de la versión de las fases de la administración de una solución de BizTalk.  
  
 Como se suele decir deja, "Si no puede planear, va a producir un error." Aunque ciertamente hay excepciones a este Consejo sage, una implementación correcta de una solución de BizTalk de producción no es uno de ellos. Este tema de introducción a la sección de planeación proporciona una descripción general de las decisiones que debe tomar al planear la solución de BizTalk.  
  
## <a name="deciding-whether-biztalk-server-is-the-right-tool-for-the-job"></a>Decidir si el servidor BizTalk Server es la herramienta adecuada para el trabajo  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede considerarse como un "motor de integración empresarial". En esencia, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está diseñado para integrar sistemas empresariales dispares, procesos y los mensajes. Por ejemplo, un sistema de negocio que intercambia mensajes que cumplen el estándar EDI que deba integrarse en un sistema de negocio que intercambia mensajes que cumplen el estándar de RosettaNet. O bien, un sistema de negocio internas que utiliza SAP que necesite para comunicarse con otro sistema de negocio internas que almacena datos en una base de datos de Microsoft SQL Server. O quizás se necesita un sistema de negocio que solo se puede enviar o recibir mensajes mediante el protocolo FTP intercambiar mensajes con un sistema de negocio que solo se puede usar el protocolo HTTP.  
  
 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] actuando como intermediario para la entrega de mensajes entre los sistemas se adapta a la integración de dichos sistemas dispares. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] admite una amplia gama de protocolos de transporte estándar del sector, formatos de intercambio de documentos y aplicaciones empresariales.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] También proporciona las capacidades de automatización del proceso de negocio eficaces en el motor de orquestaciones de BizTalk. Utilice el Diseñador de orquestaciones de BizTalk para crear representaciones visuales de los procesos empresariales que pueden crearse en el código ejecutable que se ejecuta en el motor de orquestaciones de BizTalk.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] También incluye otras características que facilitan la integración de negocio incluye un motor de flujo de trabajo de mensaje, un motor de reglas de negocios (BRE) y tecnologías para los trabajadores de información como la actividad de supervisión a económica (BAM).  
  
 Para obtener más información sobre el uso de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] funcionalidad de administración de procesos de negocio, consulte [notas del producto: Microsoft y BPM: Introducción técnica a](http://go.microsoft.com/fwlink/?LinkId=106015) (<http://go.microsoft.com/fwlink/?LinkId=106015>). Para obtener más información acerca de las tecnologías de integración diferentes ofrecidas por Microsoft y las ventajas que uno tiene sobre el otro, consulte [entender las tecnologías de Microsoft Integration](http://go.microsoft.com/fwlink/?LinkId=158452) (<http://go.microsoft.com/fwlink/?LinkId=158452>).  
  
 Ciertos escenarios de integración son más adecuadas para otros productos de Microsoft. Si su objetivo principal es ante cualquiera de los siguientes escenarios, considere el uso de estos productos de Microsoft en lugar de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
|**Escenario**|**Producto de usar**|  
|------------------|------------------------|  
|Aprovisionamiento de usuarios|**Ciclo de vida de Microsoft Identity Manager 2010**<br /><br /> Para obtener más información acerca del ciclo de vida de Microsoft Identity Manager 2010, consulte [Microsoft Identity Lifecycle Manager 2010 FP1](http://go.microsoft.com/fwlink/?LinkId=204577) (http://go.microsoft.com/fwlink/?LinkId=204577).|  
|Replicación de datos entre sistemas|**Replicación de SQL Server**<br /><br /> Para obtener más información acerca de la replicación de SQL Server, vea [replicación de SQL Server 2008 R2](http://go.microsoft.com/fwlink/?LinkID=69978) (http://go.microsoft.com/fwlink/?LinkID=69978).|  
|Extracción de datos, transformación y carga (ETL)|**SQL Server Integration Services (SSIS)**<br /><br /> Para obtener más información acerca de SQL Server Integration Services, consulte [SQL Server 2008 R2 Integration Services](http://go.microsoft.com/fwlink/?LinkId=152044) (http://go.microsoft.com/fwlink/?LinkId=152044).|  
  
## <a name="deciding-which-edition-of-biztalk-server-is-right-for-the-job"></a>Decidir qué edición de BizTalk Server es el derecho para el trabajo  
 Hay cuatro ediciones de BizTalk Server, cada uno de los cuales se destina a escenarios específicos. Las cuatro ediciones de BizTalk Server incluyen:  
  
- **Enterprise** : diseñada para los clientes con requisitos de nivel empresarial de gran volumen, la confiabilidad y disponibilidad.  
  
- **Estándar** : diseñada para las empresas con volumen moderado y requisitos de implementación de escalado.  
  
- **Rama** -versión de Especialidad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] diseñado para el concentrador y radio escenarios de implementación incluida de RFID.  
  
- **Desarrollador** : proporciona toda la funcionalidad de Enterprise Edition para fines de prueba y desarrollo y está disponible como la edición de evaluación de BizTalk Server sin costo alguno para fines de evaluación. Cuando se instala como la edición de evaluación, BizTalk Server funcionará durante 120 días.  
  
- **Enterprise RFID** : diseñada para proporcionar una plataforma escalable y extensible para desarrollo, implementación y administración de RFID enriquecido y soluciones de sensor, incluye el servidor BizTalk RFID y BizTalk RFID Mobile.  
  
  Para obtener más información sobre las diferentes ediciones de BizTalk Server, consulte [ediciones de Microsoft BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=108051) (http://go.microsoft.com/fwlink/?LinkId=108051).  
  
## <a name="planning-for-message-load"></a>Planeación de la carga de mensajes  
 Cuando haya determinado que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cumple su integración negocio necesita, lo siguiente que debe determinar la carga de mensajes que será la solución de BizTalk debe procesar. Esto es una decisión importante porque las diferentes ediciones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] tiene distintas capacidades de escalado vertical y horizontal.  
  
 La clave para determinar la carga de mensajes es realizar pruebas de carga para determinar el rendimiento sostenible máximo (MST) y el máximo sostenible seguimiento de rendimiento (MSTT) de la solución de BizTalk. Para obtener más información sobre cómo medir el rendimiento máximo sostenible y procedimientos recomendados de rendimiento en general, consulte el [Guía de rendimiento de BizTalk Server 2009](http://go.microsoft.com/fwlink/?LinkID=150492) (http://go.microsoft.com/fwlink/?LinkID=150492).  
  
## <a name="planning-for-expansion"></a>Planeación de expansión  
 Considere la posibilidad de implementar una solución de BizTalk mediante la edición Enterprise de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] si va a agregar un número significativo de socios comerciales, necesita usar clústeres de host, o bien se debe escalar horizontalmente a varios equipos que ejecuten [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el Grupo de BizTalk. Las ediciones Standard y rama de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no dar cabida a varios equipos que ejecuten [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un grupo o los clústeres de host.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Responsabilidades y roles de BizTalk Server](../technical-guides/biztalk-server-roles-and-responsibilities.md)  
  
-   [Planificación del nivel de BizTalk Server](../technical-guides/planning-the-biztalk-server-tier.md)  
  
-   [Planificación del nivel de base de datos](../technical-guides/planning-the-database-tier.md)  
  
-   [Planificación de los entornos de desarrollo, pruebas, ensayo y producción](../technical-guides/planning-the-development-testing-staging-and-production-environments.md)