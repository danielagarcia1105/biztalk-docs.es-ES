---
title: Cómo agregar una transacción | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adding, transactions
- transactions, adding
ms.assetid: 25385c20-3025-4cf1-bc1f-ef266e081bad
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3a4fcb1116e5b4a0cd3a8b62dc1283abc3215c6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009973"
---
# <a name="how-to-add-a-transaction"></a>Cómo agregar una transacción
Para agregar una transacción, siga estos pasos.  
  
### <a name="to-add-a-transaction"></a>Para agregar una transacción  
  
1. Haga clic en el **transacciones** ficha.  
  
2. Haga clic en **Agregar transacción**.  
  
3. Haga clic en **agregar un nuevo valor**. Escriba la información siguiente y, a continuación, haga clic en **agregar**.  
  
   1. **Nombre del nodo:** Compruebe que se trata **MSEXTERNAL**.  
  
   2. **Tipo de transacción:** Compruebe que se trata **asíncrona saliente**.  
  
   3. **Mensaje de solicitud:** escriba `LOCATION_SYNC`.  
  
   4. **Versión de mensaje de solicitud:** escriba `VERSION_1`.  
  
      ![](../core/media/psadapter-38-task-gatewayaddtransaction.gif "PSAdapter_38_Task_GatewayAddTransaction")  
  
4. En el **detalles de transacción** , compruebe la configuración siguiente:  
  
   1. **Estado:** activo.  
  
   2. **Enrutamiento:** implícita.  
  
      ![](../core/media/psadapter-39-task-gatewaytransdetail.gif "PSAdapter_39_Task_GatewayTransDetail")  
  
5. Haga clic en **Guardar**.  
  
6. Haga clic en el **volver a la lista de transacciones** vínculo.  
  
    La transacción aparecerá en la lista de transacciones.  
  
## <a name="see-also"></a>Vea también  
 [Creación de puertos y hosts HTTP de PeopleSoft](../core/creating-a-peoplesoft-http-host-and-port.md)