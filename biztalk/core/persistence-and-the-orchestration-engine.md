---
title: Persistencia y el motor de orquestaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestration engine, persistence
- persistence
- orchestration engine, serialization
ms.assetid: 088230ef-13b3-440b-9875-6449f29dd5c6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e9e1c8b158d313681a6e1374a586ca957b1aa15
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264932"
---
# <a name="persistence-and-the-orchestration-engine"></a>Persistencia y el motor de orquestaciones
La persistencia de los estados, su administración y restauración constituyen la base de muchas de las funcionalidades fundamentales del motor de orquestaciones. En particular, la persistencia es crítica para el funcionamiento correcto de:  
  
-   Deshidratación y rehidratación  
  
-   Ejecución agnóstica del equipo y rehidratación  
  
-   Modelo de compensación  
  
-   Cierre controlado del sistema  
  
-   Recuperación  
  
 El motor de orquestaciones guarda toda la información de estado de las instancias de orquestación en ejecución en varios puntos en el almacenamiento persistente, de modo que las instancias se puedan restaurar posteriormente en la memoria. El estado incluye:  
  
-   El estado interno del motor, incluido su progreso actual  
  
-   El estado de cualquier componente .NET que mantenga información de estado y que utilice la orquestación  
  
-   Valores de variables y mensajes  
  
## <a name="persistence-points"></a>Puntos de persistencia  
 El motor de orquestaciones guarda el estado de una instancia de orquestación en ejecución en varios puntos. Si la instancia de orquestación se debe rehidratar, iniciar a partir de un cierre controlado o recuperar desde un cierre inesperado, ésta se ejecutará desde el último punto de persistencia como si nada hubiera ocurrido. Por ejemplo, si se recibe un mensaje pero se produce un cierre inesperado antes de que se pueda guardar el estado, el motor no registrará que se ha recibido el mensaje y lo volverá a recibir después de reiniciarse. El motor guardará el estado de una orquestación cuando se produzcan las siguientes circunstancias:  
  
-   Se alcanza el final de un ámbito transaccional.  
  
    -   El motor guarda el estado al final de un ámbito transaccional de modo que el punto desde el que se debe reanudar la orquestación esté definido de forma no ambigua y que, por tanto, se pueda llevar a cabo correctamente dicha compensación si es necesario.  
  
    -   La orquestación seguirá ejecutándose desde el final del ámbito si la persistencia es correcta; en caso contrario, se invocará el controlador de excepción apropiado.  
  
    -   Si el ámbito es transaccional y atómico, el motor guardará el estado al final del ámbito atómico cuando realice la confirmación.  
  
    -   Si el ámbito es transaccional y de larga ejecución, el motor generará una nueva transacción y almacenará el estado completo de tiempo de ejecución cuando se complete el ámbito.  
  
-   Se alcanza un punto de interrupción de depuración.  
  
-   Se envía un mensaje. La única excepción a esto es cuando se envía un mensaje desde un ámbito de transacción atómica.  
  
-   La orquestación inicia otra orquestación de forma asincrónica, al igual que con la **Iniciar orquestación** forma.  
  
-   La instancia de orquestación se suspende.  
  
-   Cuando se solicita el cierre del motor de orquestaciones, éste intenta guardar la información de control y el estado actual de todas las instancias de orquestación en ejecución, de modo que pueda reanudar la ejecución de dichas instancias cuando se vuelva a iniciar. Si el motor no consigue guardar el estado actual, reanudará la instancia de orquestación desde el último punto de persistencia que se haya producido antes del cierre. Esto se aplica al cierre del sistema de manera controlada, así como a la terminación anormal.  
  
-   El motor determina que la instancia se debe deshidratar.  
  
-   La instancia de orquestación se finaliza.  
  
## <a name="serialization"></a>Serialización  
 Todas las instancias de objetos a las que la orquestación haga referencia de forma directa o indirecta (como a través de otros objetos) deben ser serializables para que se pueda almacenar de forma persistente el estado de la orquestación. Hay dos excepciones:  
  
-   Puede haber un objeto no serializable declarado dentro de una transacción atómica. Esto es posible porque los ámbitos atómicos no contienen puntos de persistencia.  
  
-   System.Xml.XmlDocument no es una clase serializable; se considera un caso especial y se puede utilizar en cualquier lugar.  
  
> [!CAUTION]
>  Un objeto .NET debe estar marcado como serializable para que se pueda almacenar de forma persistente.  
  
> [!NOTE]
>  Los objetos COM no se pueden almacenar de forma persistente con procedimientos de serialización .NET estándar. Si desea llamar un objeto COM fuera de una transacción atómica, debe incluir el objeto COM en un objeto .NET que sea .NET serializable, además de saber cómo almacenarlo de forma persistente y cómo restaurar el estado del objeto COM.  
  
## <a name="system-shutdown"></a>Cierre del sistema  
 Cuando se solicita el cierre del motor de orquestaciones, éste intenta guardar la información de control y el estado actual de todas las instancias de orquestación en ejecución, de modo que pueda reanudar la ejecución de dichas instancias cuando se vuelva a iniciar. Si el motor no consigue guardar el estado actual, reanudará la instancia de orquestación desde el último punto de persistencia que se haya producido antes del cierre. Esto se aplica al cierre del sistema de manera controlada, así como a la terminación anormal.  
  
## <a name="recovery"></a>Recuperación  
 El motor guarda periódicamente la información de estado de una instancia de orquestación en el almacenamiento persistente y guarda también el estado en caso de cierre del sistema.  
  
 Cuando por cualquier motivo se produce un error anormal en una instancia de orquestación, la instancia se puede recuperar desde el último estado guardado y puede seguir ejecutándose como si no se hubiera producido ninguna interrupción. Esto ocurre aunque el servidor original en el que se ejecuta la instancia se quede sin servicio por algún motivo; la instancia puede simplemente reanudar la ejecución en un equipo distinto. Debido a este modelo de recuperación de varios servidores, ya no necesitará más la organización por clústeres.  
  
## <a name="see-also"></a>Vea también  
 [Orquestación deshidratación y rehidratación](../core/orchestration-dehydration-and-rehydration.md)