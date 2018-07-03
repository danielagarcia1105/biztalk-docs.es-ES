---
title: 'Paso 1: Configurar la información de entidad para fuera de proceso por lotes en Batch | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a93d774b-1282-40d9-836f-44abeb65f78e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eafe692cf86ccf3c6fbe0713c1e621a99a601d5d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974925"
---
# <a name="step-1-configure-party-information-for-batch-inbatch-out"></a>Paso 1: Configurar la información de entidad para el lote o salida
En este paso, desactivar la fragmentación del procesamiento por lotes para la entidad, lo que permite el lote en / escenario de lote. A continuación, reinicie [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para habilitar el cambio de configuración surta efecto.  
  
### <a name="to-turn-off-fragmentation-of-batching-for-the-party"></a>Para desactivar la fragmentación del procesamiento por lotes para la entidad  
  
1. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft BizTalk \<versión\> Acelerador para HL7**y, a continuación, haga clic en **Explorador de configuración de BTAHL7**.  
  
2. En el Explorador de configuración de BTAHL7, en el **partes** , haga clic en el panel izquierdo **Tutorial_BatchSource**.  
  
3. Haga clic en el **definición de lote** ficha.  
  
4. Seleccione **No** para **requerida fragmentación**y, a continuación, haga clic en **guardar**.  
  
5. Asegúrese de que en **soporte técnico de intercambio recuperable requiere** lista desplegable **False** está seleccionada.  
  
   Continúe con [paso 2: modificar o crear el envío y recepción](../../adapters-and-accelerators/accelerator-hl7/step-2-modify-or-create-the-send-and-receive-ports.md).