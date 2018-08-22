---
title: Uso de varias continuaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 01a38087-71ee-40b3-a957-6a2653bd6435
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78468438dbd04583f8936bab28e80bf400e83d72
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987141"
---
# <a name="using-multiple-continuations"></a>Usar varias continuaciones
Usar el Editor de perfiles de seguimiento (TPE) en entornos donde hay varias actividades requiere una comprensión adecuada del escenario en que se realiza el seguimiento de estas actividades, a fin de asignar los puertos de recepción, las orquestaciones y los puertos de envío en el orden correcto.  
  
 En un perfil de seguimiento, el TPE evalúa el principio y el final de la actividad de manera automática. La actividad se inicia cuando se recopila el primer dato y finaliza cuando se recopila el último.  
  
 En la mayoría de los casos, crear una sola continuación, como una continuación entre dos orquestaciones, constituye un proceso sencillo para los programadores. Cuando el TPE da muestras de complejidad es cuando se requieren varias continuaciones. Un escenario de varias continuaciones es aquél en que una actividad de Supervisión de la actividad económica (BAM) abarca varios puertos de recepción, orquestaciones y puertos de envío. Para recopilar los datos de BAM en un mismo registro, debe crear continuaciones entre todas las programaciones de BizTalk Server. Este proceso puede resultar complejo cuando se completa mediante la interfaz de usuario del TPE.  
  
 En este tema se describe cómo crear una y varias continuaciones en distintos escenarios.  
  
#### <a name="base-scenario-description---multiple-receive-ports-orchestrations-and-send-ports"></a>Descripción del escenario básico: varios puertos de recepción, orquestaciones y puertos de envío  
 El escenario consiste en un servidor de BizTalk que tiene varios puertos de recepción (R), orquestaciones (O) y puertos de envío (S). Existe una propiedad de contexto interchangeID genérica que se usa para vincular las continuaciones. Puede usar cualquier propiedad de contexto, como activityID u otro identificador exclusivo. La elección del contenido específico no es relevante para la explicación del escenario.  
  
 A efectos del escenario, no se especifican explicaciones sobre los datos, hitos ni valores de propiedades de contexto cuyo seguimiento se realiza desde estos puertos y orquestaciones. Esa parte de la asignación corresponde a la lógica empresarial. El objetivo es capturar todos los datos de BAM de todos los puertos y las orquestaciones en una misma fila de la tabla de actividad completada. Las distintas maneras en que se puede recibir y procesar un mensaje en las orquestaciones presenta algunos desafíos y soluciones interesantes.  
  
> [!NOTE]
>  El escenario de un puerto o una orquestación puede considerarse un caso especial del escenario de varios puertos y varias orquestaciones.  
  
#### <a name="scenario-solution-1---one-receive-port-and-one-orchestration"></a>Solución de escenario 1: un puerto de recepción y una orquestación  
 En este escenario, un mensaje llega exactamente a uno de los puertos de recepción (R1) y lo procesa exactamente una de las orquestaciones (O1).  
  
 El proceso de creación de la continuación es el siguiente:  
  
1. Cree una continuación en la vista de árbol de actividades de carpeta del perfil de seguimiento.  
  
2. Elija el esquema de propiedades de contexto haciendo clic en el **Seleccionar origen de eventos** botón y, a continuación, haga clic en el **Seleccionar propiedad de contexto** elemento de menú.  
  
3. Busque el **propiedad interchangeId** en el **nombre de la propiedad de contexto** lista y, a continuación, selecciónelo.  
  
4. Desde el esquema de propiedades, asigne interchangeID a la carpeta de continuación que acaba de crear.  
  
5. Haga clic con el botón secundario en el nodo interchangeID recién creado en el árbol de actividades y seleccione los puertos desde los que efectuar las asignaciones.  
  
6. En el **seleccionar puertos** cuadro de diálogo que aparece, seleccione todos **N** puertos de recepción.  
  
7. Cree una carpeta continuationID en el árbol de actividades de carpeta.  
  
8. Abra cada orquestación haciendo clic en el **Seleccionar origen de eventos** botón y, a continuación, haga clic en el **seleccionar programación de orquestación** elemento de menú. En cada orquestación, haga clic con el botón secundario en una forma de la orquestación y asigne la propiedad de contexto interchangeID al continuationID recién creado.  
  
   En una implementación con tres orquestaciones, la apariencia del perfil de seguimiento será parecida a la siguiente:  
  
   ![TPE escenario de continuación múltiple 1](../core/media/4761d680-7218-4404-a636-06739f70f344.gif "4761d680-7218-4404-a636-06739f70f344")  
  
