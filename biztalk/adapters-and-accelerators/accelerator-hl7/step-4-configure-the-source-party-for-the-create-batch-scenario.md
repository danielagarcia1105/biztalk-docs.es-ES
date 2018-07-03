---
title: 'Paso 4: Configurar la entidad de origen para el escenario de creación de lote | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b06b6545-4c2e-4a56-9feb-bd3f9574d4d1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbb4e172c88c179ea53f1e48d1e08dcb63458607
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999829"
---
# <a name="step-4-configure-the-source-party-for-the-create-batch-scenario"></a>Paso 4: Configurar la entidad de origen para el escenario de creación de lote
En este paso, configure la entidad de origen para el escenario de lote de crear. También selecciona las confirmaciones que el Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) procesará por lotes los, tal como se define para esta entidad. Establecer la programación para el lote de confirmación que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] creará el lote después de que el número de mensajes llega a 2.  
  
> [!NOTE]
>  En este escenario, se usa la misma entidad de origen que creó en [paso 7: crear y configurar una entidad de origen](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md) parte 1 de este tutorial (el fragmentado de entrada por lotes escenario).  
  
### <a name="to-configure-the-source-party-for-the-create-batch-scenario"></a>Para configurar la entidad de origen para el escenario de creación de lote  
  
1. En el Explorador de configuración de BTAHL7, en el **partes** , haga clic en el árbol de consola **Tutorial_BatchSource**.  
  
2. Haga clic en el **confirmación** ficha en el panel de detalles. Compruebe que la **tipo de confirmación** es **OriginalMode**.  
  
3. Haga clic en el **definición de lote** ficha. En **confirmaciones de mensajes disponibles**, haga clic en **BTAHL7Schemas.ADT_A03_231_GLO_DEF**, haga clic en la migración a la flecha derecha (**>>**) para agregar este esquema a  **Selecciona las confirmaciones de mensajes**y, a continuación, haga clic en **guardar**.  
  
4. Haga clic en el **programación por lotes** ficha. En el **Repita el proceso por lotes después** sección, seleccione **mensajes**y, a continuación, escriba **2** en el **mensajes** cuadro.  
  
5. Haga clic en **iniciar programación**.  
  
   Continúe con [paso 5: crear el puerto de envío para el lote de mensajes](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-send-port-for-the-message-batch.md).