---
title: Prácticas recomendadas para el mantenimiento de bases de datos de servidor BizTalk Server | Documentos de Microsoft
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
ms.openlocfilehash: b5f6cf1fadf5c039c53e6cca46792c4660353d0c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22300004"
---
# <a name="best-practices-for-maintaining-biztalk-server-databases"></a>Prácticas recomendadas para el mantenimiento de bases de datos de servidor BizTalk Server
Este tema enumeran algunas prácticas recomendadas para el mantenimiento de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] las bases de datos.  
  
-   Asegúrese de que el Agente SQL Server se ejecuta en el servidor SQL Server. Cuando se detiene el Agente SQL Server, no se pueden ejecutar los trabajos de agente SQL Server de BizTalk integrados que son responsables de mantenimiento de base de datos. Este comportamiento provoca el crecimiento de la base de datos, y este crecimiento puede provocar problemas de rendimiento. Para obtener información acerca de la supervisión de trabajos del Agente SQL Server, vea [trabajos del agente de supervisión de SQL Server](../technical-guides/monitoring-sql-server-agent-jobs.md).  
  
-   Asegúrese de que los archivos MDF y de SQL Server LDF se encuentran en unidades independientes. Tener los archivos LDF y MDF para las bases de datos BizTalkMsgBoxDb y BizTalkDTADb en la misma unidad está penada por la contención de disco.  
  
-   No habilite el cuerpo del mensaje de seguimiento, si no es necesario. Con frecuencia, puede que desee habilitar el seguimiento de partes de mensaje mientras desarrolla y solucionar problemas de una solución. Si es así, asegúrese de que deshabilitar el seguimiento cuando haya terminado de cuerpos de mensaje. Si mantiene el cuerpo del mensaje de seguimiento habilitado, el crecen de las bases de datos de BizTalk Server. Si tiene una necesidad empresarial que requiere que habilite el seguimiento de cuerpos de mensaje, confirme que la **TrackedMessages_Copy_BizTalkMsgBoxDb** y **DTA Purge and Archive** se estén ejecutando trabajos del Agente SQL Server se estableció correctamente.  
  
-   Normalmente, los registros de transacciones más pequeños causan un mejor rendimiento. Para mantener los registros de transacciones más pequeñas, configurar la **copia de seguridad de BizTalk Server** trabajo del Agente SQL Server para que se ejecute con más frecuencia. Para obtener más información, consulte el [notas del producto BizTalk Server Database Optimization](http://go.microsoft.com/fwlink/?LinkId=153594) (http://go.microsoft.com/fwlink/?LinkId=153594).  
  
-   Use la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Best Practices Analyzer (BPA) para evaluar una existente [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementación. El BPA realiza numerosas comprobaciones relacionadas con la base de datos. Puede descargar la herramienta de BizTalk Server Best Practices Analyzer de [herramienta de BizTalk Server Best Practices Analyzer](http://go.microsoft.com/fwlink/?LinkId=83317) (http://go.microsoft.com/fwlink/?LinkId=83317).  
  
## <a name="see-also"></a>Vea también  
 [Lista de comprobación: Mantenimiento y solución de problemas de las bases de datos de servidor BizTalk Server](~/technical-guides/checklist-maintaining-and-troubleshooting-biztalk-server-databases.md)   
 [Tablas de base de datos de servidor BizTalk Server de gran crecimiento](../technical-guides/large-growing-biztalk-server-database-tables.md)