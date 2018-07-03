---
title: Procedimientos recomendados para el mantenimiento de bases de datos de BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93333f41-ee83-4b64-b381-66584a7d5551
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b1d8f03201b04a3be1f7908eaf7e763a4ade226
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981253"
---
# <a name="best-practices-for-maintaining-biztalk-server-databases"></a>Procedimientos recomendados para el mantenimiento de bases de datos de BizTalk Server
Este tema enumeran algunas prácticas recomendadas para el mantenimiento de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos.  
  
- Asegúrese de que el Agente SQL Server se está ejecutando en el servidor SQL Server. Cuando se detiene el Agente SQL Server, no se pueden ejecutar los trabajos de agente SQL Server de BizTalk integrados que son responsables del mantenimiento de base de datos. Este comportamiento hace que el crecimiento de la base de datos, y este crecimiento puede provocar problemas de rendimiento. Para obtener información sobre la supervisión de trabajos del Agente SQL Server, vea [trabajos del agente de supervisión de SQL Server](../technical-guides/monitoring-sql-server-agent-jobs.md).  
  
- Asegúrese de que los archivos LDF de SQL Server y MDF están en unidades independientes. Tener los archivos LDF y MDF para las bases de datos BizTalkMsgBoxDb y BizTalkDTADb en la misma unidad puede producir contención del disco.  
  
- No habilite el cuerpo del mensaje de seguimiento, si no es necesario. Con frecuencia, es posible que desea habilitar el seguimiento de partes de mensaje mientras desarrolla y solución de problemas de una solución. Si es así, asegúrese de que deshabilitar el cuerpo del mensaje de seguimiento cuando haya terminado. Si mantiene el cuerpo del mensaje de seguimiento habilitada, el crecen de las bases de datos de BizTalk Server. Si tiene una necesidad empresarial que requiere que habilite el seguimiento de cuerpos de mensaje, confirme que la **TrackedMessages_Copy_BizTalkMsgBoxDb** y **DTA Purge and Archive** se estén ejecutando trabajos del Agente SQL Server correctamente.  
  
- Normalmente, los registros de transacciones más pequeños provoca un mejor rendimiento. Para mantener los registros de transacciones más pequeñas, configure el **Backup BizTalk Server** trabajo del Agente SQL Server con más frecuencia. Para obtener más información, consulte el [notas de la optimización de base de datos de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=153594) (http://go.microsoft.com/fwlink/?LinkId=153594).  
  
- Use la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Best Practices Analyzer (BPA) para evaluar una existente [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementación. El BPA realiza numerosas comprobaciones relacionadas con la base de datos. Puede descargar la herramienta Best Practices Analyzer de BizTalk Server desde [herramienta Best Practices Analyzer de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=83317) (<http://go.microsoft.com/fwlink/?LinkId=83317>).  
  
## <a name="see-also"></a>Vea también  
 [Lista de comprobación: Mantenimiento y solución de problemas de las bases de datos de BizTalk Server](~/technical-guides/checklist-maintaining-and-troubleshooting-biztalk-server-databases.md)   
 [Tablas de base de datos de BizTalk Server de gran crecimiento](../technical-guides/large-growing-biztalk-server-database-tables.md)