---
title: Cómo configurar la forma Finalizar | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Terminate shape [Orchestration Designer], about Terminate shape
- Terminate shape [Orchestration Designer], literal strings
- configuring [Orchestration Designer], Terminate shapes
- Terminate shape [Orchestration Designer], configuring
- Terminate shape [Orchestration Designer]
ms.assetid: 2c4f2c94-2bab-4af3-8954-7275696ca147
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a5eb4867970c6acafc8903eb474b67541d22764
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247932"
---
# <a name="how-to-configure-the-terminate-shape"></a>Cómo configurar la forma Finalizar
![](../core/media/ebiz-orch-terminate.gif "ebiz_orch_terminate")  
Forma Finalizar  
  
 La forma Finalizar se usa para terminar una instancia de orquestación. Puede especificar una cadena de mensaje para acompañar la forma cuando se visualice en los resultados de la página Concentrador de grupo.  
  
> [!CAUTION]
>  Si coloca un **Terminate** forma dentro de un **acciones paralelas** forma así como la rama con la **Terminate** en que se ejecuta, la instancia se completa inmediatamente, sin tener en cuenta Si el resto de bifurcaciones ha terminado de ejecutarse. Según su diseño, los resultados podrían ser imprevisibles en este caso.  
  
> [!CAUTION]
>  Si un **Terminate** forma se encuentra en una orquestación que se ha llamado de forma sincrónica (igual que con la **llamar a** forma) por otra orquestación, la instancia anidada y todas las orquestación envolvente puede finalizar instancias.  
  
### <a name="to-configure-a-terminate-shape"></a>Para configurar una forma Finalizar:  
  
-   Puede usar el **mensaje de Error** propiedad para especificar el texto que desea asociar a la forma cuando se ve en el resultado de la consulta en la página concentrador de grupo. Este texto puede ser una cadena literal o una expresión que se evalúa como un **System.String**.  
  
    > [!CAUTION]
    >  Si escribe una cadena literal, ésta debe ir entre comillas.