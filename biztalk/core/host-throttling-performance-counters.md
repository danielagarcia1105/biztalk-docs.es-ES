---
title: Contadores de rendimiento de limitación de host | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- host throttling, performance counters
ms.assetid: b9090d1c-86be-40db-b814-cc116a426d95
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ca80f44b9f1244a340e9a9892593ae42ba4b4e9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="host-throttling-performance-counters"></a>Contadores de rendimiento de limitación de host
En esta sección se describen los contadores del monitor de rendimiento que miden los parámetros del sistema que afectan a la limitación de host. Los siguientes contadores de rendimiento son accesibles para cada instancia de host en el **BizTalk: agente** categoría de objeto de rendimiento:  
  
|Contador|Description|  
|-------------|-----------------|  
|Número de instancias activas|Número de instancias de servicio activas en memoria. En el motor de orquestaciones, se entiende por instancia de servicio cada una de las instancias en ejecución de una programación de orquestación. En el Gestor extremo, una instancia de servicio puede corresponder a un mensaje único sin estado o a una colección de mensajes con estado. **Nota:** instancias con estado son aquellos que mantener cierta información de estado acerca de los mensajes asociados a la instancia. Los mensajes que pertenecen a una instancia con estado están correlacionados de una u otra forma. Por ejemplo un puerto de envío ordenado que mantiene información sobre la ordenación se considera una instancia con estado. En la mayoría de los escenarios de mensajería hay instancias sin estado donde los mensajes se procesan de forma totalmente independiente de otros. Cada una de estas instancias sin estado se corresponde con un único mensaje de EPM.|  
|Sesión de base de datos|Número de conexiones simultáneas de base de datos de cuadro de mensajes que se están utilizando.|  
|Umbral de sesiones de base de datos|Umbral actual de sesiones simultáneas de base de datos. Inicialmente se establece en el **las conexiones de base de datos** valor en el **limitación basada en recursos** ficha **panel de configuración**. Este valor se ajusta automáticamente según el uso de sesiones de base de datos del proceso. Si el número de sesiones simultáneas de base de datos supera este umbral en un momento dato, se implementa la limitación de host.|  
|Tamaño de la base de datos|Número de mensajes en las colas de la base de datos que ha publicado este proceso. Este valor se mide según el número de elementos en las tablas de cola para todos los hosts y el número de elementos en las tablas de cola y de seguimiento. Si un proceso publica en varias colas, este contador refleja el promedio ponderado de todas las colas. **Nota:** si se reinicia el host, se pierden las estadísticas almacenadas en memoria. Puesto que hay cierta sobrecarga, BizTalk Server reanudará la recopilación de estadísticas sólo cuando haya al menos 100 publicaciones con un 5% del total en el proceso de host reiniciado.|  
|Número excesivo de sesiones de base de datos|-0: Normal<br />-1: recuento de sesiones de base de datos supera el umbral|  
|Tamaño excesivo de base de datos|-0: Normal<br />-1: tamaño de base de datos ha crecido por encima del umbral<br /><br /> Este contador se establecerá en un valor de uno si alguna de las condiciones enumeradas para el **recuento en la base de datos del mensaje** umbral se produce. [Cómo modificar recursos según configuración de la limitación](../core/how-to-modify-resource-based-throttling-settings.md) proporciona información acerca de este umbral de limitación.|  
|Número excesivo de mensajes en curso|-0: Normal<br />-1: número supera el límite de mensajes en proceso|  
|Tasa excesiva de entrega de mensajes|-0: Normal<br />-1: mensaje de tasa de entrega supera la velocidad de procesamiento de mensajes|  
|Tasa excesiva de publicación de mensajes|-0: Normal<br />-1: publicar solicitud tasa supera la tasa de finalización|  
|Consumo excesivo de memoria de proceso|-0: Normal<br />-1: memoria de proceso supera el umbral|  
|Consumo excesivo de memoria del sistema|-0: Normal<br />-1: memoria del sistema supera el umbral|  
|Cuenta excesiva de subprocesos|-0: Normal<br />-1: número de subprocesos supera el umbral|  
|Número de mensajes en curso|Número de mensajes en memoria entregados al motor XLANG o al motor saliente de mensajería que todavía no se han procesado.|  
|Umbral del número de mensajes en curso|Umbral actual del número de mensajes en curso.|  
|Retraso en la entrega de mensajes (ms)|Retraso actual en ms impuesto en cada lote de entrega de mensajes (aplicable si se limita la entrega de mensajes).|  
|Tasa entrante de la entrega de mensajes|Número de mensajes entregados por segundo al motor de orquestaciones o al motor de mensajería en el intervalo de muestreo dado.|  
|Tasa saliente de la entrega de mensajes|Número de mensajes procesados por segundo por el motor de orquestaciones o el motor de mensajería en el intervalo de muestreo dado.|  
|Estado de limitación de entrega de mensajes|Marca que especifica si el sistema limita la entrega de mensajes (que afecta al procesamiento de mensajes XLANG y a los transportes de salida).<br /><br /> -0: sin limitación<br />-1: limitación debido a tasa de entrega de mensajes no equilibrada (la tasa de entrada superior tasa de salida)<br />-3: limitación debido a alta-proceso de recuento de mensajes<br />-4: limitación debido a la presión de memoria de proceso<br />-5: limitación debido a la presión de memoria de sistema<br />-9: limitación debido a número excesivo de subprocesos<br />-10: limitación debido a usuario sobrescribir de entrega|  
|Duración del estado de limitación de la entrega de mensajes|Segundos desde que el sistema entró en este estado. Si hay limitación en el host, ¿cuánto tiempo se ha limitado? Si no existe limitación, ¿cuánto tiempo desde la aplicación de la limitación?|  
|Reemplazo de usuario de limitación de la entrega de mensajes|Este contador refleja el reemplazo de usuario supervisado por el motor; se interpreta de la manera siguiente:<br /><br /> -0: no hay un reemplazo<br />-1: limitar siempre entrega de mensajes<br />-2: no limitar entrega de mensajes<br /><br /> Esta invalidación es configurable en el **limitación basada en tasa** ficha **panel de configuración**.|  
|Retraso en la publicación de mensajes (ms)|Retraso actual en ms impuesto en cada lote de publicación de mensajes (aplicable si se limita la publicación de mensajes y si el lote no se excluye de la limitación).|  
|Tasa entrante de publicación de mensajes|Número de mensajes por segundo que se envían a la base de datos para su publicación en el intervalo de muestreo dado.|  
|Tasa saliente de publicación de mensajes|Número de mensajes por segundo que se publican realmente en la base de datos en el intervalo de muestreo dado.|  
|Estado de la limitación de publicación de mensajes|Marca que especifica si el sistema limita la publicación de mensajes (que afecta al procesamiento de mensajes XLANG y a los transportes de entrada).<br /><br /> -0: sin limitación<br />-2: limitación debido a tasa de publicación de mensajes no equilibrada (la tasa de entrada superior tasa de salida)<br />-4: limitación debido a la presión de memoria de proceso<br />-5: limitación debido a la presión de memoria de sistema<br />-6: limitación debido al crecimiento de la base de datos<br />-8: limitación debido a número excesivo de sesiones<br />-9: limitación debido a número excesivo de subprocesos<br />-11: limitación debido a usuario Anular publicación|  
|Duración del estado de la limitación de publicación de mensajes|Segundos desde que el sistema entró en este estado. Si hay limitación en el host, ¿cuánto tiempo se ha limitado? Si no existe limitación, ¿cuánto tiempo desde la aplicación de la limitación?|  
|Reemplazo de usuario de la limitación de publicación de mensajes|Este contador refleja el reemplazo de usuario supervisado por el motor; se interpreta de la manera siguiente:<br /><br /> -0: no hay un reemplazo<br />-1: limitar siempre publicación de mensajes<br />-2: no limitar publicación de mensajes<br /><br /> Esta invalidación es configurable en el **limitación basada en tasa** ficha **panel de configuración**.|  
|Uso de memoria física (MB)|Cantidad de memoria física en MB que utilizan todos los procesos en el equipo.|  
|Uso de memoria de proceso (MB)|Consumo de memoria de proceso en MB. Se trata del tamaño máximo de espacio de trabajo del proceso y del espacio total asignado al archivo de página para el proceso.|  
|Umbral de uso de memoria de proceso (MB)|Umbral actual del consumo de memoria de proceso en MB. Esto se establece inicialmente en el **virtual de proceso** valor en **panel de configuración**. Si se especifica un valor de porcentaje, se calcula según la memoria disponible que se va a asignar.|  
|Id. de clase de servicio|Valor decimal de la parte inicial del GUID de la clase de servicio al que corresponde la instancia del contador de rendimiento. Un proceso puede alojar más de una clase de servicio y los contadores de rendimiento del agente de mensaje muestran los datos de las clases de servicio más activas.|  
|Número de subprocesos|Número de subprocesos utilizados en el proceso.|  
|Umbral del número de subprocesos|Umbral actual del número de subprocesos en el proceso. Esto está establecido inicialmente en el **subprocesos** valor en el **limitación basada en recursos** pestaña **panel de configuración**. Este valor se ajusta automáticamente según los requisitos de subprocesos del proceso actual. Si el número de subprocesos en el proceso es superior a este valor de umbral en un momento dado, se implementa la limitación de host.|  
|Total de lotes asignados|Número de lotes de base de datos que ha asignado la clase de servicio.|  
|Total de mensajes entregados|Número de mensajes de salida entregados al motor de orquestaciones o al Gestor extremo (EPM).|  
|Total de mensajes publicados|Número de mensajes publicados.|  
  
