---
title: Mantener un rendimiento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae7e63ed-4e28-45b1-ab00-be9f9488a2e6
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da10987a6532987ff7a2ed925e717a0a713cac6e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298148"
---
# <a name="maintaining-performance"></a>Mantener el rendimiento
Esta sección proporciona información que está pensada para ayudarle a resolver problemas de rendimiento detectan durante las comprobaciones de mantenimiento rutinarias. También puede usar las herramientas y técnicas que se describen aquí de forma proactiva, para identificar posibles problemas antes de que resulten más críticos.  
  
 Generalmente es necesario establecer una línea de base de rendimiento como un estándar en el que desea evaluar el rendimiento del sistema actual.  
  
 Además de los temas de esta sección, otros temas en este documento abordan los problemas de rendimiento. En estos temas se muestran en las secciones relacionadas a continuación.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Prácticas recomendadas para mantener el rendimiento](../technical-guides/best-practices-for-maintaining-performance.md)  
  
-   [Configurar el procesamiento por lotes para mejorar el rendimiento del adaptador](../technical-guides/configuring-batching-to-improve-adapter-performance.md)  
  
-   [Cómo ajustar el intervalo de actualización de caché de configuración](../technical-guides/how-to-adjust-the-configuration-cache-refresh-interval.md)  
  
-   [Cómo deshabilitar el seguimiento](../technical-guides/how-to-disable-tracking.md)  
  
-   [Solución de problemas de rendimiento de los clientes3](../technical-guides/troubleshooting-performance-issues3.md)  
  
## <a name="related-sections"></a>Secciones relacionadas  
  
-   Para obtener más información sobre el rendimiento en general, vea problemas [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Guía de optimización del rendimiento en [http://go.microsoft.com/fwlink/?LinkID=150492](http://go.microsoft.com/fwlink/?LinkID=150492).  
  
-   Para obtener información acerca del análisis de registros de monitor de rendimiento semanal en línea de base y los umbrales, vea [mediante la herramienta de análisis de rendimiento de registros (PAL)](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md), "Buscar y eliminar los cuellos de botella" en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] rendimiento Guía de optimización en [http://go.microsoft.com/fwlink/?LinkId=154675](http://go.microsoft.com/fwlink/?LinkId=154675), y [solución de problemas de rendimiento de los clientes3](../technical-guides/troubleshooting-performance-issues3.md).  
  
-   Para obtener información sobre cómo asegurarse de que el sistema no está experimentando frecuente crecimiento automático de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, vea [definir la configuración de crecimiento automático para las bases de datos](../technical-guides/defining-auto-growth-settings-for-databases.md), "Seguimiento directrices de ajuste de tamaño de base de datos" en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Ayuda en [http://go.microsoft.com/fwlink/?LinkId=154677](http://go.microsoft.com/fwlink/?LinkId=154677)y "Identificar cuellos de botella en el nivel de base de datos" en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda en [http://go.microsoft.com/fwlink/?LinkId=154678](http://go.microsoft.com/fwlink/?LinkId=154678).  
  
-   Para obtener información acerca del mantenimiento de SQL Server, [realizar procedimientos de mantenimiento de SQL Server](~/technical-guides/checklist-configuring-sql-server.md).  
  
-   Para obtener información acerca de cómo ejecutar el analizador de SQL Server durante la carga alta para comprobar si los largos tiempos de respuesta y el uso elevado de recursos, consulte "Uso de SQL Server Profiler" en la Ayuda de SQL Server en [http://go.microsoft.com/fwlink/?LinkID=106720](http://go.microsoft.com/fwlink/?LinkID=106720).  
  
-   Para obtener información sobre cómo asegurarse de que el procesamiento por lotes de mensajes para todos los adaptadores es adecuado para el consumo de recursos o la latencia de, consulte [configuración de procesamiento por lotes para mejorar el rendimiento del adaptador](../technical-guides/configuring-batching-to-improve-adapter-performance.md).  
  
-   Para obtener información acerca de cómo aumentar el intervalo de actualización de caché de BizTalk Server, vea [cómo ajustar el intervalo de actualización de caché de configuración](../technical-guides/how-to-adjust-the-configuration-cache-refresh-interval.md).  
  
-   Para obtener información acerca de la limitación de host entrante y saliente, vea "¿Qué es la limitación de Host?" en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda en [http://go.microsoft.com/fwlink/?LinkId=154694](http://go.microsoft.com/fwlink/?LinkId=154694). Para obtener información acerca de los desencadenadores, acciones y estrategias de mitigación para la limitación de entrada y salida, vea "desencadenadores de condiciones de limitación, acciones y estrategias de mitigación" en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda en [http://go.microsoft.com/fwlink/? LinkId = 154695](http://go.microsoft.com/fwlink/?LinkId=154695).  
  
-   Para usar una canalización de envío de paso a través en lugar de la canalización de envío XML de forma predeterminada, vea "Administrar Enviar puertos utilizando el Explorador de BizTalk" en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda en [http://go.microsoft.com/fwlink/?LinkID=154696](http://go.microsoft.com/fwlink/?LinkID=154696).  
  
-   Para obtener información acerca de cómo ajustar el tamaño de la base de datos de seguimiento, vea "Instrucciones Sizing base de datos de seguimiento" en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda en [http://go.microsoft.com/fwlink/?LinkId=154677](http://go.microsoft.com/fwlink/?LinkId=154677).  
  
-   Para obtener información acerca de cómo ajustar el tamaño de las bases de datos de cuadro de mensajes y BizTalkDTADb, BAMPrimaryImport, consulte "Identificar cuellos de botella en el nivel de base de datos" en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda en [http://go.microsoft.com/fwlink/?LinkId=154678](http://go.microsoft.com/fwlink/?LinkId=154678).  
  
-   Para obtener información acerca de cómo evitar la contención en la base de datos de cuadro de mensajes, vea [cómo evitar la contención de disco](http://go.microsoft.com/fwlink/?LinkId=158809) ([http://go.microsoft.com/fwlink/?LinkId=158809](http://go.microsoft.com/fwlink/?LinkId=158809)) en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Guía de optimización del rendimiento.