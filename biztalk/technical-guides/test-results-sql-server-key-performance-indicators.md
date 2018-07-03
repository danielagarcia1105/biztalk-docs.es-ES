---
title: 'Los resultados de pruebas: Indicadores clave de rendimiento SQL Server | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2459ee6d-7a75-4338-ba5c-f42ab673ab87
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed7f1348a23e6c4b145748ccfc0832c97648bdff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007517"
---
# <a name="test-results-sql-server-key-performance-indicators"></a>Los resultados de pruebas: Indicadores clave de rendimiento SQL Server
En este tema se resume a SQL Server Performance indicadores clave (KPI) observado durante los escenarios de prueba. Estas pruebas evalúan los KPI de SQL Server siguientes:  
  
-   Utilización del procesador de SQL, medido por la **\SQL\Processor(_Total)\\% Processor Time** contador del monitor de rendimiento.  
  
-   El número de lotes de comandos de Transact-SQL recibidas por segundo, medido por la **\SQL Server:SQL Statistics\Batch solicitudes/seg.** contador del monitor de rendimiento.  
  
## <a name="summary-of-sql-server-key-performance-indicators"></a>Resumen de indicadores clave de rendimiento de SQL Server  
 Para cada escenario de las máquinas físicas estaban restringidas para que el número de procesadores lógicos y los procesadores virtuales era equivalente. Esto se hacía mediante los conmutadores de boot.ini /maxmem y/numproc. Para obtener más información sobre el uso de estos modificadores, vea "Referencia de las opciones de arranque INI" en [ http://go.microsoft.com/fwlink/?LinkId=122139 ](http://go.microsoft.com/fwlink/?LinkId=122139).  
  
 **Comparación de SQL Server indicadores clave de rendimiento:** [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] utilización del procesador, medido por **\SQL\Processor(_Total)\\% Processor Time** contador era aproximadamente el mismo en todas las pruebas entornos, comprendido entre un mínimo de 88% y un valor alto de % 90.1.   Sin embargo hay una diferencia significativa entre el **\SQL Server:SQL Statistics\Batch solicitudes/seg.** medido en el entorno consolidado (4520) y el **\SQL Server:SQL Statistics\Batch solicitudes/seg.** medido en el entorno físico (6350). El **\SQL Server:SQL Statistics\Batch solicitudes/seg.** contador del monitor de rendimiento proporciona un buen indicador de cuánto trabajo se realiza en SQL Server. La reducción de solicitudes de lotes/seg cuando SQL Server se está ejecutando en un entorno de Hyper-V se puede atribuir a Hyper-V requerida la sobrecarga de CPU.  
  
 Sin embargo, hay una diferencia significativa entre el **\SQL Server:SQL Statistics\Batch solicitudes/seg.** medido en el entorno consolidado (4520) y el **\SQL Server:SQL Statistics\Batch solicitudes/seg.**  medido en el entorno físico (6350). El **\SQL Server:SQL Statistics\Batch solicitudes/seg.** contador del monitor de rendimiento proporciona un buen indicador de cuánto trabajo se realiza en SQL Server. La reducción de solicitudes de lotes/seg cuando SQL Server se está ejecutando en un entorno de Hyper-V se puede atribuir a Hyper-V requerida la sobrecarga de CPU.  
  
 Siga estos pasos para aumentar el rendimiento de SQL Server que se ejecuta en una máquina virtual de Hyper-V, medido por la **\SQL Server:SQL Statistics\Batch solicitudes/seg.** contador del monitor de rendimiento:  
  
1. **Asignar discos VHD fijos adicionales con controladores virtuales dedicados y canales –** dedicado de asignación de más discos VHD fijos mediante controladores virtuales y canales, aumentará el rendimiento de disco frente al uso de un único disco VHD.  
  
2. **Optimizar el rendimiento de red –** siga los pasos descritos en la sección "Optimizar el rendimiento de la red" de [lista de comprobación: optimización del rendimiento en Hyper-V](~/technical-guides/checklist-optimizing-performance-on-hyper-v.md). Al ejecutar varias máquinas virtuales de Hyper-V en el mismo host de Hyper-V resulta de especial importancia para seguir las recomendaciones en la sección "Configurar Hyper-V Virtual Machines que se ejecutan en el mismo Hyper-V host de equipo para usar una red Virtual de privada" de [optimizaciones de red](../technical-guides/network-optimizations.md).  
  
   Dada la naturaleza sin estado de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]adicionales [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] máquinas virtuales pueden agregarse fácilmente en el entorno según sea necesario para proporcionar escalado horizontal y aumentar el rendimiento general del sistema.  
  
   El siguiente gráfico muestra el rendimiento de SQL Server en las diferentes plataformas de prueba:  
  
   ![Indicadores clave de rendimiento de SQL](../technical-guides/media/sqlkpi.gif "SQLKPI")  
   Indicadores de rendimiento clave de SQL  
  
   En la tabla siguiente se muestra el rendimiento relativo de los recopilados KPI para cada configuración. Cada conjunto de resultados se calcula como un porcentaje de la configuración de línea de base KPI  
  
|KPI|SQL de BizTalk física o virtual|Virtual de SQL de BizTalk y virtuales en Hosts independientes|Virtual de BizTalk/Virtual SQL en el entorno consolidado|  
|---------|-----------------------------------|----------------------------------------------------|--------------------------------------------------------------|  
|\SQL\Processor(_Total)\\% de tiempo de procesador|97.7%|98.4%|99.9%|  
|\Sql server: SQL Statistics\Batch solicitudes/seg.|97.1%|83.3%|71.2%|  
  
 Para obtener más información acerca de cómo evaluar el rendimiento de E/S de disco, consulte el **medir el rendimiento de E/S de disco** sección del tema [lista de comprobación: medir el rendimiento en Hyper-V](../technical-guides/checklist-measuring-performance-on-hyper-v.md).  
  
 Para obtener más información sobre los procedimientos recomendados cuando se ejecuta SQL Server 2008 en un entorno de Hyper-V, consulte las notas del producto "Ejecutando SQL Server 2008 in a Hyper-V entorno – mejores prácticas recomendadas y recomendaciones de rendimiento" disponible para su descarga en [ http://go.microsoft.com/fwlink/?LinkId=144622 ](http://go.microsoft.com/fwlink/?LinkId=144622).