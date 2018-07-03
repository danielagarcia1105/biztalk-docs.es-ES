---
title: 'Paso 1: Configurar y puerto de recepción de habilitar la BatchControlPort | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be248a05-e740-497a-b112-8ba3a57b020b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1fb11e0638a66fa7d22332d1cbca103a14490528
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988253"
---
# <a name="step-1-configure-and-enable-the-batchcontrolport-receive-port"></a>Paso 1: Configurar y habilitar el BatchControlPort puerto de recepción
Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) programa de instalación crea un puerto de recepción, el control del lote de puerto, para controlar los mensajes que la orquestación del lote que se usa para iniciar, tiempo y detenga los lotes. Estos mensajes incluyen la activación de lotes, terminación de lotes y mensajes de temporizador de batch. En este paso, configurará la canalización de recepción para el puerto de control de proceso por lotes y habilitar el puerto.  
  
### <a name="to-configure-and-enable-batchcontrolport"></a>Para configurar y habilitar BatchControlPort  
  
1. Iniciar **administración de BizTalk Server**.  
  
2. En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, **grupo de BizTalk**, **aplicaciones**, y **aplicación de BizTalk 1**. Haga clic en **ubicaciones de recepción**.  
  
3. Haga clic en **BatchControlLocation**y, a continuación, haga clic en **deshabilitar**.  
  
4. Haga clic en **BatchControlLocation**y, a continuación, haga clic en **propiedades**.  
  
5. En el cuadro de diálogo Propiedades de ubicación de recepción para **canalización de recepción**, seleccione **BTAHL72XPipelines.BTAHL72XReceivePipeline**. Haga clic en **Aceptar**.  
  
6. En la consola de administración de BizTalk, haga clic en **BatchControlLocation**y, a continuación, haga clic en **habilitar**.  
  
   Continúe con [paso 2: habilitar la orquestación del lote](../../adapters-and-accelerators/accelerator-hl7/step-2-enable-the-batch-orchestration.md).