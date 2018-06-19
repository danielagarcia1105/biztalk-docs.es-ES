---
title: 'Resultados de pruebas: Indicadores clave de rendimiento de servidor BizTalk Server | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 902cdfc1-21ab-4f56-b97b-2f8979514b11
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab682b0d773a613e6dfcdf143ef0afbeb5af48fa
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009925"
---
# <a name="test-results-biztalk-server-key-performance-indicators"></a>Resultados de pruebas: Indicadores clave de rendimiento de servidor BizTalk Server
En este tema se resume a BizTalk Server Performance indicadores clave (KPI) observado durante los escenarios de prueba. En concreto, estas pruebas evalúan rendimiento según lo medido por la "**BizTalk: mensajería/documentos procesados/seg.**" contador del monitor de rendimiento y latencia, según lo medido por el tiempo de respuesta del cliente de Visual studio.  
  
## <a name="summary-of-biztalk-server-key-performance-indicators"></a>Resumen de indicadores clave de rendimiento de servidor BizTalk Server  
 Para cada escenario las máquinas físicas estaban restringidas para que el número de procesadores lógicos y los procesadores virtuales era equivalente. Esto se hacía con los modificadores de boot.ini/maxmem y/numproc. Para obtener más información acerca del uso de estos modificadores, vea "Referencia de opciones de arranque INI" en [http://go.microsoft.com/fwlink/?LinkId=122139](http://go.microsoft.com/fwlink/?LinkId=122139).  
  
 **Comparación de indicadores de rendimiento clave de BizTalk Server:** ejecutar BizTalk Server en una máquina virtual de Hyper-V proporciona aproximadamente el 95% del rendimiento de latencia y rendimiento de BizTalk Server en un hardware físico para este escenario de prueba. Debido a la naturaleza sin estado de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], máquinas virtuales de BizTalk Server adicionales pueden agregarse fácilmente en el entorno según sea necesario para proporcionar escalado horizontal y aumentar el rendimiento general del sistema. Crear y agregar adicionales de BizTalk Server en el entorno pueden realizarse mediante la utilidad de sysprep para generar imágenes nuevas a partir de una imagen base.  
  
> [!NOTE]  
>  Un archivo de respuesta de sysprep y secuencias de comandos son siempre con BizTalk Server para dar cabida a uso de sysprep para crear imágenes adicionales desde una imagen existente de un equipo que tiene instalado BizTalk Server. Estas secuencias de comandos de ejemplo están diseñados para su uso con BizTalk Server instalado en 32 bits y 64 bits sólo en versiones de Windows Server 2008. Para obtener más información, consulte la documentación en línea de BizTalk Server.  
  
 Aprovisionamiento, consolidación y administración de máquinas virtuales pueden ser aceleradas significativamente mediante el uso de System Center Virtual Machine Manager (VMM). Para obtener más información acerca de System Center Virtual Machine Manager, consulte [http://go.microsoft.com/fwlink/?LinkID=111303](http://go.microsoft.com/fwlink/?LinkID=111303)  
  
 Los resultados obtenidos en este laboratorio de rendimiento muestran una mejora marcada desde el rendimiento logrado cuando se ejecuta [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] en [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] en una máquina virtual de Hyper-V. Ejecuta [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] en Hyper-V máquina virtual proporciona ocupada al 75% del rendimiento de rendimiento y la latencia de [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] en el hardware físico frente a la aproximadamente el 95% rendimiento observado cuando se ejecuta BizTalk Server y [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] en máquinas virtuales de Hyper-V. Este rendimiento mejorado es en gran medida atribuible a mejorar el rendimiento de [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] cuando se ejecuta como un sistema operativo invitado en Hyper-V. La comparación de rendimiento relacionados desde el [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] Guía de Hyper-V está disponible en [http://go.microsoft.com/fwlink/?LinkId=147144](http://go.microsoft.com/fwlink/?LinkId=147144).  
  
 El siguiente gráfico muestra el rendimiento de BizTalk Server en las diferentes plataformas de prueba:  
  
 ![Indicadores de rendimiento clave de BizTalk](../technical-guides/media/biztalkkpi.gif "BizTAlkKPI")  
  
 La siguiente tabla muestra el rendimiento relativo de recopilados de KPI para cada configuración. Cada conjunto de resultados se calcula como un porcentaje de la configuración de línea de base KPI.  
  
|KPI|Virtual de BizTalk o física SQL|Virtual SQL de BizTalk y virtuales en Hosts independientes|Virtual de BizTalk/Virtual de SQL en el entorno consolidado|  
|---------|-----------------------------------|----------------------------------------------------|--------------------------------------------------------------|  
|\BizTalk:Messaging\Documents procesados/seg.|94.3%|79.8%|67%|  
|Latencia según lo medido por el cliente de Visual Studio|94.3%|79.7%|66.9%|  
  
 Para obtener más información acerca de cómo optimizar el rendimiento de una solución de BizTalk Server, consulte la Guía de optimizaciones de BizTalk Server rendimiento disponible en [http://go.microsoft.com/fwlink/?LinkId=122477](http://go.microsoft.com/fwlink/?LinkId=122477).  
  
## <a name="performance-comparison-results-summary"></a>Resumen de resultados de comparación de rendimiento  
 El rendimiento de 94,3% y la latencia de 94,3% logrado cuando se ejecuta solo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en Hyper-V sugiere que la virtualización de este nivel de la solución con Hyper-V proporciona un excelente rendimiento junto con el aprovisionamiento, consolidación, flexibilidad y facilidad de administración que son posibles al implementar soluciones en un entorno de Hyper-V.  
  
### <a name="throughput-comparison-sample-results"></a>Resultados del ejemplo de comparación de rendimiento  
 Cuando el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos utilizados en el entorno de BizTalk Server se ejecutaron en máquinas virtuales de Hyper-V, el rendimiento de la solución de BizTalk Server según lo medido por la "**BizTalk: mensajería/documentos procesados/seg.**" contador del monitor de rendimiento tiene un rango de 67% 94,3% del rendimiento de la alcanzables cuando todos los equipos que se usan en el entorno de BizTalk Server se instalaron en hardware físico.  
  
### <a name="latency-comparison-sample-results"></a>Resultados de ejemplo de comparación de latencia  
 Cuando el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos utilizados en el entorno de BizTalk Server se ejecutaron en máquinas virtuales de Hyper-V, la latencia de la solución de BizTalk Server según lo medido por la respuesta del cliente de Visual Studio hora tiene un rango de 66.9% 94,3% de la latencia alcanzables cuando todos los de los equipos utilizados en el entorno de BizTalk Server se instala en hardware físico.