#### <a name="scenario-solution-2---one-receive-port-and-multiple-orchestrations"></a>Solución de escenario 2: un puerto de recepción y varias orquestaciones  
 En este escenario, un mensaje llega exactamente a uno de los puertos de recepción y lo procesan todas y cada una de las orquestaciones. Esto sucede porque el mensaje se envía simultáneamente a todas las orquestaciones.  
  
 En este caso, se necesita una continuación y un continuationID para cada orquestación. El proceso de creación de las continuaciones sería similar a los pasos descritos en la solución de escenario 1. Para una implementación con tres orquestaciones, el perfil de seguimiento resultante tiene un aspecto similar al siguiente:  
  
 ![Escenario de continuación múltiple TPE 2](../core/media/3cebd82f-9192-4d52-84c7-584f24e8ecca.gif "3cebd82f-9192-4d52-84c7-584f24e8ecca")  
  
#### <a name="scenario-solution-3---content-based-routing"></a>Solución de escenario 3: enrutamiento por contenidos  
 En este escenario se define una solución de enrutamiento (CBR) por contenidos. Un mensaje llega exactamente a uno de los puertos de recepción y se envía exactamente a uno de los puertos de envío. Este enrutamiento se produce según el valor de una propiedad de contexto del mensaje. En este caso, solo se necesita una continuación. La asignación tiene una apariencia similar a la siguiente:  
  
 ![Escenario de continuación CBR. ](../core/media/4459a73d-515f-4d6d-a68f-b18eee072df8.gif "4459a73d-515f-4d6d-a68f-b18eee072df8")  
  
> [!NOTE]
>  La asignación anterior también es válida para un mensaje que llega exactamente a uno de los puertos de recepción y se envía a todos los puertos de envío.  
  
#### <a name="scenario-solution-4---one-orchestration-multiple-send-ports"></a>Solución de escenario 4: una orquestación y varios puertos de envío  
 En este escenario, hay varios envío. puertos. Un mensaje se procesa exactamente una de las orquestaciones, que viene determinada por las reglas de procesamiento y se envía a todos los puertos de envío. En este caso, solo se necesita una continuación. La asignación tiene una apariencia similar a la siguiente:  
  
 ![Escenario de continuación 4](../core/media/3ab10b51-d306-4ad1-acb6-6731e23394ac.gif "3ab10b51-d306-4ad1-acb6-6731e23394ac")  
  
#### <a name="scenario-solution-5---sequential-orchestrations"></a>Solución de escenario 5: orquestaciones secuenciales  
 En este escenario, un mensaje se procesa secuencialmente por cada orquestación, una a una, y se pasa a la siguiente orquestación mediante la continuación. La asignación tiene una apariencia similar a la siguiente:  
  
 ![Escenario de continuación 5](../core/media/563cacee-104c-4f8a-9836-da90aecb7487.gif "563cacee-104c-4f8a-9836-da90aecb7487")  
  
### <a name="collecting-data-in-an-asynchronous-environment"></a>Recopilar datos en un entorno asíncrono  
 Cuando se configuran continuaciones, BAM espera la llegada de datos. En un entorno asíncrono, es posible que no se reciba respuesta de un proceso de servidor.  
  
 Si no se reciben los datos de respuesta, la instancia de actividad espera por tiempo indefinido. La actividad nunca se completa y los registros permanecen en las tablas de la base de datos de importación principal de BAM. Piense en el caso de las transacciones de larga ejecución, en las que no existe ningún modo de saber cuándo llegarán los datos restantes. No existe ningún tiempo de espera, puesto que la llegada de los datos dependerá de los procesos o la lógica empresariales, tras los cuales la actividad se marca como completa. Los datos pueden llegar el mismo día o, en un caso extremo, el año próximo.  
  
 La solución consiste en usar actividades relacionadas.  
  
 Divida la actividad en dos actividades. Relacione ambas entre sí y relacione la respuesta a la actividad original.  
  
 Para obtener más información acerca de las actividades relacionadas, consulte [relaciones de actividades](../core/activity-relationships.md).  
  
## <a name="see-also"></a>Vea también  
 [Editor de perfiles de seguimiento](../core/tracking-profile-editor.md)