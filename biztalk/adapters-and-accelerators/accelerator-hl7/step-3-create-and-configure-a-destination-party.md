---
title: 'Paso 3: Crear y configurar una entidad de destino | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8746f115-9f69-4593-9943-9ccda45cd900
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66d955aeaabe4d7207a07827de04c1c21e4c2c7a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-3-create-and-configure-a-destination-party"></a>Paso 3: Crear y configurar una entidad de destino
En este paso, crear y configurar una entidad de destino para el escenario de lote de crear. También selecciona los mensajes que [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] lotes y el lote programa, tal como se define para esa entidad. Puede programar la hora de envío de lote como una hora después de copiar los archivos en la carpeta. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]los lotes de cualquier mensaje recibido posteriormente con una frecuencia de una hora.  
  
### <a name="to-create-and-configure-a-destination-party"></a>Para crear y configurar una entidad de destino  
  
1.  En la consola de administración de BizTalk Server, haga clic en **partes**, seleccione **New**y, a continuación, haga clic en **entidad**.  
  
2.  En el cuadro de diálogo Propiedades de la entidad, en la **nombre** , escriba **Tutorial_BatchDest**y, a continuación, haga clic en **Aceptar**.  
  
3.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft BizTalk \<versión\> Acelerador para HL7**y, a continuación, haga clic en **Explorador de configuración de BTAHL7**.  
  
4.  En el Explorador de configuración de BTAHL7, en la **partes** en el árbol de consola, haga clic en **Tutorial_BatchDest**.  
  
5.  Haga clic en el **confirmación** en el panel de detalles. Compruebe que la **tipo de confirmación** es **ninguno**.  
  
6.  Haga clic en el **definición por lotes** ficha. En el **mensajes disponibles** panel, seleccione **BTAHL7Schemas.ADT_A03_231_GLO_DEF**. Haga clic en el movimiento a la flecha derecha (**>>**) para agregar este esquema a **mensajes seleccionados**y, a continuación, haga clic en **guardar**.  
  
7.  Haga clic en el **programación por lotes** ficha. En el **repita lote después de** sección, compruebe que **horas** está seleccionada y, a continuación, escriba **1** en el **horas** cuadro. En el **horas antes del primer lote** , escriba **1**y, a continuación, haga clic en **programación iniciar**.  
  
 Continúe con [paso 4: configurar la entidad de origen para el escenario de lote crear](../../adapters-and-accelerators/accelerator-hl7/step-4-configure-the-source-party-for-the-create-batch-scenario.md).