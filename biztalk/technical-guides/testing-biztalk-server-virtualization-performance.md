---
title: Las pruebas de rendimiento de la virtualización de servidor BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d09121b1-cdd6-4c01-9d69-0f1923464f0e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f07c6bf8371e1db84ed574d7c737d4cc5b3903b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993701"
---
# <a name="testing-biztalk-server-virtualization-performance"></a>Las pruebas de rendimiento de la virtualización de servidor BizTalk Server
Cada uno de los escenarios de prueba de rendimiento descritos en esta guía se han implementado en equipos físicos en un laboratorio de pruebas de Microsoft y, a continuación, se realizó la misma prueba de carga en cada arquitectura de sistemas distintos. El sistema operativo host en cada equipo físico era una instalación completa de [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] Enterprise, edición de 64 bits, con el rol de servidor de Hyper-V instalado. Las máquinas virtuales que se usa para pruebas de BizTalk Server se han configurado con [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] Enterprise, edición de 64 bits como el sistema operativo invitado. La máquina virtual que se usa para pruebas de SQL Server se configuró con [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] Enterprise, edición de 64 bits como el sistema operativo invitado. Los escenarios de prueba, los métodos de prueba, los resultados de pruebas de rendimiento y su análisis posterior se usaron para formular una serie de procedimientos recomendados y orientación para diseñar, implementar, y optimizar virtualizadas [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
- **Escenario de prueba 1: Línea base** : el primer escenario se diseñó para establecer el rendimiento de la base de un entorno de BizTalk Server que se ejecuta en hardware físico solo. En este escenario de BizTalk Server y SQL Server se instalaron y ejecutar en hardware físico solo.  
  
- **Escenario de prueba 2: Virtual BizTalk Server/físico SQL Server** -el segundo escenario se diseñó para determinar el impacto de rendimiento del servidor BizTalk Server que hospeda en varias máquinas virtuales de invitado en el mismo servidor físico. Procedente de varios equipos virtuales configuraciones fueron, a continuación, en comparación con una máquina física de procesamiento con el mismo número de procesadores lógicos como el número total de resultados de pruebas dispersión en todas las máquinas virtuales.  
  
- **Escenario de prueba 3: Virtual BizTalk Server/Virtual SQL Server en hosts de Hyper-V físicos independientes** -llevó a cabo el tercer escenario para determinar el impacto de rendimiento de la ejecución de BizTalk Server y SQL Server en un entorno virtualizado. Se realizaron pruebas con que se ejecutan en máquinas virtuales de Hyper-V con las bases de datos de BizTalk hospedados en una instancia de SQL Server que se ejecuta en una máquina virtual de Hyper-V de BizTalk Server. Para este escenario, las máquinas virtuales de BizTalk Server y las máquinas virtuales de SQL Server se hospedan en hosts de Hyper-V físicos independientes.  
  
- **Escenario de prueba 4: Consolidación de servidores-consolidar una completa BizTalk Group incluidos de SQL en un servidor físico en Hyper-V** : en el escenario, todas las máquinas virtuales (VM) necesarias para ejecutar la aplicación de prueba se hospedan en un servidor físico. El propósito de este escenario es determinar los costos de rendimiento de SQL Server y máquinas virtuales de BizTalk Server en un entorno consolidado de hospedaje.  
  
  Esta sección proporciona información general de la aplicación de prueba y la arquitectura de servidor que se usa para cada escenario y también presenta indicadores clave de rendimiento (KPI) observados durante las pruebas.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Información general del escenario de prueba](../technical-guides/test-scenario-overview.md)  
  
-   [Arquitectura de servidor del escenario de prueba](../technical-guides/test-scenario-server-architecture.md)  
  
-   [Resultados de pruebas: indicadores clave de rendimiento de BizTalk Server](../technical-guides/test-results-biztalk-server-key-performance-indicators.md)  
  
-   [Resultados de pruebas: indicadores clave de rendimiento de SQL Server](../technical-guides/test-results-sql-server-key-performance-indicators.md)  
  
-   [Resultados de pruebas: indicadores clave de rendimiento de redes](../technical-guides/test-results-networking-key-performance-indicators.md)  
  
-   [Resultados de pruebas: indicadores clave de rendimiento de memoria](../technical-guides/test-results-memory-key-performance-indicators.md)  
  
-   [Resumen de los resultados de pruebas](../technical-guides/summary-of-test-results.md)