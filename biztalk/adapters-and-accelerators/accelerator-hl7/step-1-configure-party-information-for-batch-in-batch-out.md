---
title: "Paso 1: Configurar la información de entidad para el lote en procesos por lotes el | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a93d774b-1282-40d9-836f-44abeb65f78e
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 982b17fe3826a0e5c5ee2a42030ba020b755ab70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-configure-party-information-for-batch-inbatch-out"></a>Paso 1: Configurar la información de entidad para el lote en / lote Out
En este paso, desactivar la fragmentación del procesamiento por lotes para la entidad, lo que permite el lote en / escenario de lote. A continuación, reinicie [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para habilitar el cambio de configuración surta efecto.  
  
### <a name="to-turn-off-fragmentation-of-batching-for-the-party"></a>Para desactivar la fragmentación del procesamiento por lotes para la entidad  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft BizTalk \<versión > Accelerator for HL7**y, a continuación, haga clic en **BTAHL7 Explorador de configuración**.  
  
2.  En el Explorador de configuración de BTAHL7, en la **partes** en el panel izquierdo, haga clic en **Tutorial_BatchSource**.  
  
3.  Haga clic en el **definición por lotes** ficha.  
  
4.  Seleccione **No** para **requerida fragmentación**y, a continuación, haga clic en **guardar**.  
  
5.  Asegúrese de que en **soporte técnico de intercambio recuperable requiere** lista desplegable **False** está seleccionada.  
  
 Continúe con [paso 2: modificar o crear el envío y puertos de recepción](../../adapters-and-accelerators/accelerator-hl7/step-2-modify-or-create-the-send-and-receive-ports.md).