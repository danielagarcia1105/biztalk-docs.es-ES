---
title: Cómo configurar la forma ámbito | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scope shape [Orchestration Designer], about Scope shape
- Scope shape [Orchestration Designer], configuring
- Scope shape [Orchestration Designer], variables
- Scope shape [Orchestration Designer]
- configuring [Orchestration Designer], Scope shape
- Scope shape [Orchestration Designer], transactions
ms.assetid: 3c518db0-d68c-4f72-9d5c-48540811e289
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef17f5d1ab94875af118d17551da4334525535fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249452"
---
# <a name="how-to-configure-the-scope-shape"></a>Cómo configurar la forma Ámbito
El **ámbito** forma proporciona un marco de trabajo contextual para su contenido. El primer bloque de un **ámbito** forma es el bloque de contexto o cuerpo, en el que realicen las acciones básicas del ámbito; es análogo al bloque try en una instrucción try/catch. Después, el cuerpo de la **ámbito** forma también puede incluir uno o más bloques de controlador de excepciones y un bloque de compensación.  
  
> [!NOTE]
>  En un entorno de varios equipos donde [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y SQL Server se encuentran en equipos diferentes, si la hora Universal coordinada (UTC) es diferente en los dos equipos, a continuación, el **tiempo de espera** propiedad configurar para el  **Ámbito** forma puede desencadenarse antes de lo esperado debido a la hora UTC en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y máquinas de SQL Server no está sincronizado. Tenga en cuenta que no es un problema de zonas horarias, ya que éstas no afectan a la hora universal coordinada.  
  
### <a name="to-configure-a-scope-shape-as-a-transaction-boundary"></a>Para configurar una forma Ámbito como un límite de la transacción:  
  
1.  En la ventana Propiedades, establezca la **tipo de transacción** propiedad **atómica** o **larga ejecución**.  
  
    > [!NOTE]
    >  La orquestación debe ser una transacción de larga ejecución para poder establecer el tipo de transacción como atómica o de larga ejecución.  
  
2.  Si el **tipo de transacción** está establecido en **atómica**, a continuación, en la ventana Propiedades, especifique las siguientes propiedades:  
  
    |Propiedad|Description|  
    |--------------|-----------------|  
    |Lote|Valor booleano que determina si esta transacción se puede procesar por lotes con otras transacciones en varias instancias de la orquestación. Esta propiedad nunca se usa en BizTalk Server porque BizTalk Server no admite el procesamiento por lotes de las transacciones atómicas en varias instancias de orquestaciones. Esta propiedad quedará obsoleta en la versión futura.|  
    |Nivel de aislamiento|Determina el nivel de acceso a los datos para las transacciones simultáneas:<br /><br /> -Lectura confirmada: para evitar que la transacción seleccionada tengan acceso a las modificaciones de datos en las transacciones simultáneas hasta que se confirman. Esta opción es la configuración predeterminada de Microsoft SQL Server.<br />-Repeatable Read: requerir bloqueos de lectura hasta que se complete la transacción seleccionada.<br />-Serializable: para evitar que las transacciones simultáneas realicen modificaciones de datos hasta que se complete la transacción seleccionada. Esta opción es el nivel de aislamiento más restrictivo.|  
    |Reintentar|Valor booleano que determina si se reintenta esta transacción en caso de error. El valor predeterminado es **True**. **Nota:** se volverá a intentar una transacción atómica si lanza Microsoft.XLANG.BaseTypes.RetryTransactionException o si el motor de orquestaciones no puede almacenar su estado o confirmar la transacción.|  
    |Timeout|Determina el tiempo en segundos transcurrido hasta que se produzca un error en la transacción por inactividad. Si no desea usar un tiempo de espera, establezca el valor de esta propiedad en 0. **Nota:** esto un tiempo de espera de DTC y no se aplica por el motor de orquestaciones. Solo para las transacciones atómicas, el motor no interrumpirá la transacción. Continuará normalmente hasta la confirmación, en ese punto se producirá un error en la confirmación solo si se participa en una transacción de DTC a través de uno de los objetos de su interior.|  
  
3.  Si el **tipo de transacción** está establecido en **larga ejecución**, a continuación, en la ventana Propiedades, especifique la siguiente propiedad:  
  
    |Propiedad|Description|  
    |--------------|-----------------|  
    |Timeout|Determina el tiempo en segundos transcurrido hasta que se excede el tiempo de espera de la transacción y se considera una transacción errónea. Si no desea usar un tiempo de espera, establezca el valor de esta propiedad en 0.|  
  
### <a name="to-configure-a-scope-shape-to-contain-local-variables"></a>Para configurar una forma Ámbito y que contenga variables locales  
  
1.  Haga doble clic en el ámbito en la ventana Vista orquestación.  
  
2.  Haga clic en la carpeta de Variables en el ámbito y, a continuación, haga clic en **nueva Variable**.  
  
3.  Continúe en el paso 2 en la sección "para agregar una variable" en [cómo agregar Variables de orquestación](../core/how-to-add-orchestration-variables.md).