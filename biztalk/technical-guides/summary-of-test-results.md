---
title: Resumen de resultados de pruebas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d95fbaa6-0e07-4086-bea2-0577d39ae7cd
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad5550a073101e2a30555f90ad6bd879edff3a79
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997965"
---
# <a name="summary-of-test-results"></a>Resumen de resultados de pruebas
En este tema se resume los resultados de los escenarios de prueba.  
  
## <a name="summary-of-test-results"></a>Resumen de resultados de pruebas  
 El [probar el rendimiento de BizTalk Server Virtualization](../technical-guides/testing-biztalk-server-virtualization-performance.md) sección de esta guía describe la aplicación de prueba utilizado y la configuración de los diversos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entornos en la que se ejecutó la aplicación de prueba. Comparar el rendimiento de las pruebas se realizaron un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  /  [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] entorno que el rendimiento del entorno que se ejecutan en máquinas virtuales de Hyper-V se ejecuta en hardware físico. Indicadores clave de rendimiento (KPI) mide durante las pruebas incluyen lo siguiente:  
  
1. Mide el rendimiento de los mensajes en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos.  
  
2. Latencia de solicitud y respuesta se mide en el cliente de prueba de Visual Studio que envían las solicitudes sincrónicas a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
3. Uso del procesador y las solicitudes por lotes por segundo que se observan en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  
  
4. Rendimiento de la red se observa en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipos.  
  
5. Memoria disponible para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipos.  
  
### <a name="throughput-comparison-sample-results"></a>Resultados del ejemplo de comparación de rendimiento  
 Con todos los demás factores son iguales, el rendimiento de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución, medido por el "BizTalk: mensajería/documentos procesadas por segundo" contador del monitor de rendimiento tiene un rango de 67% a % 94,3 del rendimiento alcanzables cuando tanto el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] los equipos y la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] se instalaron los equipos del entorno en el hardware físico.  
  
 Cuando el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] los equipos del entorno se han instalado en las máquinas virtuales de Hyper-V, el rendimiento de la solución se ha observado a rechazar considerablemente, esta reducción en el rendimiento se puede atribuir a la sobrecarga de CPU necesaria por Hyper-V.  
  
### <a name="latency-comparison-sample-results"></a>Resultados de ejemplo de comparación de latencia  
 Con todos los demás factores son iguales, cuando los equipos de BizTalk Server utilizados en el entorno de BizTalk Server se ejecuta en máquinas virtuales de Hyper-V, la latencia de la solución de BizTalk Server, medido por el "BizTalk: latencia de latencia de solicitud-respuesta (s de mensajería ) "contador del monitor de rendimiento tiene un rango de 66.9% 94,3% de la latencia alcanzables cuando los equipos de BizTalk Server utilizados en el entorno de BizTalk Server se instala en hardware físico.  
  
 Cuando el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] los equipos del entorno se han instalado en las máquinas virtuales de Hyper-V, el rendimiento de la solución se ha observado a rechazar considerablemente, esta reducción en el rendimiento se puede atribuir a la sobrecarga de CPU necesaria por Hyper-V en el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] máquinas virtuales.  
  
### <a name="sql-server-processor-utilization-and-batch-requests-per-second-sample-results"></a>Utilización del procesador SQL Server y las solicitudes de Batch por segundo resultados de ejemplo  
 Utilización del procesador de SQL Server, medido por \SQL\Processor(_Total)\\contador % Processor Time era aproximadamente el mismo en todos los entornos de prueba, comprendido entre un mínimo de 88% y un valor alto de % 90.1. Hay sin embargo, una diferencia significativa entre el \SQL Server:SQL Statistics\Batch solicitudes/seg. mide en el entorno consolidado (4520) y el \SQL Server:SQL Statistics\Batch solicitudes/seg. mide en el entorno físico (6350). El \SQL Server:SQL Statistics\Batch contador del monitor de rendimiento de solicitudes/seg. proporciona un buen indicador de cuánto trabajo se realiza en SQL Server. La reducción de solicitudes de lotes/seg cuando SQL Server se está ejecutando en un entorno de Hyper-V se puede atribuir a Hyper-V requerida la sobrecarga de CPU.  
  
### <a name="biztalk-server-and-sql-server-network-throughput-sample-results"></a>Resultados de ejemplo de rendimiento red SQL Server y BizTalk Server  
 Rendimiento de la red para que BizTalk Server que se ejecutan en máquinas virtuales de Hyper-V se ha observado al intervalo de aproximadamente 70-96% del rendimiento de red conseguido en los servidores físicos de BizTalk, según el entorno de prueba determinada. Rendimiento de red de SQL Server que se ejecuta en una máquina virtual de Hyper-V se ha observado al intervalo de aproximadamente 68 al 81% del rendimiento de red logrado en físico SQL Server, vuelva a según el entorno de prueba determinada. La diferencia en el rendimiento de red observado se puede atribuir a los requisitos de recursos del hipervisor de Hyper-V.  
  
### <a name="biztalk-server-and-sql-server-available-memory-sample-results"></a>Resultados de ejemplo de memoria disponible de BizTalk Server y SQL Server  
 Memoria total disponible para SQL Server y BizTalk Server, medido por el contador del monitor de rendimiento de \Memory\Available Mbytes era bastante coherente en todos los escenarios de prueba.