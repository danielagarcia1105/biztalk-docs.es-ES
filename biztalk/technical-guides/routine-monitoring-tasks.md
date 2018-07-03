---
title: Rutina de supervisión de tareas | Microsoft Docs
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
ms.openlocfilehash: d500e79cdf20c6a1914708976101715c2f00ae69
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001661"
---
# <a name="routine-monitoring-tasks"></a>Tareas rutinarias de supervisión
Realizar las siguientes tareas de supervisión de forma programada con regularidad le ayudarán a mantener su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aplicaciones e infraestructura operativamente listo.  
  
## <a name="daily-monitoring-tasks"></a>Tareas de supervisión diarias  
  
- Revisar todas las alertas abiertas.  
  
- Use la **concentrador de grupo** página en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración para investigar la orquestación, puerto y errores de mensaje. El **concentrador de grupo** página proporciona acceso al estado actual en tiempo real del sistema, acceso a datos en la base de datos de cuadro de mensajes. Puede ver todas las instancias de servicio, como orquestaciones, puertos y mensajería, junto con sus mensajes asociados. Mediante el **concentrador de grupo** página puede realizar las siguientes actividades:  
  
  - Ver ejecutando instancias de servicio, como las orquestaciones y mensajería y sus mensajes asociados.  
  
  - Buscar una vista de los datos actuales y el estado en tiempo real del sistema en la base de datos de cuadro de mensajes.  
  
  - Suspender, finalizar y reanudar instancias de servicio.  
  
    Para obtener más información sobre el uso de la **concentrador de grupo** página, vea [ http://go.microsoft.com/fwlink/?LinkId=155281 ](http://go.microsoft.com/fwlink/?LinkId=155281).  
  
- Revisar las advertencias (opcional).  
  
  Para obtener más información, consulte [lista de comprobación: realizar comprobaciones de mantenimiento diario](../technical-guides/checklist-performing-daily-maintenance-checks.md).  
  
## <a name="weekly-monitoring-tasks"></a>Tareas semanales de supervisión  
  
- Revise los registros de eventos al menos una vez por semana. El motivo de esta tarea es para evitar problemas, como errores de DBNetLib pasar inadvertidos. Interrupción del servicio podría pasar desapercibida a menos que tenga un sistema de latencia muy baja. Sin embargo, algunos de estos errores pueden indicar un problema mayor (por ejemplo, muchos hosts o servidores de BizTalk Server para el número de cuadros de mensaje, problemas de rendimiento en el cuadro de SQL, etcetera).  
  
  Para obtener más información, consulte [lista de comprobación: realizar comprobaciones de mantenimiento semanal](../technical-guides/checklist-performing-weekly-maintenance-checks.md).  
  
## <a name="as-needed-tasks"></a>Tareas según sea necesario  
  
- Modificar las reglas para personalizar la supervisión de su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aplicaciones e infraestructura.  
  
- Ejecute la herramienta de análisis de registros de rendimiento (PAL). Si su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementación es bastante constante (por ejemplo, no se agregan nuevos asociados comerciales de forma rutinaria, nuevo código se ha implementado), podría ejecutar Perfmon y PAL una vez por trimestre o incluso cada seis meses. Si su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cambios en la implementación con más frecuencia, es posible que desea ejecutar el Monitor de rendimiento y PAL cada par de meses que se compara con una línea de base. Para obtener más información sobre la PAL, vea [mediante la herramienta de análisis de rendimiento de los registros (PAL)](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md).  
  
- Monitor de rendimiento de ejecución se producen cada pocos meses, a una vez por trimestre o incluso cada seis meses según el número de cambios en su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementación.  
  
- Ejecutar BizTalk Server Best Practices Analyzer cuando la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cambios de implementación (por ejemplo, la adición de nuevas aplicaciones) o la creación de nuevos hosts. Puede descargar BizTalk Server Best Practices Analyzer en [ http://go.microsoft.com/fwlink/?LinkId=83317 ](http://go.microsoft.com/fwlink/?LinkId=83317).  
  
- Ejecute el [herramienta BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=151930) (http://go.microsoft.com/fwlink/?LinkId=151930). Esta herramienta analiza BizTalk MessageBox y otras bases de datos y genera un informe HTML que contiene las advertencias, si cualquier y otra información relacionada con las bases de datos.  
  
  > [!TIP]  
  >  También puede guardar los informes para su uso posterior. Estos informes pueden ser útiles al solucionar problemas con la aplicación de BizTalk.  
  
  > [!NOTE]  
  >  Uso de esta herramienta no es compatible con Microsoft y Microsoft no ofrece ninguna garantía sobre la idoneidad de este programa. La utilización de este programa queda bajo su propia responsabilidad.  
  
- Ejecute el [herramienta terminador](http://go.microsoft.com/fwlink/?LinkId=151931) (http://go.microsoft.com/fwlink/?LinkId=151931). Esta herramienta permite a los usuarios fácil de resolver los problemas detectados por la herramienta BizTalk MsgBoxViewer. Para obtener más información acerca de cómo la herramienta terminador se integra con la herramienta BizTalk MsgBoxViewer, consulte [utilizando el terminador de BizTalk para resolver los problemas identificados por BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=151932)(http://go.microsoft.com/fwlink/?LinkId=151932).  
  
  > [!NOTE]  
  >  Uso de esta herramienta no es compatible con Microsoft y Microsoft no ofrece ninguna garantía sobre la idoneidad de este programa. La utilización de este programa queda bajo su propia responsabilidad.  
  
## <a name="annual-monitoring-tasks"></a>Tareas de supervisión anuales  
  
- Revisar la eficacia de la supervisión de su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aplicaciones e infraestructura.  
  
- Cree un plan para realizar los cambios necesarios en la supervisión.  
  
## <a name="see-also"></a>Vea también  
 [Listas de comprobación de mantenimiento rutinario](../technical-guides/routine-maintenance-checklists.md)