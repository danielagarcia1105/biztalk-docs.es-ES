---
title: "Cómo agregar una transacción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adding, transactions
- transactions, adding
ms.assetid: 25385c20-3025-4cf1-bc1f-ef266e081bad
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24c67a9c76ae87f2355bb0ea4638d3bd156cda6e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-transaction"></a>Cómo agregar una transacción
Para agregar una transacción, siga estos pasos.  
  
### <a name="to-add-a-transaction"></a>Para agregar una transacción  
  
1.  Haga clic en el **transacciones** ficha.  
  
2.  Haga clic en **Agregar transacción**.  
  
3.  Haga clic en **agregar un nuevo valor**. Escriba la información siguiente y, a continuación, haga clic en **agregar**.  
  
    1.  **Nombre del nodo:** Compruebe que se trata de **MSEXTERNAL**.  
  
    2.  **Tipo de transacción:** Compruebe que se trata de **asíncrona saliente**.  
  
    3.  **Mensaje de solicitud:** escriba `LOCATION_SYNC`.  
  
    4.  **Versión de mensaje de solicitud:** escriba `VERSION_1`.  
  
     ![](../core/media/psadapter-38-task-gatewayaddtransaction.gif "PSAdapter_38_Task_GatewayAddTransaction")  
  
4.  En el **detalle de la transacción** ficha, compruebe la configuración siguiente:  
  
    1.  **Estado:** Active.  
  
    2.  **Enrutamiento:** implícita.  
  
     ![](../core/media/psadapter-39-task-gatewaytransdetail.gif "PSAdapter_39_Task_GatewayTransDetail")  
  
5.  Haga clic en **Guardar**.  
  
6.  Haga clic en el **volver a la lista de transacciones** vínculo.  
  
     La transacción aparecerá en la lista de transacciones.  
  
## <a name="see-also"></a>Vea también  
 [Crear un Host de HTTP de PeopleSoft y puerto](../core/creating-a-peoplesoft-http-host-and-port.md)