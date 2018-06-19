---
title: Algunos principios de la solución de administración de procesos empresariales de diseño | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business processes, design principals
- designing, design principals
- process management solution tutorial, dividing business processes
- patterns [process management solutions], design principals
ms.assetid: 688b970f-8e64-4a47-bcc5-bdb9c5195902
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b975f94853c155da41f09b2b0ff76a681c1df075
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279364"
---
# <a name="some-design-principles-in-the-business-process-management-solution"></a>Algunos principios de diseño en la solución Administración de procesos empresariales
Este tema comienza con directrices generales acerca de cómo dividir los procesos empresariales en etapas. Más adelante, considera la estructura de algunas de las orquestaciones, ensamblados y aplicaciones de la solución en relación con estas directrices y los requisitos empresariales. Para obtener más información acerca de los requisitos empresariales, vea "Requisitos empresariales" en [descripción de la solución de administración de procesos empresariales](../core/understanding-the-business-process-management-solution.md).  
  
## <a name="dividing-business-processes"></a>Dividir procesos empresariales  
 Habitualmente, al considerar un proceso empresarial, el primer impulso suele ser tratarlo como un proceso único monolítico. Este diseño no es siempre el mejor. Para Southridge Video, un pedido es un proceso empresarial de larga ejecución, cuya finalización puede durar hasta un año. Durante este tiempo, el proceso empresarial en sí puede cambiar. Para permitir actualizaciones al proceso empresarial sin interrumpir los pedidos en curso, el procesamiento de pedidos de Southridge Video se divide en fases.  
  
 El punto en el que se divide el proceso es esencial para las partes del proceso cuyas versiones se pueden controlar y los tipos de interrupciones que se permiten a los pedidos pendientes. La solución de Southridge Video utiliza cuatro criterios generales para determinar las fases:  
  
-   El agrupamiento lógico de pasos en el proceso empresarial.  
  
-   El ámbito de las operaciones dentro de una orquestación.  
  
-   Los elementos del proceso cuyas versiones podría ser útil controlar, en función del proceso empresarial.  
  
-   Una orquestación debería finalizar tras completar una operación de larga duración.  
  
 De los cuatro criterios, el primero y el tercero son los más importantes porque normalmente habrá muchos más ámbitos de operaciones que agrupamientos lógicos o elementos obvios cuyas versiones sería útil controlar. Sin embargo, tenga en cuenta que no debe finalizar una orquestación en medio de un ámbito.  
  
 Si observa la orquestación para la primera fase, **CableOrder1.odx**, verá que termina de forma efectiva con la secuencia de respuesta de la solicitud al sistema de distribución. Éste es un buen punto para finalizar la fase porque es la parte del proceso que implica el trabajo físico real de finalizar el pedido. Que los pasos de procesamiento largo estén cerca del final de la orquestación garantiza que, al rehidratarse, la orquestación finalice rápidamente. Esto agiliza el traslado de la solución completa a versiones más nuevas de las orquestaciones.  
  
> [!NOTE]
>  Aunque la solución divide el proceso en fases discontinuas, la supervisión de la solución le permite ver los elementos en una vista continua mediante el uso de SAE.  
  
## <a name="order-action-broker-and-manager-orchestrations"></a>Orquestaciones acción de pedido, agente de pedido y administrador de pedidos  
 Además de dividir el procesamiento del pedido en fases, observará que cada una de las acciones del pedido, por ejemplo, analizar el pedido, validar el pedido, cancelar el pedido, está en una orquestación independiente. La colocación de cada acción en una orquestación independiente separa las acciones de la estructura de las fases. Esto permite a su vez una mayor flexibilidad en el diseño y control de versiones de las fases de procesamiento del pedido.  
  
 El agente de pedido y el administrador de pedidos están en orquestaciones independientes por motivos similares. El diseño de solución permite utilizar varios administradores de pedido para controlar otros tipos de pedidos. La separación del agente y el administrador también permite que estén en diferentes ubicaciones. Para obtener más información acerca del diseño del agente de pedido, vea "¿por qué agente de pedido?" en [de procesamiento en la orquestación OrderBroker](../core/processing-in-the-orderbroker-orchestration.md). Para obtener los detalles del administrador, consulte [lógica del Administrador de procesos](../core/process-manager-logic.md).  
  
