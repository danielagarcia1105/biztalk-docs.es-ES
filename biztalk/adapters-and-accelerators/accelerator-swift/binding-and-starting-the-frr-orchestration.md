---
title: Enlazar e iniciar la orquestación de FRR | Microsoft Docs
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
ms.openlocfilehash: b01386cedbd25148e5ea0ce2ac44fb56e9fe3d03
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987445"
---
# <a name="binding-and-starting-the-frr-orchestration"></a>Enlazar e iniciar la orquestación de FRR
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] incluye la orquestación de FRR como un ensamblado implementado (Microsoft. Solutions.FinancialServices.SWIFT.FrrOrchestration). Debe iniciar esta orquestación.  
  
 **Resumen**  
  
 Para iniciar la orquestación de FRR, realice lo siguiente:  
  
-   Enlazar la orquestación FrrOrchestration.FrrMain estableciendo al host BizTalkServerApplication.  
  
-   Iniciar la orquestación FrrOrchestration.FrrMain.  
  
### <a name="to-bind-and-start-the-frr-orchestration"></a>Para enlazar e iniciar la orquestación de FRR  
  
1.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, **grupo de BizTalk**, **aplicaciones**y, a continuación, **BizTalk Aplicación 1**. Haga clic en **orquestaciones**.  
  
2.  En el panel orquestaciones, haga clic en el **FrrOrchestration.FrrMain** orquestación y, a continuación, haga clic en **propiedades**.  
  
3.  En el cuadro de diálogo Propiedades de orquestación, haga clic en **enlaces** en el panel izquierdo. Para **Host**, seleccione **BizTalkServerApplication**. Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.  
  
4.  En el panel orquestaciones, haga clic en el **FrrMain** orquestación y, a continuación, haga clic en **iniciar**.