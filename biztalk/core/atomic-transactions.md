---
title: Las transacciones atómicas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- atomic transactions
- scopes, examples
- transactions, orchestrations
- orchestrations, transactions
- transactions, isolation levels
- transactions, ACID concept
- transactions, examples
- transactions, atomic
- scopes, transactions
- scopes
ms.assetid: 5030e1fd-943f-42bc-9296-4f315bd5f733
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8319f93d4e03dfde94b1cb3b9d099470592b1893
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986845"
---
# <a name="atomic-transactions"></a>Transacciones atómicas
Las orquestaciones de BizTalk pueden diseñarse para ejecutar elementos discretos de trabajo, siguiendo el clásico concepto "ACID" de una transacción. Estas unidades discretas o atómicas de trabajo, cuando se ejecutan, llevan el proceso empresarial de un estado coherente a un estado nuevo, coherente y duradero que se aísla de otras unidades de trabajo. Normalmente, esto se realiza mediante el **ámbito** que encapsula las unidades de trabajo con la semántica transaccional. También se puede definir la orquestación completa como una transacción atómica sin el uso de ámbitos. No obstante, los ámbitos no pueden marcarse como transaccionales a menos que la propia orquestación se marque como transacción atómica o de larga duración. Las transacciones atómicas garantizan que todas las actualizaciones parciales se revertirán automáticamente si se produce un error durante la actualización de la transacción, y los efectos de la transacción se borrarán (excepto los efectos de cualquier llamada .NET que se haga en la transacción). Las transacciones atómicas en orquestaciones de BizTalk se parecen a las transacciones del coordinador de transacciones distribuidas (DTC) en que suelen ser de corta duración y tener los cuatro atributos "ACID" (atomicidad, coherencia, aislamiento y durabilidad):  
  
- **Atomicidad**  
  
   Una transacción representa una unidad atómica de trabajo. En una transacción se realizan todas las modificaciones o ninguna de ellas.  
  
- **Coherencia**  
  
   Cuando se confirma, una transacción debe preservar la integridad de los datos dentro del sistema. Si una transacción realiza una modificación de datos en una base de datos que era coherente internamente antes de que se iniciase la transacción, debe seguir siéndolo una vez confirmada ésta. El programador de la aplicación es el principal responsable de garantizar esta propiedad.  
  
- **Aislamiento**  
  
   Las modificaciones realizadas por transacciones simultáneas se deben aisladas de las modificaciones efectuadas por otras transacciones simultáneas. Las transacciones aisladas que se ejecutan simultáneamente realizan modificaciones que conservan la coherencia interna de la base de datos, del mismo modo que si se tratara de transacciones ejecutadas en serie.  
  
- **Durabilidad**  
  
   Una vez confirmada una transacción, todas las modificaciones permanecen en el sistema de forma predeterminada. Las modificaciones persisten aunque se produzca un error del sistema.  
  
  Las transacciones atómicas utilizadas en orquestaciones de BizTalk admiten los siguientes niveles de aislamiento:  
  
- **Lectura confirmada**  
  
   Los bloqueos compartidos se mantienen durante la lectura de los datos para evitar lecturas no actualizadas, pero los datos pueden cambiarse antes del fin de la transacción, lo que daría lugar a lecturas no repetibles o a datos ficticios.  
  
- **Lectura repetible**  
  
   Se colocan bloqueos en todos los datos utilizados en una consulta, lo que impide que otros usuarios actualicen los datos. De este modo, se evitan lecturas no repetibles, pero todavía pueden aparecer filas ficticias.  
  
- **Serializable**  
  
   Se coloca un bloqueo de intervalo que impide que otros usuarios actualicen o inserten filas en la base de datos hasta que no se complete la transacción.  
  
  BizTalk Server garantiza que el estado de los cambios dentro de una transacción atómica, como las modificaciones a las variables, mensajes y objetos, son visibles fuera del ámbito de la transacción atómica únicamente al confirmarse la transacción. Los cambios de estado intermedios se aíslan de otras partes de una orquestación.  
  
