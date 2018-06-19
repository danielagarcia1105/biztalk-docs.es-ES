---
title: Cómo configurar la forma escuchar | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Listen shape [Orchestration Designer], about Listen shape
- Listen shape [Orchestration Designer], configuring
- Listen shape [Orchestration Designer]
- Listen shape [Orchestration Designer], branching
- configuring [Orchestration Designer], Listen shapes
ms.assetid: 4765dc0a-a30e-4515-83bc-72b4f37268cf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5bd8f8bbcc08d41430b95a9d177aeb06a5288be4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247900"
---
# <a name="how-to-configure-the-listen-shape"></a>Cómo configurar la forma Escuchar
Las acciones de escucha permiten que las aplicaciones esperen uno de varios mensajes en uno o varios puertos o que detengan la espera después de un intervalo del tiempo de espera especificado y ramifiquen según los resultados.  
  
 ![](../core/media/ebiz-orch-listen.gif "ebiz_orch_listen")  
Forma Escuchar  
  
 Puede agregar tantas ramas como sea necesario. Puede colocar cualquier otra forma bajo la inicial **recepción** o **retraso** forma.  
  
 Es posible utilizar una activación de recepción en un **escuchar** forma. Si una rama de la **escuchar** forma contiene una activación de recepción, todas las ramas deben contener recepciones de activación, y no puede usarse tiempo de espera. La recepción de activación debe ser la primera acción en cada rama.  
  
 Puede usar el **escuchar** forma al flujo de orquestación de bifurcación en función de la aparición de uno o más eventos. La primera forma en cada rama debe ser un **retraso** o un **recepción** forma. La primera rama que cumpla su condición, la aparición de un tiempo de espera para un **retraso** forma o la recepción de un mensaje para un **recepción** forma, se ejecutará. Puede agregar más ramas si lo necesita.  
  
### <a name="to-configure-a-listen-shape"></a>Para configurar una forma Escuchar  
  
1.  Seleccione una rama.  
  
2.  En la ventana Propiedades, especifique la **tipo de rama** propiedad.  
  
     : "O":  
  
     Arrastre un **retraso** o **recepción** forma en la bifurcación.  
  
### <a name="to-add-a-branch-to-a-listen-shape"></a>Para agregar una rama a una forma Escuchar  
  
-   Haga clic en el **escuchar** forma y, a continuación, haga clic en **nueva rama escuchar**.  
  
    > [!NOTE]
    >  Para quitar una rama de un **escuchar** forma, haga clic en la rama que desee quitar y, a continuación, haga clic en **eliminar**.