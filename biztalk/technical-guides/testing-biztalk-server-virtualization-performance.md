---
title: "Probar el rendimiento de la virtualización de servidor BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d09121b1-cdd6-4c01-9d69-0f1923464f0e
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8cec992ab489c63f68ac4d77652209e65eff258a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="testing-biztalk-server-virtualization-performance"></a>Probar el rendimiento de la virtualización de servidor BizTalk Server
Cada uno de los escenarios de prueba de rendimiento que se describe en esta guía se implementaron en equipos físicos en un laboratorio de pruebas de Microsoft y, a continuación, se realiza la misma prueba de carga en cada arquitectura de sistemas distintos. El sistema operativo de host en cada equipo físico era una instalación completa de [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] Enterprise, edición de 64 bits, con el rol de servidor de Hyper-V instalado. Las máquinas virtuales para pruebas [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] se han configurado con [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] Enterprise, edición de 64 bits como el sistema operativo invitado. La máquina virtual para pruebas [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] se configuró con [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] Enterprise, edición de 64 bits como el sistema operativo invitado. Los escenarios de prueba, métodos de prueba, los resultados de pruebas de rendimiento y su análisis posterior empleadas para formular una serie de procedimientos recomendados y orientación para diseñar, implementar, y optimizar virtualiza [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
-   **Escenario de prueba 1: Línea de base** : el primer escenario se diseñó para establecer el rendimiento de línea de base de un entorno de BizTalk Server que se ejecuta en solo un hardware físico. Para este escenario BizTalk Server y SQL Server se han instalado y ejecución en solo un hardware físico.  
  
-   **Escenario de prueba 2: Virtual BizTalk Server/físico SQL Server** -el segundo escenario se diseñó para determinar el impacto de rendimiento de BizTalk Server de hospedaje en varias máquinas virtuales de invitado en el mismo servidor físico. Resultados de las pruebas realizadas desde varios equipos virtuales configuraciones se compararon con una procesamiento de la máquina física con el mismo número de procesadores lógicos como el número total dispersión en todas las máquinas virtuales.  
  
-   **Escenario de prueba 3: Virtual BizTalk Server/Virtual SQL Server en los hosts de Hyper-V físicos independientes** -el tercer escenario se realiza para determinar el impacto de rendimiento de BizTalk Server y SQL Server en un entorno virtualizado. Las pruebas se realizaron con BizTalk Server en máquinas virtuales de Hyper-V con las bases de datos de BizTalk hospedados en un [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] instancia que se ejecuta en una máquina virtual de Hyper-V. En este escenario, las máquinas virtuales de BizTalk Server y las máquinas virtuales de SQL Server se hospedan en los hosts de Hyper-V físicos independientes.  
  
-   **Prueba escenario 4: Consolidación de servidores-la consolidación de una completa BizTalk grupo incluidas SQL en un servidor físico en Hyper-V** : en el escenario, todas las máquinas virtuales (VM) necesarias para ejecutar la aplicación de prueba se hospedan en un servidor físico. El propósito de este escenario es determinar los costes de rendimiento de hospedaje [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] y [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] máquinas virtuales en un entorno consolidado.  
  
 En esta sección se proporciona información general de la aplicación de prueba y la arquitectura de servidor que se usa para cada escenario y también presenta indicadores clave de rendimiento (KPI) observados durante las pruebas.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Información general del escenario de prueba](../technical-guides/test-scenario-overview.md)  
  
-   [Arquitectura de servidor del escenario de prueba](../technical-guides/test-scenario-server-architecture.md)  
  
-   [Resultados de pruebas: Indicadores clave de rendimiento de servidor BizTalk Server](../technical-guides/test-results-biztalk-server-key-performance-indicators.md)  
  
-   [Resultados de pruebas: Indicadores clave de rendimiento SQL Server](../technical-guides/test-results-sql-server-key-performance-indicators.md)  
  
-   [Resultados de pruebas: Indicadores clave de rendimiento de red](../technical-guides/test-results-networking-key-performance-indicators.md)  
  
-   [Resultados de pruebas: Indicadores clave de rendimiento de memoria](../technical-guides/test-results-memory-key-performance-indicators.md)  
  
-   [Resumen de resultados de pruebas](../technical-guides/summary-of-test-results.md)