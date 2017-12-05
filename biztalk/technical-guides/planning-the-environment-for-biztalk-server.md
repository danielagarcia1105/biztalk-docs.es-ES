---
title: Planear el entorno de BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3e9ef0b4-eccb-47e2-bbb5-e859ffa0468c
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66cd358f3d8a4fbda2c4ed43432f1ad8b2f6979e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="planning-the-environment-for-biztalk-server"></a>Planear el entorno de BizTalk Server
La sección de planeamiento de la Guía de operaciones describe los roles y responsabilidades asociadas con un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno. Incluye la planificación de las recomendaciones para los niveles de aplicación y los datos de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno y proporciona recomendaciones de planificación de la versión de fases de la administración de una solución de BizTalk.  
  
 Como los hablados queda, "Si se produce un error planear, piensa producirá un error." Aunque por supuesto, hay excepciones a este Consejo sage, una implementación correcta de una solución de BizTalk de producción no es uno de ellos. Este tema de introducción a la sección de planeamiento proporciona una descripción general de las decisiones que debe tomar al planear la solución de BizTalk.  
  
## <a name="deciding-whether-biztalk-server-is-the-right-tool-for-the-job"></a>Decidir si el servidor BizTalk Server es la herramienta adecuada para el trabajo  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]puede considerarse como un "motor de integración empresarial". En esencia, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está diseñado para integrar los sistemas empresariales diferentes, los procesos y mensajes. Por ejemplo, un sistema de negocio que intercambia mensajes que cumplen el estándar EDI necesite integrar con un sistema de negocio que intercambia mensajes que cumplen el estándar de RosettaNet. O bien, un sistema de negocio internas que utiliza SAP que necesite comunicarse con otro sistema de negocio internas que almacena los datos en una base de datos de Microsoft SQL Server. O quizás se necesita un sistema de negocio que solo se puede enviar o recibir mensajes mediante el protocolo FTP intercambiar mensajes con un sistema de negocio que solo se puede usar el protocolo HTTP.  
  
 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]admite la integración de estos sistemas dispares que actúa como intermediario para la entrega de mensajes entre los sistemas. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]admite una gran variedad de protocolos de transporte estándar del sector, formatos de intercambio de documentos y aplicaciones empresariales.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]También proporciona capacidades de automatización de procesos de negocios eficaces en el motor de orquestación de BizTalk. Utilice el Diseñador de orquestaciones de BizTalk para crear representaciones visuales de los procesos empresariales que se pueden compilar en código ejecutable que se ejecuta en el motor de orquestaciones de BizTalk.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]También incluye otras características que facilitan la integración de negocio incluye un motor de flujo de trabajo de mensaje, un motor de reglas de negocios (BRE) y tecnologías para trabajadores de la información como la actividad de supervisión a económica (BAM).  
  
 Para obtener más información sobre el uso de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] funcionalidad de administración de procesos de negocio, consulte [notas del producto: Microsoft y BPM: Introducción técnica a](http://go.microsoft.com/fwlink/?LinkId=106015) (http://go.microsoft.com/fwlink/?LinkId=106015). Para obtener más información acerca de las tecnologías de integración diferentes ofrecidas por Microsoft y las ventajas uno tiene sobre el otro, consulte [entender las tecnologías de integración de Microsoft](http://go.microsoft.com/fwlink/?LinkId=158452) (http://go.microsoft.com/fwlink/?LinkId=158452).  
  
 Ciertos escenarios de integración se adaptan mejor a otros productos de Microsoft. Si su objetivo principal es ante cualquiera de los siguientes escenarios, considere el uso de estos productos de Microsoft en lugar de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
|**Escenario**|**Poder usar producto**|  
|------------------|------------------------|  
|Aprovisionamiento de usuarios|**Microsoft Identity Lifecycle Manager 2010**<br /><br /> Para obtener más información acerca de Microsoft Identity Lifecycle Manager 2010, vea [Microsoft Identity Lifecycle Manager 2010 FP1](http://go.microsoft.com/fwlink/?LinkId=204577) (http://go.microsoft.com/fwlink/?LinkId=204577).|  
|Replicación de datos entre sistemas|**Replicación de SQL Server**<br /><br /> Para obtener más información acerca de la replicación de SQL Server, vea [replicación de SQL Server 2008 R2](http://go.microsoft.com/fwlink/?LinkID=69978) (http://go.microsoft.com/fwlink/?LinkID=69978).|  
|Extracción de datos, transformación y carga (ETL)|**SQL Server Integration Services (SSIS)**<br /><br /> Para obtener más información acerca de SQL Server Integration Services, vea [SQL Server 2008 R2 Integration Services](http://go.microsoft.com/fwlink/?LinkId=152044) (http://go.microsoft.com/fwlink/?LinkId=152044).|  
  
## <a name="deciding-which-edition-of-biztalk-server-is-right-for-the-job"></a>Decidir qué edición de BizTalk Server es correcta para el trabajo  
 Hay cuatro ediciones de BizTalk Server, cada uno de los cuales está destinada a escenarios concretos. Las cuatro ediciones de BizTalk Server incluyen:  
  
-   **Enterprise** : diseñado para los clientes con requisitos de nivel de empresa de gran volumen, confiabilidad y disponibilidad.  
  
-   **Estándar** : diseñada para empresas con moderado volumen y requisitos de implementación de escala.  
  
-   **Rama** -versión especializada de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] diseñado para su concentrador y radio escenarios de implementación incluso RFID.  
  
-   **Developer** : proporciona toda la funcionalidad de la edición Enterprise para fines de pruebas y desarrollo y está disponible como la edición de evaluación de BizTalk Server sin costo alguno para fines de evaluación. Cuando se instala como la edición de evaluación, BizTalk Server funcionará de 120 días.  
  
-   **RFID empresarial** : diseñado para proporcionar una plataforma escalable y extensible para desarrollo, implementación y administración de RFID enriquecida y las soluciones de sensor, incluye el servidor BizTalk RFID y BizTalk RFID Mobile.  
  
 Para obtener más información acerca de las diferentes ediciones de BizTalk Server, vea [ediciones de Microsoft BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=108051) (http://go.microsoft.com/fwlink/?LinkId=108051).  
  
## <a name="planning-for-message-load"></a>Planeación de la carga de mensajes  
 Una vez que ha determinado que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cumple su integración negocio necesita, lo siguiente que debe determinar la carga de mensajes que será la solución de BizTalk debe procesar. Esto es una decisión importante porque las distintas ediciones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] tienen capacidades distintas de escalado vertical y horizontal.  
  
 La clave para determinar la carga de mensaje es para realizar pruebas de carga para determinar el rendimiento sostenible máximo (MST) y el máximo sostenible seguimiento de rendimiento (MSTT) de la solución de BizTalk. Para obtener más información acerca de cómo medir el rendimiento máximo sostenible y prácticas recomendadas de rendimiento en general, vea el [Guía de rendimiento de BizTalk Server 2009](http://go.microsoft.com/fwlink/?LinkID=150492) (http://go.microsoft.com/fwlink/?LinkID=150492).  
  
## <a name="planning-for-expansion"></a>Planeación de expansión  
 Considere la posibilidad de implementar una solución de BizTalk mediante la edición Enterprise de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] si va a agregar un número significativo de socios comerciales, necesita usar clústeres de host, o bien se debe escalar horizontalmente a varios equipos que ejecuten [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el Grupo de BizTalk. Las ediciones Standard y bifurcación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no se ajustan a varios equipos que ejecuten [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un grupo o de clústeres de host.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Responsabilidades y roles de BizTalk Server](../technical-guides/biztalk-server-roles-and-responsibilities.md)  
  
-   [Planificación del nivel de BizTalk Server](../technical-guides/planning-the-biztalk-server-tier.md)  
  
-   [Planificación del nivel de base de datos](../technical-guides/planning-the-database-tier.md)  
  
-   [Planificación de los entornos de desarrollo, pruebas, ensayo y producción](../technical-guides/planning-the-development-testing-staging-and-production-environments.md)