---
title: "Supervisión de la solución de administración de procesos empresariales con SAE | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, monitoring
- monitoring, process management solutions
ms.assetid: 7c5fde9d-6eef-41c9-979c-ac7e5a172812
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26a8b795b90b75518f6c1ec21a6ca6d8f0f0d6a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-the-business-process-management-solution-with-bam"></a>Supervisar la solución Administración de procesos empresariales con SAE
La solución supervisa los pasos del procesamiento de pedidos con la API de Supervisión de la actividad económica (SAE). El diseño del proceso empresarial divide las actividades en varias fases. Después, las actividades se pueden volver a combinar para crear la sensación de un proceso continuo. SAE también suministra datos agregados para que pueda saber cuánto tardan los distintos servidores, cuántos pedidos se han finalizado y otros datos similares.  
  
 Al igual que la solución orientada a servicios, usa el nuevo **OrchestrationEventStream** objeto. Para obtener una descripción de la **OrchestrationEventStream** de objetos, vea "¿Qué es el objeto orchestrationeventstream?" en [supervisión de la solución orientada a servicios con BAM](../core/monitoring-the-service-oriented-solution-with-bam.md).  
  
 Para obtener información general acerca de BAM, consulte [usando Business Activity Monitoring](../core/using-business-activity-monitoring.md). Para obtener información sobre el Editor de perfiles de seguimiento (TPE), consulte [Editor de perfiles de seguimiento](../core/tracking-profile-editor.md).  
  
## <a name="wrapping-the-orchestrationeventstream-object"></a>Ajustar el objeto OrchestrationEventStream  
 Al igual que la solución orientada a servicios, la solución de administración de procesos empresariales ajusta el **OrchestrationEventStream** objeto. Y, al igual que la solución orientada a servicios, todos los métodos son estáticos de modo que las orquestaciones no tengan que crear instancias de objetos para usar los métodos. Esto también significa que los objetos utilizados en el seguimiento no tienen que estar serializados ni tendrán que guardarse (no tienen que ser serializables) si el motor deshidrata una orquestación. Sin embargo, incluye la solución de administración de procesos empresariales, **OrchestrationEventStream** con varios objetos de todas ellas derivados de una sola, objeto abstracto.  
  
 La clase abstracta es **BasicActivity**. Aunque es abstracta, la clase no sirve realmente como plantilla para las clases derivadas. En su lugar, mediante sus métodos estáticos, proporciona un conjunto de métodos disponibles sin calificación en una clase derivada. Esto le proporciona en esencia cuatro implementaciones predeterminadas de los métodos. Los cuatro métodos estáticos son: **CreateActivityId**, **BeginActivity**, **UpdateActivity**, y **EndActivity**.  
  
 La clase sobrecarga el **BeginActivity** método. Una versión de éste toma un nombre de actividad como argumento único, crea un GUI para utilizarlo como identificador de la actividad y, después, llama a una versión de sí mismo que toma un nombre de actividad y un identificador de actividad y, a continuación, devuelve el identificador de actividad. Esta versión de argumento único resulta útil en los casos en los que un pedido podría no tener un identificador único.  
  
 El **CreateActivityId** método toma una cadena y un identificador único, como el identificador de solicitud y devuelve una cadena que se concatena con un carácter de subrayado. Esto proporciona un identificador de actividad único y se utiliza de forma exhaustiva en las clases derivadas. El **BeginActivity**, **UpdateActivity**, y **EndActivity** métodos llamada la **BeginActiviy**, **UpdateActivity** , y **EndActivity** métodos de **OrchestrationEventStream**.  
  
 La solución deriva clases de **BasicActivity** para el agente de pedido (**CustomerOrderRequest**), Administrador de pedidos (**OrderManager**) y las fases de procesamiento ( **ServiceOrderRequest**). Cada una de las clases corresponde a una actividad. Cada clase proporciona una cadena para el nombre de la actividad que se usará en **CreateActivityId** para crear la actividad identificador, así como los métodos especializan para los hitos de actividad.  
  
 Puesto que el agente de pedido entrega el pedido y recibe una respuesta después, incluye un método para recuperar el identificador de actividad enviado al identificador de solicitud del pedido. Esto permite que el proceso empresarial siga realizando un seguimiento de los elementos finales del procesamiento del pedido.  
  
> [!NOTE]
>  Si envía los pedidos mediante la función de archivo en vez de la aplicación Web de atención al cliente, deberá agregar un identificador único a cada solicitud.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar una solución de administración de procesos empresariales](../core/developing-a-business-process-management-solution.md)