---
title: ¿Qué es una vista de actividad? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], Activity view [Tracking Profile Editor]
- activities [BAM], definitions
- Tracking Profile Editor, Activity view
- Activity view [Tracking Profile Editor]
ms.assetid: ae6bcdc8-e426-4148-b83d-08a1a5e99ca3
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48cbf2419f1d3ab0939ed1607df7c17e1ea3f8d1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997949"
---
# <a name="what-is-an-activity-view"></a>¿Qué es una vista de actividad?
Una vista de actividad contiene la definición de actividad de BAM importada que se crea con el complemento de BAM para Excel. La definición de actividad de BAM es un resumen de los requisitos de seguimiento para el proceso empresarial. Una actividad puede abarcar varias orquestaciones y puertos. La definición de actividad debe importarse una vez y asignarse a cada orquestación o artefacto de mensajería que coincida con alguna parte de la definición.  
  
 El vínculo de la vista de actividad se encuentra en el panel izquierdo de la interfaz de usuario del Editor de perfiles de seguimiento (TPE).  
  
## <a name="activity-view-elements"></a>Elementos de la vista de actividad  
 La vista de actividad muestra la estructura global del perfil de seguimiento en una vista de árbol, e incluye los elementos siguientes:  
  
- Hitos  
  
- Elementos de datos para la actividad  
  
- Orígenes de eventos  
  
- Orígenes de datos  
  
  **Hitos**: los hitos son objetos que definen un punto en un proceso determinado. Existen tres formas de obtener acceso a los hitos:  
  
- Puede arrastrar una forma desde una programación de orquestación, y la hora de finalización de ejecución de dicha forma se enviará desde BAM como valor del hito.  
  
- Puede arrastrar una propiedad de mensajería, desde una representación esquemática de la derecha hasta un hito de destino.  
  
- Puede arrastrar un nodo de esquema de carga de mensaje que contenga un valor de hito.  
  
  > [!NOTE]
  >  Los nodos de esquema de tipo DATETIME ONLY se evalúan en tiempo de ejecución. Cualquier conversión o problema de conversión en tiempo de ejecución dará lugar a un error de seguimiento en el registro de eventos.  
  
  **Elementos de datos**: elementos de datos son objetos que definen un elemento determinado de un esquema XML para una instancia de mensaje, el sistema o la propiedad promocionada. Para obtener acceso al elemento de datos, expanda el esquema para encontrar y seleccionar el elemento que le interesa, y arrastre el elemento hasta la carpeta apropiada de tipo de elemento de datos. La información sobre los elementos de datos (por ejemplo, XPath) se almacena en el perfil.  
  
> [!NOTE]
>  TPE admite solo elementos de datos que tengan una representación cero a uno, tal como se define en el esquema de mensaje de un campo de datos concreto. Pueden producirse errores en el seguimiento de orquestaciones si existen elementos de datos con representaciones en una proporción superior. En estas situaciones, no se almacena ningún dato en la base de datos de importación principal de BAM. Si no se produce ningún error, no se sabrá con seguridad de qué elemento de datos se está efectuando el seguimiento.  
  
> [!NOTE]
>  Los programadores de BAM deben saber que las propiedades se rellenan de acuerdo con las reglas de proceso de BizTalk Server, y no de BAM.  
>   
>  Por ejemplo, en el adaptador de SMTP, las propiedades de contexto como SMTPServer, CC y De, no contendrán ningún valor a menos que se rellenen de forma explícita. Una vez que se hayan rellenado, sus valores aparecerán en la base de datos de importación principal de BAM, y estarán disponibles para seguimiento.  
  
## <a name="activity-view-context-menus"></a>Menús contextuales de vista de actividad  
 Los menús contextuales de acciones disponibles para la vista de actividad cambian dinámicamente en función del nodo seleccionado en la vista Orquestación. Por ejemplo, si selecciona un nodo de carpeta de actividad, el menú contextual contendrá los elementos de menú contextual de la carpeta de actividad.  
  
 Para asociar eventos y datos a los elementos de la actividad empresarial, arrástrelos desde la ventana de eventos de origen, a la derecha, hasta el nodo de eventos o datos de la vista de actividad.  
  
 Para obtener acceso a los menús contextuales de la vista de actividad, haga clic con el botón secundario en uno de los nodos del árbol. La pantalla siguiente muestra el nodo raíz de las vistas de actividad. En las tablas siguientes se describen los elementos de los menús contextuales de los nodos de una vista de actividad.  
  
 **Nodo raíz de árbol de definición de actividad**  
  
 ![](../core/media/activityviewcontextmenu.gif "activityviewcontextmenu")  
  
|Elemento de menú|Uso|  
|---------------|-----------|  
|Nueva Continuation|Inserta una nueva carpeta Continuation en el árbol de actividades. Asigne el valor de esta carpeta desde el segmento de código fuente de una continuación.<br /><br /> Se utiliza de forma conjunta con una carpeta ContinuationID a fin de pasar el procesamiento entre varios componentes que completan la misma actividad. Ejemplos de estos componentes son las orquestaciones, puertos, BufferedEventStreams y DirectEventStreams de BizTalk. **Nota:** los nombres de carpeta de continuación pueden contener un máximo de 127 caracteres.|  
|Nuevo ContinuationID|Inserta una nueva carpeta ContinuationID en el árbol de actividades. Esta carpeta se asigna al segmento “continued-to” de una continuación. Por ejemplo, si la orquestación A sigue a la orquestación B, esta carpeta debe asignarse a un elemento de la orquestación B.<br /><br /> Se utiliza de forma conjunta con una carpeta Continuation a fin de pasar el procesamiento entre varios componentes que completan la misma actividad. Ejemplos de estos componentes son las orquestaciones, puertos, BufferedEventStreams y DirectEventStreams de BizTalk. **Nota:** los nombres de carpetas ContinuationID pueden contener un máximo de 127 caracteres.|  
|Nueva relación|Inserta una nueva carpeta de relación en el árbol de actividades. Se utiliza para publicar la relación entre actividades que forman una vista. **Nota:** los nombres de carpeta de relación pueden contener un máximo de 128 caracteres. Esto incluye el nombre de servidor y el nombre de base de datos de administración de BizTalk.|  
|Nueva Document Reference URL|Inserta una nueva carpeta Document Reference URL en el árbol de actividades. Se utiliza para definir una URL de referencia en una ubicación que contenga un documento relacionado con esta actividad. **Nota:** los nombres de carpeta Document Reference URL pueden contener un máximo de 128 caracteres.|  
  
 **Nodo de propiedad**  
  
|Elemento de menú|Uso|  
|---------------|-----------|  
|Asociar datos seleccionados|Se utiliza para crear una asociación entre un elemento de datos de carga de mensaje o de propiedad de contexto y la carpeta de elemento de datos Actividad de BAM.|  
  
 **Nodo de eventos**  
  
|Elemento de menú|Uso|  
|---------------|-----------|  
|Asociar con el final de la acción seleccionada|Se utiliza para crear una asociación entre una forma de orquestación, elemento de datos de carga de mensaje DateTime o de propiedad de contexto, y la carpeta de hitos Actividad de BAM.|  
  
## <a name="see-also"></a>Vea también  
 [Implementar actividades de BAM con secuencias de eventos](../core/implementing-bam-activities-with-event-streams.md)   
 [Definir actividades económicas y vistas en Excel](../core/defining-business-activities-and-views-in-excel.md)   
 [Componentes del TPE](../core/components-of-the-tpe.md)