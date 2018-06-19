---
title: Tareas de supervisión rutinaria | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2f9f56a-c839-4108-933d-69b00a1e3817
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d91a49393e2b43c9cf39add35e06c5bd864782e8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22301908"
---
# <a name="routine-monitoring-tasks"></a>Tareas rutinarias de supervisión
Realizar las siguientes tareas de supervisión de forma programada con regularidad te ayudará a mantener su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aplicaciones e infraestructura operativamente listo.  
  
## <a name="daily-monitoring-tasks"></a>Tareas de supervisión diarias  
  
-   Revisar todas las alertas abiertas.  
  
-   Use la **concentrador de grupo** página en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración para investigar la orquestación, puerto y errores de mensaje. El **concentrador de grupo** página proporciona acceso al estado actual en tiempo real del sistema, acceso a datos en la base de datos de cuadro de mensajes. Puede ver todas las instancias de servicio, como orquestaciones, puertos y mensajería, junto con sus mensajes asociados. Mediante el **concentrador de grupo** página puede realizar las siguientes actividades:  
  
    -   Vea actualmente ejecutando instancias de servicio, como orquestaciones y mensajería y sus mensajes asociados.  
  
    -   Buscar una vista de los datos actuales y el estado en tiempo real del sistema en la base de datos de cuadro de mensajes.  
  
    -   Suspender, finalizar y reanudar instancias de servicio.  
  
     Para obtener más información sobre el uso de la **concentrador de grupo** página, vea [http://go.microsoft.com/fwlink/?LinkId=155281](http://go.microsoft.com/fwlink/?LinkId=155281).  
  
-   Revisar las advertencias (opcional).  
  
 Para obtener más información, consulte [lista de comprobación: realizar comprobaciones de mantenimiento diario](../technical-guides/checklist-performing-daily-maintenance-checks.md).  
  
## <a name="weekly-monitoring-tasks"></a>Tareas semanales de supervisión  
  
-   Revise los registros de eventos al menos una vez por semana. La razón de esta tarea es evitar problemas, como errores de DBNetLib pasar desapercibidos. Interrupción del servicio podría pasar desapercibido, a menos que tenga un sistema de una latencia muy baja. Sin embargo, algunos de estos errores pueden indicar un problema más grande (por ejemplo, hay demasiados hosts o servidores de BizTalk Server para el número de cuadros de mensaje, problemas de rendimiento en el cuadro de SQL, etcetera).  
  
 Para obtener más información, consulte [lista de comprobación: realizar comprobaciones de mantenimiento semanal](../technical-guides/checklist-performing-weekly-maintenance-checks.md).  
  
## <a name="as-needed-tasks"></a>Tareas como sea necesario  
  
-   Modificar las reglas para personalizar la supervisión de su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aplicaciones e infraestructura.  
  
-   Ejecute la herramienta de análisis de registros de rendimiento (PAL). Si su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementación es bastante constante (por ejemplo, socios comerciales nuevos no se agregan habitualmente, código nuevo se ha implementado), puede ejecutar Perfmon y PAL una vez por trimestre o incluso cada seis meses. Si su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cambios de implementación con más frecuencia, puede que desee ejecutar Perfmon y PAL cada dos meses para comparar una línea base. Para obtener más información acerca de la PAL, vea [mediante la herramienta de análisis de rendimiento de registros (PAL)](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md).  
  
-   Monitor de rendimiento de ejecución cada cierto número de meses a una vez por trimestre o incluso cada seis meses según el número de cambios se producen en su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementación.  
  
-   Ejecutar el analizador de procedimientos recomendados de BizTalk Server cuando el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cambios de implementación (por ejemplo, la adición de nuevas aplicaciones) o la creación de nuevos hosts. Puede descargar el analizador de procedimientos recomendados de BizTalk Server en [http://go.microsoft.com/fwlink/?LinkId=83317](http://go.microsoft.com/fwlink/?LinkId=83317).  
  
-   Ejecute el [herramienta BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=151930) (http://go.microsoft.com/fwlink/?LinkId=151930). Esta herramienta analiza BizTalk MessageBox y otras bases de datos y genera un informe HTML que contiene advertencias, si cualquier y otra información relacionada con las bases de datos.  
  
    > [!TIP]  
    >  También puede guardar los informes para su uso posterior. Estos informes pueden ser útiles al solucionar problemas relacionados con la aplicación de BizTalk.  
  
    > [!NOTE]  
    >  Uso de esta herramienta no es compatible con Microsoft y Microsoft no otorga ninguna garantía sobre la idoneidad de este programa. La utilización de este programa queda bajo su propia responsabilidad.  
  
-   Ejecute el [herramienta terminador](http://go.microsoft.com/fwlink/?LinkId=151931) (http://go.microsoft.com/fwlink/?LinkId=151931). Esta herramienta permite a los usuarios a resolver fácilmente los problemas identificados por la herramienta de BizTalk MsgBoxViewer. Para obtener más información acerca de cómo la herramienta de terminador se integra con la herramienta de BizTalk MsgBoxViewer, consulte [utilizando el terminador de BizTalk para resolver los problemas identificados por BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=151932)(http://go.microsoft.com/fwlink/?LinkId=151932).  
  
    > [!NOTE]  
    >  Uso de esta herramienta no es compatible con Microsoft y Microsoft no otorga ninguna garantía sobre la idoneidad de este programa. La utilización de este programa queda bajo su propia responsabilidad.  
  
## <a name="annual-monitoring-tasks"></a>Tareas de supervisión anuales  
  
-   Revise la eficacia de la supervisión de su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aplicaciones e infraestructura.  
  
-   Crear un plan para realizar los cambios necesarios en la supervisión.  
  
## <a name="see-also"></a>Vea también  
 [Listas de comprobación de mantenimiento rutinarias](../technical-guides/routine-maintenance-checklists.md)