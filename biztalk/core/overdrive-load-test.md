---
title: Sobrecargar la prueba de carga | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d16d0a8-4255-4f5a-86a2-26cc11bb9a70
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cff4592c58dd165a85d63666958721231cfcbd4c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007669"
---
# <a name="overdrive-load-test"></a>Prueba de sobrecarga
La información de este tema hace referencia a las pruebas que se explican en [escenarios de prueba para medir el rendimiento máximo Sostenible del motor de](../core/test-scenarios-for-measuring-mst-of-the-engine.md).  
  
 La herramienta para la generación de cargas, LoadGen 2007, le permite simular cargas pesadas en un sistema de BizTalk Server.  
  
> [!NOTE]
>  Descargar [LoadGen](https://www.microsoft.com/download/details.aspx?id=14925). La versión anterior de esta herramienta, la herramienta de generación de cargas de BizTalk Server 2004 está disponible para su descarga en [http://go.microsoft.com/fwlink/?linkid=108999](http://go.microsoft.com/fwlink/?linkid=108999).  
  
 Para simular un sistema continuamente sobrecargado, LoadGen 2007 se ha configurado para enviar alrededor de 410 mensajes por segundo, 120 mensajes por segundo más que el rendimiento máximo sostenible medido.  
  
 La prueba se ha diseñado no sólo para sobrecargar el sistema, sino también para tener una idea de cuánto tardará en recuperarse de una profundidad de trabajo acumulado en la cola de impresión de alrededor de 2 millones de registros.  
  
 Para esto, el sistema se ha ido controlando a velocidad creciente hasta que la profundidad de cola de impresión fuera de alrededor de 2 millones de registros. Una vez que la profundidad de cola de impresión ha alcanzado el nivel deseado, no se ha generado más carga.  
  
 Para asegurarse de que el mecanismo de limitación de BizTalk no limitar el host de recepción, lo que impediría la acumulación de un trabajo pendiente de tabla de cola de impresión, el **recuento en la base de datos del mensaje** umbral de limitación para el host de recepción se cambió desde la valor predeterminado de 50000 a 2000000. Para obtener información acerca de cómo cambiar la **recuento en la base de datos del mensaje** umbral de limitación, consulte [cómo modificar recursos según configuración de la limitación](../core/how-to-modify-resource-based-throttling-settings.md). Para obtener información sobre la configuración de limitación de host predeterminado, consulte [uso del panel de configuración para la optimización de rendimiento de BizTalk Server](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md).  
  
 En el gráfico siguiente se muestran los mismos indicadores que en el gráfico anterior.  
  
 **Perfil de carga de prueba de sobrecarga**  
  
 ![Mostrar en el Monitor de rendimiento de la sobrecarga](../core/media/bts06-overdrive-load.gif "BTS06_Overdrive_Load")  
  
 Como se puede ver en el gráfico, la profundidad de cola de impresión empezó a generarse inmediatamente, y alcanzó el máximo justo por encima de los 2 millones de registros. A esta velocidad, se necesitaron unas 2,5 horas en alcanzar los 2 millones de registros de trabajo acumulado que se habían marcado como objetivo. Una vez detenida la carga, se necesitaron alrededor 8 horas de trabajos de limpieza para recuperarse del trabajo acumulado.  
  
## <a name="see-also"></a>Vea también  
 [Escenarios de prueba para medir MST del motor de](../core/test-scenarios-for-measuring-mst-of-the-engine.md)   
 [Mediante el panel de configuración de BizTalk Server ajuste del rendimiento](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)   
 [Prueba de carga sostenible](../core/sustainable-load-test.md)