> [!NOTE]
>  Si una transacción atómica contiene una **recepción** forma, un **enviar** forma, o un **Iniciar orquestación** forma, las acciones correspondientes no llevará a cabo hasta que el ha confirmado la transacción.  
  
 Si necesita propiedades ACID completas en los datos, por ejemplo, cuando los datos se deben aislados de otras transacciones, debe utilizar transacciones atómicas exclusivamente.  
  
 Cuando se producen errores en una transacción atómica, todos los estados se restablecen como si la instancia de orquestación nunca hubiese entrado en el ámbito. La regla que BizTalk aplica a transacciones atómicas es que todas las variables (no solo las locales para el ámbito) participen en la transacción. Todas las variables y mensajes no serializables utilizados en una transacción atómica deben declararse como locales para el ámbito; en caso contrario, el compilador mostrará el error que indica que la variable en cuestión no está marcada como serializable. Se presupone que todos los ámbitos atómicos están "sincronizados" y el compilador de orquestaciones mostrará una advertencia sobre uso redundante si, en efecto, se utiliza la palabra clave "synchronized" para ámbitos atómicos. La sincronización de los datos compartidos va desde el inicio del ámbito hasta la correcta finalización de éste (incluida la persistencia de estado al final del ámbito), o bien hasta la finalización del controlador de excepción (en caso de que se produzcan errores). El dominio de sincronización no se extiende al controlador de compensación.  
  
 Las transacciones atómicas pueden asociarse a valores de tiempo de espera, momento a partir del cual la orquestación detendrá la transacción y la instancia se suspenderá. Si una transacción atómica contiene una forma Recepción, una forma Envío o una forma Iniciar orquestación, las acciones correspondientes no se llevarán a cabo hasta que no se haya confirmado la transacción.  
  
 Una transacción atómica se reintenta cuando el usuario lanza deliberadamente una **RetryTransactionException** o si un **PersistenceException** se genera en el momento en que la transacción atómica intenta confirmar. Esto último ocurriría si, por ejemplo, la transacción atómica formase parte de una transacción DTC distribuida y algún otro participante en dicha transacción la detuviese. Del mismo modo, si había problemas de conectividad de base de datos en el momento cuando la transacción se intenta confirmar, también habrá un **PersistenceException** genera. Si se trata de un ámbito atómico que tiene **vuelva a intentar = True**, a continuación, se volverá a intentar hasta 21 veces. El intervalo predeterminado entre cada reintento es de dos segundos (pero se puede modificar). Una vez concluidos los 21 reintentos, si sigue sin poder confirmarse la transacción, se suspenderá la instancia de toda la orquestación. Se puede reanudar manualmente y volverá a comenzar, con un contador nuevo, desde el principio del ámbito atómico infractor.  
  
> [!NOTE]
>  Solo el **RetryTransactionException** y **PersistenceException** puede provocar un ámbito atómico volver a intentar. Cualquier otra excepción que se produce en un ámbito atómico no puede hacer que vuelva a intentar, incluso si la **vuelva a intentar** propiedad está establecida en **True**. El retraso predeterminado de dos segundos entre dos reintentos consecutivos puede invalidarse mediante el uso de una propiedad pública en **RetryTransactionException** (si es la excepción que se usa para hacer que los reintentos).  
  
 Los ámbitos atómicos tienen restricciones relativas a la anidación de otras transacciones que no se pueden anidar transacciones ni incluir **Catch - Exception** bloques.  
  
## <a name="dtc-transactions"></a>Transacciones DTC  
 Aunque las transacciones atómicas se comportan como transacciones DTC, no equivalen explícitamente a transacciones DTC de forma predeterminada. Puede convertirlas explícitamente en transacciones DTC, siempre que los objetos utilizados en la transacción sean objetos COM+ derivados de System.EnterpriseServices.ServicedComponents, y que los niveles de aislamiento coincidan entre los componentes de la transacción.  
  
> [!NOTE]
>  Una transacción atómica no puede contener cualquier otra transacción ni controladores de excepción.  
  
> [!NOTE]
>  Una transacción atómica no puede contener envío coincidente y las acciones de recepción, que es un par solicitud-respuesta o un envío y recepción que utilizan el mismo conjunto de correlación.  
  
## <a name="non-serializable-objects"></a>Objetos no serializables  
 Si desea utilizar un objeto no serializable dentro de una orquestación, debe utilizarlo únicamente dentro de una transacción atómica. Cualquier uso de un objeto de este tipo fuera de una transacción atómica supone un riesgo en lo que a pérdida de datos se refiere cuando el motor guarda la orquestación.  
  
> [!CAUTION]
>  Cada ámbito atómico representa un punto de persistencia y esto significa que el estado de la orquestación se guarda en la base de datos en cada punto de persistencia. El uso extensivo del ámbito atómico aumentará la latencia de la orquestación. En lugar de utilizar un ámbito atómico para crear objetos no serializables, puede utilizar llamadas a métodos estáticos que no requieren ámbitos atómicos, lo que elimina la necesidad de puntos de persistencia.  
  
## <a name="see-also"></a>Vea también  
 [Escenarios de uso de transacciones atómicas](../core/scenarios-using-atomic-transactions.md)   
 [Transacciones de ejecución prolongada](../core/long-running-transactions.md)