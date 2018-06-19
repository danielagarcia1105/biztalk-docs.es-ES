---
title: 'Resultados de pruebas: Indicadores clave de rendimiento SQL Server | Documentos de Microsoft'
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
ms.openlocfilehash: 93e1f1bdef55ad726c308902062dccff67eeb170
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302468"
---
# <a name="test-results-sql-server-key-performance-indicators"></a>Resultados de pruebas: Indicadores clave de rendimiento SQL Server
En este tema se resume a SQL Server Performance indicadores clave (KPI) observado durante los escenarios de prueba. Estas pruebas evalúan el KPI de SQL Server siguientes:  
  
-   Utilización del procesador de SQL según lo medido por la **\SQL\Processor(_Total)\\% Processor Time** contador del monitor de rendimiento.  
  
-   El número de lotes de comandos de Transact-SQL recibidos por segundo, medido por la **\SQL Server:SQL Statistics\Batch solicitudes/seg.** contador del monitor de rendimiento.  
  
## <a name="summary-of-sql-server-key-performance-indicators"></a>Resumen de indicadores clave de rendimiento de SQL Server  
 Para cada escenario las máquinas físicas estaban restringidas para que el número de procesadores lógicos y los procesadores virtuales era equivalente. Esto se hacía con los modificadores de boot.ini/maxmem y/numproc. Para obtener más información acerca del uso de estos modificadores, vea "Referencia de opciones de arranque INI" en [http://go.microsoft.com/fwlink/?LinkId=122139](http://go.microsoft.com/fwlink/?LinkId=122139).  
  
 **Comparación de SQL Server indicadores clave de rendimiento:** [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] según lo medido por la utilización del procesador **\SQL\Processor(_Total)\\% Processor Time** contador era aproximadamente el mismo en todos los entornos, comprendido entre un mínimo de 88% y un valor alto de % de 90.1 de prueba.   Sin embargo hay una diferencia significativa entre el **\SQL Server:SQL Statistics\Batch solicitudes/seg.** medido en el entorno consolidado (4520) y la **\SQL Server:SQL Statistics\Batchsolicitudes/segundo** medido en el entorno físico (6350). El **\SQL Server:SQL Statistics\Batch solicitudes/seg.** contador del monitor de rendimiento proporciona un buen indicador de cuánto trabajo se realiza por SQL Server. La reducción de solicitudes de lotes/seg cuando SQL Server se está ejecutando en un entorno de Hyper-V puede deberse a la sobrecarga de CPU necesaria por Hyper-V.  
  
 Sin embargo, hay una diferencia significativa entre el **\SQL Server:SQL Statistics\Batch solicitudes/seg.** medido en el entorno consolidado (4520) y la **\SQL Server:SQL Statistics\Batch solicitudes/seg.**  medido en el entorno físico (6350). El **\SQL Server:SQL Statistics\Batch solicitudes/seg.** contador del monitor de rendimiento proporciona un buen indicador de cuánto trabajo se realiza por SQL Server. La reducción de solicitudes de lotes/seg cuando SQL Server se está ejecutando en un entorno de Hyper-V puede deberse a la sobrecarga de CPU necesaria por Hyper-V.  
  
 Siga estos pasos para aumentar el rendimiento de SQL Server que se ejecuta en una máquina virtual de Hyper-V, medido por la **\SQL Server:SQL Statistics\Batch solicitudes/seg.** contador del monitor de rendimiento:  
  
1.  **Asignar discos VHD fijos adicionales con los controladores virtuales dedicados y canales:** dedicado de asignación de más discos VHD fijos con controladores virtuales y canales, aumentará el rendimiento del disco frente al uso de un solo disco a disco duro virtual.  
  
2.  **Optimizar el rendimiento de red:** siga los pasos descritos en la sección "Optimizar el rendimiento de la red" de [lista de comprobación: optimizar el rendimiento en Hyper-V](~/technical-guides/checklist-optimizing-performance-on-hyper-v.md). Al ejecutar varias máquinas virtuales de Hyper-V en el mismo host de Hyper-V es de particular importancia para seguir las recomendaciones en la sección "Máquinas virtuales de configurar Hyper-V que se ejecutan en el mismo Hyper-V host de equipo para que use una red de Virtual privada" de [optimizaciones de red](../technical-guides/network-optimizations.md).  
  
 Debido a la naturaleza sin estado de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]adicionales [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] máquinas virtuales pueden agregarse fácilmente en el entorno según sea necesario para proporcionar escalado horizontal y aumentar el rendimiento general del sistema.  
  
 El siguiente gráfico muestra el rendimiento de SQL Server en las diferentes plataformas de prueba:  
  
 ![Indicadores clave de rendimiento de SQL](../technical-guides/media/sqlkpi.gif "SQLKPI")  
Indicadores de rendimiento clave de SQL  
  
 La siguiente tabla muestra el rendimiento relativo de recopilados de KPI para cada configuración. Cada conjunto de resultados se calcula como un porcentaje de la configuración de línea de base KPI  
  
|KPI|Virtual de BizTalk o física SQL|Virtual SQL de BizTalk y virtuales en Hosts independientes|Virtual de BizTalk/Virtual de SQL en el entorno consolidado|  
|---------|-----------------------------------|----------------------------------------------------|--------------------------------------------------------------|  
|\SQL\Processor(_Total)\\% de tiempo de procesador|97.7%|98.4%|99.9%|  
|\Sql server: SQL Statistics\Batch solicitudes/seg.|97.1%|83.3%|71.2%|  
  
 Para obtener más información acerca de cómo evaluar el rendimiento de E/S de disco, consulte el **medir el rendimiento de E/S de disco** sección del tema [lista de comprobación: medir el rendimiento en Hyper-V](../technical-guides/checklist-measuring-performance-on-hyper-v.md).  
  
 Para obtener más información acerca de las prácticas recomendadas cuando se ejecuta SQL Server 2008 en un entorno de Hyper-V, vea las notas del producto "Ejecuta SQL Server 2008 in a Hyper-V entorno – y rendimiento recomendaciones" disponible para su descarga en [http ¿: / / go.microsoft.com/fwlink/? LinkId = 144622](http://go.microsoft.com/fwlink/?LinkId=144622).