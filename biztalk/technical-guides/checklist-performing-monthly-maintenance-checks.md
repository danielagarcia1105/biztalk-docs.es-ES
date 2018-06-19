---
title: 'Lista de comprobación: Hacer comprobaciones de mantenimiento mensual | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 588b74fa-6bf5-43ad-aa15-3595adde76d1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a637e80363e16f7a910bad98fee1843dd7dd891a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009261"
---
# <a name="checklist-complete-monthly-maintenance-checks-in-biztalk-server"></a>Lista de comprobación: Comprobaciones de mantenimiento mensual completos en BizTalk Server
En este tema se describe los pasos necesarios para mensual realizar comprobaciones de mantenimiento de la confiabilidad, la administración, la seguridad y el rendimiento de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sistema.  

## <a name="checklist"></a>Lista de comprobación
|Pasos|Referencia|  
|-----------|---------------|  
|Asegúrese de que la clave secreta principal realiza una arriba y estén disponibles en el almacenamiento sin conexión (comprobación de confiabilidad).|[Cómo realizar copias de seguridad del secreto principal](../core/how-to-back-up-the-master-secret.md)|  
|Asegúrese de que conmutan por error para todos los servicios en clúster se ha probado (comprobación de confiabilidad).|[Revisar y probar la configuración de clúster de servidores SQL Server para escenarios de conmutación por error](../technical-guides/reviewing-and-testing-sql-server-cluster-configuration-for-failover-scenarios.md)|  
|Asegúrese de que el servicio de SSO empresarial esté agrupado (comprobación de confiabilidad).|[Agrupación en clústeres del servidor de secreto maestro](../technical-guides/clustering-the-master-secret-server.md)|  
|Asegúrese de que las bases de datos de BizTalk Server están agrupados en servicios de SQL Server (comprobación de confiabilidad).|[Agrupación en clústeres de las bases de datos de BizTalk Server](../technical-guides/clustering-the-biztalk-server-databases2.md)|  
|Asegúrese de que al menos dos servidores físicos BizTalk forman parte del grupo de BizTalk (comprobación de confiabilidad).|[Asegurarse de varios servidores forman parte de un grupo de BizTalk](../technical-guides/maintaining-reliability.md#BKMK_BTSGrp)|  
|Determinar si se está usando cualquier código inestable y si es así, usar hosts independientes (comprobación de confiabilidad).|[Alta disponibilidad para los hosts de BizTalk](../technical-guides/high-availability-for-biztalk-hosts.md)|  
|Realice pruebas funcionales de todas las aplicaciones nuevas de BizTalk (comprobación de confiabilidad).|-   [Probar una aplicación](../technical-guides/testing-an-application.md)<br />-   [Tareas de ensayo para la implementación de aplicación de BizTalk](../core/staging-tasks-for-biztalk-application-deployment.md)|  
|Configurar y programar trabajos de copia de seguridad BizTalk Server (comprobación de confiabilidad).|-   [Cómo configurar el trabajo de copia de seguridad de BizTalk Server](../core/how-to-configure-the-backup-biztalk-server-job.md)<br />-   [Cómo programar el trabajo de copia de seguridad de BizTalk Server](../core/how-to-schedule-the-backup-biztalk-server-job.md)|  
|Asegúrese de que la versión correcta de un conjunto de ensamblados se instala en cada equipo de BizTalk (comprobación de integridad).|Use la **Comprobador de ensamblado de BizTalk y GAC remoto** herramienta (BTSAssemblyChecker.exe) para comprobar las versiones de ensamblados implementados en la base de datos de administración de BizTalk y para comprobar que están registrados correctamente en la GAC en todos los [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos. Puede usar esta herramienta para comprobar que todos los ensamblados que contienen los artefactos de una aplicación de BizTalk están instalados en todos los nodos de BizTalk. La herramienta es especialmente útil en combinación con una estrategia de control de versiones sólido para comprobar que la versión correcta de un conjunto de ensamblados está instalada en cada equipo de BizTalk, sobre todo cuando se utiliza el enfoque de implementación en paralelo. La herramienta está disponible con los medios de instalación de BizTalk Server en Support\Tools\x86\BTSAssemblyChecker.exe.|  
|Determinar si hay cualquier innecesarias aplicaciones, artefactos y configuraciones (comprobación de administración) de BizTalk.|-Quitar todos los innecesarios BizTalk aplicaciones, artefactos y configuraciones.<br />-Para obtener más información acerca de cómo quitar una aplicación de BizTalk o un artefacto mediante la herramienta de línea de comandos de BTSTask vea [comando RemoveApp](../core/removeapp-command.md).<br />-Para obtener más información acerca de cómo quitar un artefacto de una aplicación mediante la consola de administración de BizTalk Server o la herramienta de línea de comandos de BTSTask, vea [cómo quitar un artefacto de una aplicación](../core/how-to-remove-an-artifact-from-an-application.md).|  
|Compruebe la consola de administración de BizTalk Server para que los cambios no aprobado (comprobación de administración).|[Uso de la consola de administración de BizTalk Server](../core/using-the-biztalk-server-administration-console.md)|  
|Busque BTSNTSvc.exe.config las modificaciones no autorizadas (comprobación de administración).|[BTSNTSvc.exe.config (archivo)](../core/btsntsvc-exe-config-file.md)|  
|Compruebe las claves del registro relacionadas con el servidor BizTalk Server para las modificaciones no autorizadas (comprobación de administración).|Artículo de Microsoft Knowledge Base 256986 [información de registro de Windows para los usuarios avanzados](https://support.microsoft.com/kb/256986)|  
|Ejecutar el analizador de procedimientos recomendados para el servidor BizTalk Server (comprobación de administración).|[Analizador de procedimientos recomendados de BizTalk Server](https://www.microsoft.com/download/details.aspx?id=43382)|  
|Asegúrese de tener instaladas el service Pack más recientes y las actualizaciones (comprobación de seguridad y administración).|[Microsoft Update](https://support.microsoft.com/help/12373/windows-update-faq)|  
|Asegúrese de que los artefactos para diferentes socios comerciales no están instalados en el mismo host (comprobación de seguridad).|[Configuración de hosts e instancias de host](../technical-guides/configuring-hosts-and-host-instances.md)|  
|Asegúrese de que BizTalk Server use solo de nivel de dominio a los usuarios y grupos (comprobación de seguridad).|[Grupos de dominio](../core/domain-groups.md)|  
|Asegúrese de que está habilitada la configuración de seguridad de MSDTC (comprobación de seguridad).|Vea **establecer las opciones de configuración de seguridad de MSDTC** en [solución de problemas con MSDTC](../core/troubleshooting-problems-with-msdtc.md).|  
|Determinar si el intervalo de actualización de caché de BizTalk Server debe ser mayor (comprobación de rendimiento).|[Cómo ajustar el intervalo de actualización de la caché de configuración](../technical-guides/how-to-adjust-the-configuration-cache-refresh-interval.md)|  
|Determinar si las opciones de limitación de cada host deben ser ajustado (comprobación de rendimiento).|-Para obtener información acerca de la limitación de host entrante y saliente, vea [¿qué es la limitación de Host?](../core/what-is-host-throttling.md).<br />-Para obtener información acerca de los desencadenadores, acciones y estrategias de mitigación para la limitación de entrada y salida, vea **limitación desencadenadores de condiciones, acciones y estrategias de mitigación** en [cómo BizTalk Server implementa Limitación de host](../core/how-biztalk-server-implements-host-throttling.md).|  
|Determinar si está habilitado seguimiento innecesario, como orquestaciones, forma y (comprobación de rendimiento) de seguimiento de eventos de motor de reglas de negocios (BRE).|-   [Cómo deshabilitar el seguimiento](../technical-guides/how-to-disable-tracking.md)<br />-   [Planeación de seguimiento](../technical-guides/planning-for-tracking.md)<br />-   [Prácticas recomendadas para seguimiento](../technical-guides/planning-for-tracking.md#BKMK_TrackingBP)|  
|Determina si están usando un host dedicado para realizar el seguimiento de mantenimiento (comprobación de rendimiento).|[Configuración de un host de seguimiento dedicado](../technical-guides/configuring-a-dedicated-tracking-host.md)|  
|Comprobar los tamaños de base de datos de BizTalk Server para una tendencia creciente (comprobación de rendimiento).|-Para obtener más información acerca de cómo ajustar el tamaño de la base de datos de seguimiento, vea [directrices de tamaño de base de datos de seguimiento](../core/tracking-database-sizing-guidelines.md).<br />-Para obtener más información acerca de cómo ajustar el tamaño de las bases de datos de cuadro de mensajes y BizTalkDTADb, BAMPrimaryImport, consulte [identificar cuellos de botella de rendimiento](../core/identifying-performance-bottlenecks.md).|  
  
## <a name="see-also"></a>Vea también  
 [Listas de comprobación de mantenimiento rutinario](../technical-guides/routine-maintenance-checklists.md)