## <a name="assemblies"></a>Ensamblados  
 Los ensamblados en la solución están organizados para admitir la creación de versiones de los componentes y el traslado de los componentes a otros servidores. Por ejemplo, los esquemas están en ensamblados independientes. En concreto, los esquemas para el agente de pedido están en su propio ensamblado. Esto permite controlar las versiones sin cambiar otros elementos de la solución. También hace más fácil trasladar el agente de pedido a otro grupo o servidor. Para obtener más información acerca de las versiones de la aplicación y ensamblados de esquema, consulte [control de versiones de la solución de administración de procesos empresariales](../core/versioning-the-business-process-management-solution.md).  
  
## <a name="applications"></a>Aplicaciones  
 Si observa en la consola de administración de BizTalk, puede ver que la solución generada está compuesta por tres aplicaciones independientes:  
  
-   **BTSScn.BPM.OrderBrokerApp**, la aplicación que contiene el agente de pedido  
  
-   **BTSScn.BPM.CableOrderApp**, la aplicación que contiene los componentes de procesamiento de pedidos  
  
-   **BTSScn.BPM.MessagingApp**, una aplicación que recopila artefactos compartidos por las otras dos aplicaciones  
  
 La estructura tripartita de la solución es posible porque las aplicaciones de BizTalk tienen la capacidad de utilizar artefactos en otras aplicaciones dentro del mismo grupo de BizTalk. Para utilizar los artefactos de otra aplicación, se agrega una referencia a la otra aplicación desde la aplicación que hace referencia. Para obtener información sobre cómo hacer referencia a otras aplicaciones, consulte [cómo agregar una referencia a otra aplicación](../core/how-to-add-a-reference-to-another-application.md).  
  
 Colocar los artefactos comunes en una aplicación independiente le permite actualizar los componentes en un único sitio. Los componentes compartidos pueden ser de cualquier tipo, puertos incluidos. Por ejemplo, las orquestaciones en la solución envían errores a un puerto de notificación de errores. Dicho puerto está en la aplicación de mensajería, BTSScn.BPM.MessagingApp, donde puede utilizarlo toda la solución.  
  
 La estructuración de la solución en tres aplicaciones también facilita el traslado de partes de la solución a otros servidores. Puede convertir cada aplicación y las aplicaciones a las que ésta hace referencia en un archivo MSI. A continuación, puede instalar el archivo MSI en otro equipo. Para obtener información sobre cómo convertir aplicaciones en archivos MSI, consulte [cómo exportar una aplicación de BizTalk](../core/how-to-export-a-biztalk-application.md).  
  
### <a name="the-test-solution"></a>La solución de prueba  
 Tendrá que también tres aplicaciones de prueba en la consola de administración de BizTalk: **BTSScn.BPM.OrderBrokerApp.Test**, **BTSScn.BPM.CableOrderApp.Test**, y  **BTSScn.BPM.MessagingApp.Test**. Estas tres aplicaciones contienen sólo los puertos para la aplicación de prueba y las aplicaciones principales hacen referencia a éstas. Esta estructura permite que las aplicaciones principales utilicen los puertos de prueba para crear una solución de prueba al mismo tiempo que se separan los puertos de prueba de la solución.  
  
## <a name="see-also"></a>Vea también  
 [Aspectos destacados de la implementación de la solución de administración de procesos empresariales](../core/implementation-highlights-of-the-business-process-management-solution.md)   
 [Patrones de la solución de administración de procesos empresariales](../core/patterns-in-the-business-process-management-solution.md)