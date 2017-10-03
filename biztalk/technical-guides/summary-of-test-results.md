---
title: Resumen de resultados de pruebas | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d95fbaa6-0e07-4086-bea2-0577d39ae7cd
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2eebcdef457716cab9ad61415bf3fe46db301b55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="summary-of-test-results"></a>Resumen de resultados de pruebas
En este tema se resume los resultados de los escenarios de prueba.  
  
## <a name="summary-of-test-results"></a>Resumen de resultados de pruebas  
 El [probar el rendimiento de virtualización de BizTalk Server](../technical-guides/testing-biztalk-server-virtualization-performance.md) sección de esta guía describe la aplicación de prueba que se utilizan y la configuración de los diversos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entornos con el que se ejecutó la aplicación de prueba. Las pruebas se realizan para comparar el rendimiento de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  /  [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] ejecutándose en hardware físico para el rendimiento del entorno que se ejecutan en máquinas virtuales de Hyper-V de entorno. Indicadores clave de rendimiento (KPI) mide durante las pruebas incluyen lo siguiente;  
  
1.  Mide el rendimiento de los mensajes en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos.  
  
2.  Latencia de solicitudes y respuestas se mide en el cliente de prueba de Visual Studio que envían las solicitudes sincrónicas a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
3.  Utilización del procesador y las solicitudes por lotes por segundo observado en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  
  
4.  Rendimiento de la red observado en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipos.  
  
5.  Memoria disponible para la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipos.  
  
### <a name="throughput-comparison-sample-results"></a>Resultados del ejemplo de comparación de rendimiento  
 Con todos los demás factores son iguales, el rendimiento de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución según lo medido por la "BizTalk: mensajería/documentos procesados/seg." contador del monitor de rendimiento tiene un rango de 67% 94,3% del rendimiento de la alcanzables cuando tanto el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos y la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipos del entorno se instalaron en el hardware físico.  
  
 Cuando el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipos del entorno se han instalado en máquinas virtuales de Hyper-V, el rendimiento de la solución se observó para rechazar significativamente, esta reducción en el rendimiento puede deberse a la sobrecarga de CPU necesaria por Hyper-V.  
  
### <a name="latency-comparison-sample-results"></a>Resultados de ejemplo de comparación de latencia  
 Con todos los demás factores son iguales, cuando los equipos de BizTalk Server utilizados en el entorno de BizTalk Server se ejecuta en máquinas virtuales de Hyper-V, la latencia de la solución de BizTalk Server según lo medido por la "BizTalk: latencia de latencia de solicitud-respuesta (s de mensajería ) "contador del monitor de rendimiento tiene un rango de 66.9% 94,3% de la latencia alcanzables cuando los equipos de BizTalk Server utilizados en el entorno de BizTalk Server se instala en hardware físico.  
  
 Cuando el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipos del entorno se han instalado en máquinas virtuales de Hyper-V, el rendimiento de la solución se observó para rechazar significativamente, esta reducción en el rendimiento puede deberse a la sobrecarga de CPU necesaria por Hyper-V en el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] máquinas virtuales.  
  
### <a name="sql-server-processor-utilization-and-batch-requests-per-second-sample-results"></a>Utilización del procesador SQL Server y las solicitudes de lotes por segundo resultados del ejemplo  
 Utilización del procesador de SQL Server según lo medido por \SQL\Processor(_Total)\\contador % de tiempo de procesador era aproximadamente el mismo en todos los entornos de prueba, comprendido entre un mínimo de 88% y un valor alto de % 90.1. Hay sin embargo, una diferencia significativa entre el \SQL Server:SQL Statistics\Batch solicitudes/seg. medido en el entorno consolidado (4520) y la \SQL Server:SQL Statistics\Batch solicitudes/seg. se mide en el entorno físico (6350). El \SQL Server:SQL Statistics\Batch contador del monitor de rendimiento de solicitudes/seg. proporciona un buen indicador de cuánto trabajo se realiza por SQL Server. La reducción de solicitudes de lotes/seg cuando SQL Server se está ejecutando en un entorno de Hyper-V puede deberse a la sobrecarga de CPU necesaria por Hyper-V.  
  
### <a name="biztalk-server-and-sql-server-network-throughput-sample-results"></a>Resultados de ejemplo del rendimiento de red SQL Server y BizTalk Server  
 Rendimiento de la red para que BizTalk Server que se ejecutan en máquinas virtuales de Hyper-V se observó en el intervalo de aproximadamente 70-96% del rendimiento de red de los servidores físicos de BizTalk, dependiendo del entorno de prueba determinada. Rendimiento de la red de SQL Server que se ejecuta en una máquina virtual de Hyper-V se observó en el intervalo de 68 y 81% aproximadamente del rendimiento de red obtenido en el servidor físico de SQL, nuevo según el entorno de prueba determinada. Las diferencias en el rendimiento de la red observado se pueden atribuir a los requisitos de recursos del hipervisor de Hyper-V.  
  
### <a name="biztalk-server-and-sql-server-available-memory-sample-results"></a>Resultados de ejemplo de memoria disponible de BizTalk Server y SQL Server  
 Memoria total disponible para SQL Server y BizTalk Server según lo medido por el contador del monitor de rendimiento de \Memory\Available Mbytes era bastante consistente en todos los escenarios de prueba.