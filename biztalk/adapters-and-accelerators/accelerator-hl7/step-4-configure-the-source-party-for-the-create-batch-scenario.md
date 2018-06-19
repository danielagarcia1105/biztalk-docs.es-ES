---
title: 'Paso 4: Configurar la entidad de origen para el escenario de lote crear | Documentos de Microsoft'
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
ms.openlocfilehash: 12f7ca9eebb28bb97ae925aec4fc34cefd5a2dcd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206404"
---
# <a name="step-4-configure-the-source-party-for-the-create-batch-scenario"></a>Paso 4: Configurar la entidad de origen para el escenario de lote crear
En este paso, configurará la entidad de origen para el escenario de lote de crear. También selecciona las confirmaciones que Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) se procesar por lotes, como se define para esta entidad. Establece la programación para el lote de confirmación que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] creará el lote después de que el número de mensajes llega a 2.  
  
> [!NOTE]
>  En este escenario, utilice la misma entidad de origen que creó en [paso 7: crear y configurar una entidad de origen](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md) de la parte 1 de este tutorial (el fragmentado de entrada por lotes escenario).  
  
### <a name="to-configure-the-source-party-for-the-create-batch-scenario"></a>Para configurar la entidad de origen para el escenario de crear lote  
  
1.  En el Explorador de configuración de BTAHL7, en la **partes** en el árbol de consola, haga clic en **Tutorial_BatchSource**.  
  
2.  Haga clic en el **confirmación** en el panel de detalles. Compruebe que la **tipo de confirmación** es **OriginalMode**.  
  
3.  Haga clic en el **definición por lotes** ficha. En **confirmaciones de mensajes disponible**, haga clic en **BTAHL7Schemas.ADT_A03_231_GLO_DEF**, haga clic en el movimiento a la flecha derecha (**>>**) para agregar este esquema a  **Selecciona confirmaciones de mensaje**y, a continuación, haga clic en **guardar**.  
  
4.  Haga clic en el **programación por lotes** ficha. En el **repita lote después de** sección, seleccione **mensajes**y, a continuación, escriba **2** en el **mensajes** cuadro.  
  
5.  Haga clic en **comenzará programación**.  
  
 Continúe con [paso 5: crear el puerto de envío para el lote de mensajes](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-send-port-for-the-message-batch.md).