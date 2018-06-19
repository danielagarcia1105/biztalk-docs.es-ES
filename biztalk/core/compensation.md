---
title: Compensación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- compensations, errors
- compensations
- errors, compensations
- compensations, about compensations
- compensations, atomic transactions
- atomic transactions, compensations
- transactions, compensations
ms.assetid: 0a80dd16-fd35-4f45-95b7-52bb9df80cbb
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c572638ea6212c3fb79e6b239aa8ffbe713c3c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231604"
---
# <a name="compensation"></a>Compensación
Si se produce un error y tiene que deshacer o invertir los efectos de una transacción confirmada correctamente, puede hacerlo agregando código de compensación a la orquestación.  
  
 solo puede invocarse la compensación después de que la transacción haya completado correctamente sus acciones. En ese punto, se conoce el estado de la orquestación y la información de estado está disponible para el código de la compensación, con lo que ya es posible escribir código que actúe debidamente en función del estado de la orquestación cuando se confirme la transacción.  
  
 También se pueden realizar compensaciones para las transacciones atómicas. solo se puede llamar a estas compensaciones después de que se confirme la transacción atómica. Es preciso escribir código en la compensación que deshaga o invierta la ruta de ejecución normal.  
  
 El bloque de compensación es flexible; puede contener cualquier otra forma, incluso otro ámbito de transacción.  
  
> [!NOTE]
>  Únicamente se puede realizar una compensación para cada ámbito determinado.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo configurar la forma compensar](../core/how-to-configure-the-compensate-shape.md)  
  
-   [Cómo agregar la compensación personalizada a una orquestación](../core/how-to-add-custom-compensation-to-an-orchestration.md)  
  
-   [Cómo agregar un bloque de compensación](../core/how-to-add-a-compensation-block.md)