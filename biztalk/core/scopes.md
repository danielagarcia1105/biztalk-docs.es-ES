---
title: Ámbitos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- scopes, exception handling
- Scope shape [Orchestration Designer], nesting
- scopes, variables
- scopes, Scope shape [Orchestration Designer]
- Scope shape [Orchestration Designer], exception handling
- scopes, transactions
- scopes, synchronization
- scopes, nesting
- Scope shape [Orchestration Designer], transactions
ms.assetid: 51d81ce4-0034-4415-b6ab-4c952737c1bd
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bc4d1b5d926540477293591ade8123126be1b84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269780"
---
# <a name="scopes"></a>Ámbitos
Un ámbito es un marco de trabajo para agrupar acciones. Se utiliza principalmente para la ejecución de transacciones y el control de excepciones.  
  
 Un ámbito contiene uno o más bloques. Tiene un cuerpo y, de forma opcional, puede tener anexado cualquier número de bloques de control de excepciones. También puede incluir un bloque de compensación opcional, según sea la naturaleza del ámbito. Algunos ámbitos estarán destinados únicamente al control de excepciones y no necesitarán compensación. Sin embargo, otros serán explícitamente transaccionales y siempre contarán con un controlador de compensación predeterminado junto con uno opcional que cree para ellos. Un ámbito transaccional también incluirá un controlador de excepción predeterminado y un número indefinido de controladores de excepción adicionales que cree para él.  
  
## <a name="synchronized-scopes"></a>Ámbitos sincronizados  
 Puede especificar que los ámbitos estén sincronizados o no. Al sincronizar un ámbito, se asegura de que una o varias acciones paralelas de la orquestación no escriban los datos compartidos a los que se tenga acceso dentro del ámbito, ni tampoco mientras otra acción los lee.  
  
 Los ámbitos de transacciones atómicas siempre están sincronizados. Todas las acciones dentro de un ámbito sincronizado se consideran sincronizadas, así como todas las acciones incluidas en cualquiera de sus controladores de excepción. Las acciones del controlador de compensación de un ámbito transaccional no están sincronizadas.  
  
> [!CAUTION]
>  Tenga en cuenta que, si no diseña los procesos con cuidado, todavía puede encontrarse con una condición de interbloqueo. Por ejemplo, dos ramas de una paralela en la orquestación A tienen acceso al mismo mensaje, una para enviarlo y otra para recibirlo, por lo que ambas deben tener un ámbito sincronizado. Una segunda orquestación recibe el mensaje y lo vuelve a enviar. Es posible que la rama de envío de la orquestación A reciba sus bloqueos antes que la rama de recepción, y terminará encontrándose con un interbloqueo.  
  
## <a name="nesting-of-scopes"></a>Anidación de ámbitos  
 Puede anidar **ámbito** formas dentro de otras **ámbito** formas. Las reglas para anidar ámbitos son las siguientes:  
  
-   Los ámbitos transaccionales o sincronizados no pueden anidarse en ámbitos sincronizados, incluidos los controladores de excepción de ámbitos sincronizados.  
  
-   Los ámbitos de transacciones atómicas no pueden tener otros ámbitos transaccionales anidados en ellos.  
  
-   Los ámbitos transaccionales no pueden anidarse en ámbitos no transaccionales ni en orquestaciones.  
  
-   Puede anidar ámbitos con una profundidad máxima de 21 niveles.  
  
-   **Orquestación de llamada** formas pueden incluirse dentro de los ámbitos, pero las orquestaciones llamadas se tratan igual que cualquier otra transacción anidada y se aplican las mismas reglas.  
  
-   **Iniciar orquestación** formas pueden incluirse dentro de los ámbitos. Las limitaciones de anidación no se aplican a las orquestaciones iniciadas.  
  
## <a name="scope-variables"></a>Variables de ámbito  
 Puede declarar variables como mensajes y conjuntos de correlaciones en el nivel de ámbito. Sin embargo, no puede utilizar el mismo nombre para una variable de ámbito y para una variable de orquestación; la ocultación de nombres no está permitida.  
  
## <a name="see-also"></a>Vea también  
 [Uso de transacciones y control de excepciones](../core/using-transactions-and-handling-exceptions.md)   
 [Transacciones atómicas](../core/atomic-transactions.md)