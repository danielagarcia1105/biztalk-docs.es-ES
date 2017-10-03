---
title: "Herramientas y utilidades para la solución de problemas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56b0946a-56de-47cd-95d9-365722cdbaed
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 086c7144d39b459a342e3c4f6c5c87f669fffedc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="tools-and-utilities-for-troubleshooting"></a>Herramientas y utilidades para solucionar problemas
En este tema se describe varias herramientas y utilidades que pueden resultar útiles para diagnosticar la causa de un problema en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] dependencia o un componente.  
  
|Solucionar problemas|Herramienta|Utilice|  
|---------------------|----------|---------|  
|**Solución de problemas de SQL Server**|Monitor de actividad SQL|Monitor de actividad de SQL Server 2008 proporciona información acerca de los procesos de SQL Server y cómo estos procesos afectan a la instancia actual de SQL Server. Para obtener más información sobre el Monitor de actividad de SQL Server 2008, consulte [Monitor de actividad](http://go.microsoft.com/fwlink/?LinkId=146355) (http://go.microsoft.com/fwlink/?LinkId=146355) en la documentación de SQL Server. Para obtener información acerca de cómo abrir el Monitor de actividad desde SQL Server Management Studio, consulte [Cómo: abrir el Monitor de actividad (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=135094) (http://go.microsoft.com/fwlink/?LinkId=135094) en la documentación de SQL Server.|  
||Recopilación de datos SQL Server 2008|SQL Server 2008 proporciona un recopilador de datos que puede usar para obtener y guardar los datos recopilados de varios orígenes. El recopilador de datos permite usar contenedores de recopilación de datos, lo que permite determinar el ámbito y la frecuencia de recopilación de datos en un equipo que ejecuta SQL Server 2008. Para obtener más información acerca de cómo implementar la recopilación de datos de SQL Server 2008, consulte [la recopilación de datos](http://go.microsoft.com/fwlink/?LinkId=146356) (http://go.microsoft.com/fwlink/?LinkId=146356) en la documentación de SQL Server.|  
||**Solución de problemas relacionados con el rendimiento**|La utilidad de volver a registrar se usa para extraer los contadores de rendimiento de registros creados por el Monitor de rendimiento y convertir los datos en otros formatos, como archivos de texto delimitado por tabulaciones (TSV texto), archivos de texto delimitado por comas (CSV de texto), archivos binarios y las bases de datos SQL. Estos datos, a continuación, se pueden analizar y consultan mediante otras herramientas, como el analizador del registro, para generar estadísticas de indicadores clave de rendimiento (KPI). La utilidad de volver a registrar se proporciona con Windows Server 2003 y versiones posteriores.|  
|Herramientas de análisis de rendimiento de Windows||Herramientas de rendimiento de Windows se ha diseñado para el análisis de una amplia gama de problemas de rendimiento, incluidos los tiempos de inicio de aplicación, problemas de arranque, llamadas a procedimientos aplazados y actividad (DPC e ISR), sistema la capacidad de respuesta de interrupción emite, recursos de aplicación uso y los aluviones de interrupción. Para obtener más información, consulte [Centro para desarrolladores de Windows Performance Analysis](http://go.microsoft.com/fwlink/?LinkId=139763) (http://go.microsoft.com/fwlink/?LinkId=139763).|  
|Pathping||Pathping proporciona información acerca de la posible pérdida de datos en uno o varios saltos de enrutador en la forma de un host de destino. Para ello, pathping envía paquetes de protocolo de mensajes de Control de Internet (ICMP) a cada enrutador en la ruta de acceso. Pathping.exe está disponible con todas las versiones de Windows desde Windows 2000 Server.|  
|IOMeter||IOMeter es una herramienta de código abierto que se usa para medir rendimiento de E/S de disco. Para obtener más información, consulte [IOMeter](http://go.microsoft.com/fwlink/?LinkId=122412) (http://go.microsoft.com/fwlink/?LinkId=122412). **Importante:** no se admite el uso de esta herramienta por Microsoft y Microsoft no otorga ninguna garantía sobre la idoneidad de este programa. La utilización de este programa queda bajo su propia responsabilidad.|  
|**Solución de problemas generales**|: Visor de eventos<br />: Monitor de red<br />-SQL Server Profiler<br />-Editor de consultas SQL Server<br />-DTCTester<br />-DTCPing<br />: Consola de rendimiento<br />-RegMon<br />-FileMon<br />-Herramienta de diagnóstico del Kit de herramientas de diagnóstico IIS de depuración|Vea [herramientas y utilidades que se usan para solucionar problemas de](http://go.microsoft.com/fwlink/?LinkId=154416) (http://go.microsoft.com/fwlink/?LinkId=154416).|  
  
## <a name="see-also"></a>Vea también  
 [Herramientas de prueba](../technical-guides/tools-for-testing.md)   
 [Lista de comprobación: Configuración de BizTalk Server](~/technical-guides/checklist-configuring-biztalk-server.md)