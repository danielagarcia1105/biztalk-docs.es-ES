---
title: Contadores de rendimiento de cuadro de mensaje | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5eafbd7b-f5fc-4942-a975-18154e6a7ee2
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 584cad0c850b85ef7c920da1611adbdc464d7250
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972786"
---
# <a name="message-box-performance-counters"></a>Contadores de rendimiento de cuadro de mensajes
Los contadores de rendimiento le permiten controlar aspectos específicos del trabajo realizado por el servicio en el sitio o sistema. Los contadores de rendimiento pueden ayudarle a identificar y solucionar problemas de rendimiento del servidor.  
  
 Los siguientes contadores de rendimiento son accesibles para cada instancia de host en el **BizTalk cuadro de mensajes: contadores generales** y **BizTalk cuadro: contadores de Host** categorías de objetos de rendimiento :  
  
> [!NOTE]
>  Para habilitar contadores que hacen referencia al trabajo del Agente SQL, debe incluir la función de SQLAgentUserRole a la cuenta de servicio que se utiliza para ejecutar el servicio de NT y el host de BizTalk. También puede conceder permisos mediante otras funciones o concediendo permisos explícitos de lectura de la base de datos MSDB.  
  
> [!NOTE]
>  Si ha agregado un nuevo cuadro de mensajes para el grupo de BizTalk Server, los contadores que se muestran a continuación no estará disponibles para el cuadro de mensajes nuevo hasta que el configurado **actualización de la caché** ha transcurrido el intervalo para el grupo de BizTalk Server (valor predeterminado de 60 segundos).  
  
|Categoría|Contador|Description|  
|--------------|-------------|-----------------|  
|Contadores generales|Instancias - Número total|Realiza el seguimiento de la suma de todas las instancias de cada host existentes dentro de un cuadro de mensajes determinado.|  
|Contadores generales|Limpieza de procesos caducos del cuadro de mensajes (Purgar trabajos)|Tiempo en segundos de la última ejecución del trabajo del Agente SQL que libera las filas de la base de datos asociadas con procesos caducos de BizTalk.|  
|Contadores generales|Limpieza de mens. del cuadro de mensajes (Purgar trabajos)|Tiempo en segundos de la última ejecución del trabajo del Agente SQL que limpia las tablas del cuadro de mensajes asociadas con mensajes quitados.|  
|Contadores generales|Limpieza de partes del cuadro de mensajes (Purgar trabajo)|Tiempo en segundos de la última ejecución del trabajo del Agente SQL que limpia las tablas del cuadro de mensajes asociadas con partes de mensajes quitados.|  
|Contadores generales|Trabajo de purga de suscripciones del cuadro de mensajes (Purgar trabajos)|Tiempo en segundos de la última ejecución del trabajo del Agente SQL que purga las suscripciones que ya no se encuentran en uso.|  
|Contadores generales|Tamaño de cola de impresión|Hace un seguimiento del tamaño de la cola de impresión de un cuadro de mensajes particular de un servidor particular.|  
|Contadores generales|Copia de mens. controlados (Purgar trabajos)|Tiempo en segundos de la última ejecución del trabajo del Agente SQL que copia cuerpos de mensajes de los que se ha efectuado el seguimiento.|  
|Contadores generales|Tamaño de datos de seguimiento|Hace un seguimiento de la tabla de datos de seguimiento de un cuadro de mensajes determinado de un servidor particular.|  
|Contadores generales|Limpieza de cola de impresión de seguimiento (Purgar trabajos)|Tiempo en segundos de la última ejecución del trabajo del Agente SQL que purga las tablas de colas de impresión de seguimiento inactivas.|  
|Contadores de host|Cola de host - Ref. mens. de estado de instancia - Longitud|Hace un seguimiento del número de referencias de mensajes en la cola del estado de instancia del host particular.|  
|Contadores de host|Cola de host - Longitud|Hace un seguimiento del número total de mensajes en la cola de host particular.|  
|Contadores de host|Cola de host - Número de instancias|Hace un seguimiento del número de instancias del host particular.|  
|Contadores de host|Cola de host - Mens. Suspendidos - Longitud|Hace un seguimiento del número total de mensajes suspendidos del host particular.|  
  
## <a name="to-access-performance-counters"></a>Para tener acceso a los contadores de rendimiento  
 Siga los pasos que se indican a continuación para obtener acceso a los contadores de rendimiento.  
  
#### <a name="if-you-are-using-windows-2008"></a>Si está usando Windows 2008  
  
1.  Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Monitor de rendimiento**.  
  
2.  En el **Monitor de rendimiento** cuadro de diálogo, expanda **herramientas de supervisión**, seleccione **Monitor de rendimiento**y, a continuación, haga clic en **agregar**.  
  
3.  En el **agregar contadores** cuadro de diálogo, desde el **contadores disponibles** lista, seleccione **BizTalk cuadro de mensajes: contadores generales** o **BizTalk : Contadores de host**. Expanda el objeto de contador de rendimiento seleccionado y seleccione los contadores que desea supervisar.  
  
4.  En el **instancias del objeto seleccionado** , seleccione las instancias específicas que se deben supervisar en los contadores seleccionados y, a continuación, haga clic en **agregar**.  Para seleccionar todas las instancias de contador disponibles, seleccione \< **todas las instancias**\>.  
  
5.  Después de agregar los contadores, haga clic en **Aceptar**.  
  
     Los contadores de rendimiento seleccionados aparecen en la **Monitor de rendimiento** pantalla.  
  
## <a name="see-also"></a>Vea también  
 [Trucos y sugerencias de rendimiento](../core/performance-tips-and-tricks.md)   
 [Medir el rendimiento máximo sostenible del motor](../core/measuring-maximum-sustainable-engine-throughput.md)   
 [Medir el rendimiento de seguimiento sostenible máximo](../core/measuring-maximum-sustainable-tracking-throughput.md)   
 [Optimizar el uso de recursos mediante la limitación de Host](../core/optimizing-resource-usage-through-host-throttling.md)