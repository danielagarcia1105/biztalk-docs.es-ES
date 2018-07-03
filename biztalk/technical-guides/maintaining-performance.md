---
title: Mantener el rendimiento | Microsoft Docs
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
ms.openlocfilehash: bdaa00ebb244db6d389393a0bbf32c0075c1f3d3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984429"
---
# <a name="maintaining-performance"></a>Mantener el rendimiento
En esta sección se proporciona información que está pensado para ayudarle a resolver problemas de rendimiento detectan durante las comprobaciones de mantenimiento rutinarias. También puede usar las herramientas y técnicas descritas aquí de forma proactiva, para identificar posibles problemas antes de que se conviertan en problemas críticos.  

 Por lo general, deberá establecer una línea de base de rendimiento como estándar en el que se va a evaluar el rendimiento del sistema actual.  

 Además de los temas de esta sección, otros temas de este documento trata problemas de rendimiento. Estos temas se muestran en las secciones relacionadas a continuación.  

## <a name="in-this-section"></a>En esta sección  

-   [Procedimientos recomendados para el mantenimiento del rendimiento](../technical-guides/best-practices-for-maintaining-performance.md)  

-   [Configuración del procesamiento por lotes para mejorar el rendimiento del adaptador](../technical-guides/configuring-batching-to-improve-adapter-performance.md)  

-   [Cómo ajustar el intervalo de actualización de la caché de configuración](../technical-guides/how-to-adjust-the-configuration-cache-refresh-interval.md)  

-   [Cómo deshabilitar el seguimiento](../technical-guides/how-to-disable-tracking.md)  

-   [Solución de problemas de rendimiento de los clientes3](../technical-guides/troubleshooting-performance-issues3.md)  

## <a name="related-sections"></a>Secciones relacionadas  

- Para obtener más información sobre el rendimiento en general, vea problemas [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Guía de optimización del rendimiento en [ http://go.microsoft.com/fwlink/?LinkID=150492 ](http://go.microsoft.com/fwlink/?LinkID=150492).  

- Para obtener información acerca del análisis de registros de monitor de rendimiento semanales frente a la línea base y los umbrales, vea [mediante la herramienta de análisis de rendimiento de los registros (PAL)](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md), "Buscar y eliminar cuellos de botella" en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] rendimiento Guía de optimización en [ http://go.microsoft.com/fwlink/?LinkId=154675 ](http://go.microsoft.com/fwlink/?LinkId=154675), y [solución de problemas de rendimiento de los clientes3](../technical-guides/troubleshooting-performance-issues3.md).  

- Para obtener información sobre cómo asegurarse de que el sistema no está experimentando con frecuencia el crecimiento automático de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, vea [definir valores de crecimiento automático para las bases de datos](../technical-guides/defining-auto-growth-settings-for-databases.md), "Seguimiento de las directrices de tamaño de base de datos" en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Ayuda en [ http://go.microsoft.com/fwlink/?LinkId=154677 ](http://go.microsoft.com/fwlink/?LinkId=154677)y "Identificar cuellos de botella en el nivel de base de datos" en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda en [ http://go.microsoft.com/fwlink/?LinkId=154678 ](http://go.microsoft.com/fwlink/?LinkId=154678).  

- Para obtener información acerca del mantenimiento de SQL Server, [realizar procedimientos de mantenimiento de SQL Server](~/technical-guides/checklist-configuring-sql-server.md).  

- Para obtener información sobre la ejecución de SQL Server Profiler durante una carga elevada para comprobar si los largos tiempos de respuesta y el uso elevado de recursos, consulte "Uso de SQL Server Profiler" en la Ayuda de SQL Server en [ http://go.microsoft.com/fwlink/?LinkID=106720 ](http://go.microsoft.com/fwlink/?LinkID=106720).  

- Para obtener información sobre cómo asegurarse de que es adecuado para el consumo de recursos o la latencia de procesamiento por lotes de mensajes para todos los adaptadores, vea [configuración de procesamiento por lotes para mejorar el rendimiento del adaptador](../technical-guides/configuring-batching-to-improve-adapter-performance.md).  

- Para obtener información sobre cómo aumentar el intervalo de actualización de caché de BizTalk Server, vea [cómo ajustar el intervalo de actualización de caché de configuración](../technical-guides/how-to-adjust-the-configuration-cache-refresh-interval.md).  

- Para obtener información acerca de la limitación de host entrante y saliente, consulte "¿Cuál es la limitación de Host?" en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda en [ http://go.microsoft.com/fwlink/?LinkId=154694 ](http://go.microsoft.com/fwlink/?LinkId=154694). Para obtener información sobre los desencadenadores, acciones y estrategias de mitigación para la limitación de entrada y salida, vea "estrategias de mitigación, acciones y desencadenadores de condición de limitación" en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda en [ http://go.microsoft.com/fwlink/?LinkId=154695 ](http://go.microsoft.com/fwlink/?LinkId=154695).  

- Para usar una canalización de envío de paso a través en lugar de la canalización de envío XML de forma predeterminada, vea "Administrar Enviar puertos utilizando el Explorador de BizTalk" en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda en [ http://go.microsoft.com/fwlink/?LinkID=154696 ](http://go.microsoft.com/fwlink/?LinkID=154696).  

- Para obtener información sobre cómo ajustar el tamaño de la base de datos de seguimiento, vea "Instrucciones Sizing base de datos de seguimiento" en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda en [ http://go.microsoft.com/fwlink/?LinkId=154677 ](http://go.microsoft.com/fwlink/?LinkId=154677).  

- Para obtener información sobre cómo ajustar el tamaño de las bases de datos de cuadro de mensajes, BizTalkDTADb y BAMPrimaryImport, consulte "Identificar cuellos de botella en el nivel de base de datos" en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda en [ http://go.microsoft.com/fwlink/?LinkId=154678 ](http://go.microsoft.com/fwlink/?LinkId=154678).  

- Para obtener información sobre cómo evitar la contención en la base de datos de cuadro de mensajes, vea [cómo evitar la contención del disco](http://go.microsoft.com/fwlink/?LinkId=158809) ([http://go.microsoft.com/fwlink/?LinkId=158809](http://go.microsoft.com/fwlink/?LinkId=158809)) en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Guía de optimización del rendimiento.
