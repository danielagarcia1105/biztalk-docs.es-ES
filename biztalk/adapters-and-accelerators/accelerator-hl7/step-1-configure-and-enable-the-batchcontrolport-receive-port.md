---
title: 'Paso 1: Configurar y habilitar el BatchControlPort el puerto de recepción | Documentos de Microsoft'
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
ms.openlocfilehash: d50289924062268db078844f2b3d2eaaccda23a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206148"
---
# <a name="step-1-configure-and-enable-the-batchcontrolport-receive-port"></a>Paso 1: Configurar y habilitar el BatchControlPort el puerto de recepción
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) el programa de instalación crea un puerto de recepción, el puerto el control de proceso por lotes, para controlar los mensajes que la orquestación del lote que se usa para iniciar, lotes de detención y el tiempo. Estos mensajes incluyen la activación de lotes, terminación de lotes y mensajes de temporizador de lote. En este paso, puede configura la canalización de recepción para el puerto de control de lote y habilitar el puerto.  
  
### <a name="to-configure-and-enable-batchcontrolport"></a>Para configurar y habilitar BatchControlPort  
  
1.  Iniciar **administración de BizTalk Server**.  
  
2.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, **grupo de BizTalk**, **aplicaciones**, y **aplicación de BizTalk 1**. Haga clic en **ubicaciones de recepción**.  
  
3.  Haga clic en **BatchControlLocation**y, a continuación, haga clic en **deshabilitar**.  
  
4.  Haga clic en **BatchControlLocation**y, a continuación, haga clic en **propiedades**.  
  
5.  En el cuadro de diálogo Propiedades de la ubicación de recepción, para **canalización de recepción**, seleccione **BTAHL72XPipelines.BTAHL72XReceivePipeline**. Haga clic en **Aceptar**.  
  
6.  En la consola de administración de BizTalk, haga clic en **BatchControlLocation**y, a continuación, haga clic en **habilitar**.  
  
 Continúe con [paso 2: habilitar la orquestación del lote](../../adapters-and-accelerators/accelerator-hl7/step-2-enable-the-batch-orchestration.md).