> [!NOTE]
>  El **BizTalk: agente** los contadores de rendimiento se proporcionan para el propósito explícito de analizar el comportamiento de limitación de un host y por lo tanto, no capturarán datos a menos que el host especificado está procesando activamente los documentos. Por diseño, la finalidad de este comportamiento es impedir que se consuman subprocesos del sistema con el monitor de rendimiento cuando no se están realizando actividades de limitación.  
  
## <a name="to-access-performance-counters"></a>Para tener acceso a los contadores de rendimiento  
 Siga los pasos que se indican a continuación para obtener acceso a los contadores de rendimiento.  
  
#### <a name="if-you-are-using-windows-2008"></a>Si está usando Windows 2008  
  
1.  Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Monitor de rendimiento**.  
  
2.  En el **Monitor de rendimiento** cuadro de diálogo, expanda **herramientas de supervisión**, seleccione **Monitor de rendimiento**y, a continuación, haga clic en **agregar**.  
  
3.  En el **agregar contadores** cuadro de diálogo, desde el **contadores disponibles** lista, expanda la **BizTalk: agente de** objeto de contador de rendimiento y seleccione los contadores que pueden supervisar.  
  
4.  En el **instancias del objeto seleccionado** , seleccione las instancias específicas que se deben supervisar en los contadores seleccionados y, a continuación, haga clic en **agregar**.  Para seleccionar todas las instancias de contador disponibles, seleccione \< **todas las instancias**\>.  
  
5.  Después de agregar los contadores, haga clic en **Aceptar**.  
  
     Los contadores de rendimiento seleccionados aparecen en la **Monitor de rendimiento** pantalla.  
  
## <a name="see-also"></a>Vea también  
 [Recomendaciones de diseño de limitación](../core/throttling-design-recommendations.md)   
 [Cómo BizTalk Server incorpora la limitación de Host](../core/how-biztalk-server-implements-host-throttling.md)   
 [Uso del panel de configuración para ajustar el rendimiento de BizTalk Server](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)