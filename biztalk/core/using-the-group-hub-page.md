---
title: "Mediante la página concentrador de grupo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50693ccc-a3b2-4ad0-9a05-d60dab404a07
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e035a363b71b70db390d88a8b0e32e2e9b531d92
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-group-hub-page"></a>Usar la página Concentrador de grupo
Al seleccionar la **grupo de BizTalk** nodo en la consola de administración de BizTalk Server, muestra la página concentrador de grupo de BizTalk Server en el panel de detalles. La página Concentrador de grupo de BizTalk Server se divide en tres secciones que proporcionan una vista general del estado del sistema de BizTalk Server:  
  
-   El **Introducción a la configuración** sección, situada en la parte superior de la página concentrador de grupo, indica el estado general del grupo de BizTalk, mostrando el estado de las aplicaciones, instancias de host, y los controladores de adaptador configurados en Este grupo.  
  
-   El **trabajo en curso** y **elementos suspendidos** secciones se encuentran en el medio de la página concentrador de grupo.  
  
    -   El **trabajo en curso** sección muestra las instancias de servicio, las orquestaciones deshidratadas, puertos de reintentos e inactivos, instancias de servicio preparadas e instancias de servicio programadas en ejecución.  
  
    -   El **elementos suspendidos** sección muestra el número de instancias de servicio suspendidas y las instancias reanudables y no reanudables.  
  
-   El **instancias de servicio suspendidas agrupadas** sección muestra las instancias de servicio suspendidas agrupadas por aplicación, nombre de servicio, código de error y URI.  
  
    > [!NOTE]
    >  Los números que figuran en la página Concentrador de grupo son recuentos aproximados únicamente. Por ejemplo, el número mostrado debajo **instancias en ejecución** o **instancias de servicio suspendidas** no puede ser igual el número total de instancias de servicio o instancias de servicio suspendidas en ejecución Dado que el estado del sistema puede cambiar mientras se están generando las distintas estadísticas sobre la página del concentrador.  
  
-   El **instancias de servicio controladas** y **eventos de mensajes controlados** secciones ejecutan consultas en los eventos de mensaje y el estado de las instancias de servicio con una coincidencia máxima = 50.  
  
    -   **Realiza el seguimiento de instancias de servicio** consulta busca instancias de servicio controladas.  
  
    -   **Instancias completas** consulta busca instancias de servicio controladas con el estado completado.  
  
    -   **Instancias finalizadas** consulta busca instancias de servicio controladas con el estado finalizado.  
  
    -   **Eventos de mensajes controlados** consulta busca eventos de seguimiento de mensajes.  
  
    -   **Eventos de error de transmisión** consulta busca eventos de mensajes de seguimiento con un tipo de evento de error de transmisión.  
  
-   El **informes de estado de EDI** y **informes de estado de EDIINT** secciones, situadas en la parte inferior de la página concentrador de grupo, muestra cuatro informes acerca de intercambios EDI y otro sobre los intercambios AS2: el intercambio de EDI y estado de confirmación correlacionado informes, el informe de estado del lote, el informe de agregación de intercambio, el informe de agregación de conjunto de transacciones y el informe mensaje AS2 y estado de MDN correlacionado. Para obtener más información acerca de estos informes, consulte [EDI y los informes de estado de AS2](../core/edi-and-as2-status-reporting.md).  
  
    > [!NOTE]
    >  Las secciones Informes de estado de EDI y de EDIINT solo se mostrarán si las funciones EDI/AS2 están configuradas para este grupo BizTalk.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Estados de la instancia de servicio](../core/service-instance-states.md)  
  
-   [Investigación de orquestación, puerto y errores de mensaje](../core/investigating-orchestration-port-and-message-failures.md)  
  
-   [Uso de la pestaña de consulta de la consola de administración](../core/using-the-administration-console-query-tab.md)  
  
-   [Datos de instancia y los mensajes de seguimiento de visualización](../core/viewing-tracked-message-and-instance-data.md)  
  
-   [Seguimiento de estado y actividad](../core/health-and-activity-tracking.md)