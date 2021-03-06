---
title: Guía de operaciones de BizTalk Server 2010 | Microsoft Docs
ms.custom: ''
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4dc0d8e9-9ad6-4ce1-8ca7-399b67cb360e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c78d0b9fc1b5f149e3eb3ffb7e97569bd199652f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966733"
---
# <a name="biztalk-server-2010-operations-guide"></a>Guía de operaciones de BizTalk Server 2010
Bienvenido a la Guía de operaciones de Microsoft® BizTalk® Server 2010. Hemos creado esta guía para ser un valioso recurso para cualquier persona involucrada en la implementación y administración de una solución de BizTalk, especialmente los profesionales de TI.  
  
 Para descargar una copia de esta guía en el formulario docx, pdf o chm, vaya a [Guía de operaciones de Microsoft BizTalk Server 2010](http://go.microsoft.com/fwlink/?LinkId=212652) (http://go.microsoft.com/fwlink/?LinkId=212652).  
  
## <a name="which-versions-of-biztalk-server-does-the-guide-cover"></a>¿Qué versiones de BizTalk Server cubre la Guía?  
 En esta guía se encarga de BizTalk Server y proporciona información de preparación operativa para ayudar a ponga en marcha con su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] el programa de instalación.  
  
> [!NOTE]
>  Para ver la Guía de operaciones para [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] o [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)], consulte [ http://go.microsoft.com/fwlink/?LinkID=130458 ](http://go.microsoft.com/fwlink/?LinkID=130458).  
  
## <a name="where-do-i-start"></a>¿Por dónde comenzar?  
 Se organiza la Guía de acuerdo con los aspectos funcionales de planear, implementar y administrar un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instalación. Por lo tanto, puede leerla según estos aspectos funcionales. Sin embargo, al darse cuenta que las listas de comprobación sería la más buscado después de la información en la Guía de operaciones de BizTalk Server, nos hemos clasificar todas las listas de comprobación en el documento en la siguiente tabla para facilitar la accesibilidad.  
  
|||  
|-|-|  
|**Configuración del entorno de BizTalk**|**Configurar una alta disponibilidad y el entorno de recuperación ante desastres**|  
|-   [Lista de comprobación: Introducción a BizTalk Server](http://msdn.microsoft.com/library/37d265cd-c393-46ac-ac21-129a1511359b)<br />-   [Lista de comprobación: Configuración de Windows Server](~/technical-guides/checklist-configuring-windows-server.md)<br />-   [Lista de comprobación: Configuración de Internet Information Services](~/technical-guides/checklist-configuring-internet-information-services.md)<br />-   [Lista de comprobación: Configuración de SQL Server](../technical-guides/checklist-configuring-sql-server.md)<br />-   [Lista de comprobación: Configuración de BizTalk Server](~/technical-guides/checklist-configuring-biztalk-server.md)|-   [Lista de comprobación: Proporcionar una alta disponibilidad con tolerancia a errores o equilibrio de carga](~/technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)<br />-   [Lista de comprobación: Aumento de la disponibilidad con recuperación ante desastres](~/technical-guides/checklist-increasing-availability-with-disaster-recovery.md)|  
|**Supervisión, probar y solucionar problemas**|**Rendimiento y mantenimiento**|  
|-   [Lista de comprobación: Supervisión de preparación operativa](~/technical-guides/checklist-monitoring-operational-readiness.md)<br />-   [Lista de comprobación: Mantenimiento y solución de problemas de las bases de datos de BizTalk Server](../technical-guides/checklist-maintaining-and-troubleshooting-biztalk-server-databases.md)<br />-   [Lista de comprobación: Probar la preparación operativa](~/technical-guides/checklist-testing-operational-readiness.md)<br />-   [Lista de comprobación: Supervisión de BizTalk Server con Operations Manager 2007](~/technical-guides/checklist-monitoring-biztalk-server-with-operations-manager-2007.md)<br />-   [Lista de comprobación: Supervisión de servidores SQL Server](~/technical-guides/checklist-monitoring-sql-servers.md)|Mantenimiento relacionadas con las listas de comprobación:<br /><br /> -   [Lista de comprobación: Realización de comprobaciones de mantenimiento diario](~/technical-guides/checklist-performing-daily-maintenance-checks.md)<br />-   [Lista de comprobación: Realización de comprobaciones de mantenimiento semanal](~/technical-guides/checklist-performing-weekly-maintenance-checks.md)<br />-   [Lista de comprobación: Realización de comprobaciones de mantenimiento mensual](~/technical-guides/checklist-performing-monthly-maintenance-checks.md)<br /><br /> Listas de comprobación relacionadas con el rendimiento:<br /><br /> -   [Lista de comprobación: Realización de comprobaciones de rendimiento semanales](~/technical-guides/checklist-performing-weekly-performance-checks.md)<br />-   [Lista de comprobación: Realización de comprobaciones de rendimiento mensuales](~/technical-guides/checklist-performing-monthly-performance-checks.md)|  
|**Listas de comprobación para otras tareas importantes**||  
|-   [Lista de comprobación: Implementar una aplicación](~/technical-guides/checklist-deploying-an-application.md)<br />-   [Lista de comprobación: Exportación de enlaces de una aplicación a otra](~/technical-guides/checklist-exporting-bindings-from-one-application-to-another.md)<br />-   [Lista de comprobación: Actualización de un ensamblado](~/technical-guides/checklist-updating-an-assembly.md)<br />-   [Lista de comprobación: Actualización de artefactos en una aplicación de BizTalk](~/technical-guides/checklist-updating-artifacts-in-a-biztalk-application.md)|-   [Lista de comprobación: Actualización de una aplicación con control de versiones en paralelo](~/technical-guides/checklist-updating-an-application-using-side-by-side-versioning.md)<br />-   [Lista de comprobación: Actualización de una orquestación mediante el control de versiones en paralelo](~/technical-guides/checklist-updating-an-orchestration-using-side-by-side-versioning.md)<br />-   [Lista de comprobación: Instalación y configuración de certificados](../technical-guides/checklist-installing-and-configuring-certificates.md)<br />-   [Lista de comprobación: Planificación de operaciones en un entorno seguro](../technical-guides/checklist-planning-for-operations-in-a-secure-environment.md)|  
  
 Si va a realizar las siguientes tareas, puede comenzar con las secciones relacionadas:  
  
- **Evaluación de preparación operativa**: si deseas centrarte en evaluar y evaluar la preparación operativa de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementación y, a continuación, comience por leer el [listas de comprobación de las operaciones](~/technical-guides/operations-checklists.md) y [ Aumentar la disponibilidad de BizTalk Server](~/technical-guides/increasing-availability-for-biztalk-server.md) secciones.  
  
- **Preparando operativamente**: para asegurarse de que su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] infraestructura y aplicaciones se convierten en listas operativamente, hacen referencia a la [planificación del entorno de BizTalk Server](~/technical-guides/planning-the-environment-for-biztalk-server.md) sección.  
  
- **Mantener un entorno operativo**: la mayoría de los temas de la Guía de operaciones le ayudarán a mantener un funcionamiento [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno. Encontrará procedimientos recomendados, conceptos y procedimientos para mantener un entorno operativo en las secciones siguientes: [aumentar la disponibilidad de BizTalk Server](~/technical-guides/increasing-availability-for-biztalk-server.md), [supervisar BizTalk Server](~/technical-guides/monitoring-biztalk-server2.md), y [mantenimiento de BizTalk Server2](~/technical-guides/maintaining-biztalk-server2.md).  
  
## <a name="whats-in-it"></a>¿Qué es lo?  
 Guía basada en la experiencia real. La idea de la guía se creó con los representantes de campo de Microsoft, las organizaciones asociadas y los clientes que planeen, implementar y mantener las instalaciones de BizTalk Server. Este grupo de profesionales de TI ha acumulado una amplia experiencia práctica con las soluciones de un intervalo diverso de BizTalk. Como obtenido experiencia que crean listas de comprobación, mejores prácticas y presentaciones para orientar a futuras [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] operaciones. Se recopilan y se organiza de esta información para crear a la guía.  
  
 Las partes principales de esta guía son nuevas; Sin embargo, una parte considerable hace referencia a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda, notas del producto, artículos de Knowledge Base y otros orígenes. Ha sido cuidadosamente revisado y probado por expertos de la Comunidad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] profesionales de TI y los miembros del equipo de desarrollo del producto, quien agradecemos al final de este tema. Creemos que le ayudarán la información aquí expuesta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] resolver usuarios y evite por encima de todo, muchos de los problemas comunes que pueden producirse al implementar y mantener un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instalación.  
  
## <a name="acknowledgments"></a>Confirmaciones  
 En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo de educación del usuario aportados reconoce las contribuciones pendientes de las siguientes personas para proporcionar comentarios técnicos así como una gran cantidad de contenido para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Guía de operaciones:  
  
-   Paolo Salvatori, Tim Wieman