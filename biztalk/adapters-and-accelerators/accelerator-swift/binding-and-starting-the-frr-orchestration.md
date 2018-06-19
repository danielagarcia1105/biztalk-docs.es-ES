---
title: Enlazar e iniciar la orquestación FRR | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FRR, binding orchestrations
- FRR, starting orchestrations
- bindings, orchestrations
- orchestrations, bindings
ms.assetid: b74a0116-e98b-4fec-b386-710ce421a1e2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81cf116fc03a8f2d898752a077e8347fd395a4a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209060"
---
# <a name="binding-and-starting-the-frr-orchestration"></a>Enlazar e iniciar la orquestación FRR
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]incluye la orquestación FRR como un ensamblado implementado ([!INCLUDE[btsCoName](../../includes/btsconame-md.md)]. Solutions.FinancialServices.SWIFT.FrrOrchestration). Debe iniciar esta orquestación.  
  
 **Resumen**  
  
 Para iniciar la orquestación FRR, realice lo siguiente:  
  
-   Enlazar la orquestación FrrOrchestration.FrrMain estableciendo el host BizTalkServerApplication.  
  
-   Iniciar la orquestación FrrOrchestration.FrrMain.  
  
### <a name="to-bind-and-start-the-frr-orchestration"></a>Para enlazar e iniciar la orquestación FRR  
  
1.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, **grupo de BizTalk**, **aplicaciones**y, a continuación, **BizTalk Aplicación 1**. Haga clic en **orquestaciones**.  
  
2.  En el panel orquestaciones, haga clic en el **FrrOrchestration.FrrMain** orquestación y, a continuación, haga clic en **propiedades**.  
  
3.  En el cuadro de diálogo Propiedades de orquestación, haga clic en **enlaces** en el panel izquierdo. Para **Host**, seleccione **BizTalkServerApplication**. Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.  
  
4.  En el panel orquestaciones, haga clic en el **FrrMain** orquestación y, a continuación, haga clic en **iniciar**.