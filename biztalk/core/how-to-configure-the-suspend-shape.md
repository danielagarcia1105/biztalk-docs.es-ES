---
title: "Cómo configurar la forma suspender | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [Orchestration Designer], Suspend shapes
- Suspend shape [Orchestration Designer], literal strings
- Suspend shape [Orchestration Designer], configuring
- Suspend shape [Orchestration Designer]
- atomic transactions, Suspend shape [Orchestration Designer]
- Suspend shape [Orchestration Designer], atomic transactions
- Suspend shape [Orchestration Designer], about Suspend shape
ms.assetid: 62fbb6d4-78d2-4671-84bb-909cbf6b0ec3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c846001b5a2b39a4e23e0d06ed56fb91c8863832
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-suspend-shape"></a>Cómo configurar la forma Suspender
![](../core/media/ebiz-orch-suspend.gif "ebiz_orch_suspend")  
Forma Suspender  
  
 Cuando se suspende una instancia de orquestación, se registra un error. Puede especificar una cadena de mensaje que acompañe al error para ayudar al administrador a diagnosticar la situación.  
  
 Se guarda toda la información de estado de la instancia de orquestación y se vuelve a establecer cuando el administrador reanude la instancia de orquestación.  
  
> [!NOTE]
>  Si un **Suspend** forma existe en una orquestación que se ha llamado de forma sincrónica (igual que con la **llamar a** forma) por otra orquestación, la instancia anidada y todas las instancias de orquestación envolvente le se suspende.  
  
> [!NOTE]
>  No se puede colocar una **Suspend** forma dentro de una transacción atómica.  
  
### <a name="to-configure-a-suspend-shape"></a>Para configurar una forma Suspender  
  
-   Puede usar el **mensaje de Error** propiedad para especificar el texto que desea que estén registrados cuando un **Suspend** forma se encuentra. Este texto puede ser una cadena literal o una expresión que se evalúa como un **System.String**.  
  
    > [!CAUTION]
    >  Si escribe una cadena literal, ésta debe ir entre comillas.