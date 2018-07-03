---
title: Configuración de procesamiento por lotes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, configuring
- configuring, batching
ms.assetid: 33c72d5e-31dd-44a8-8418-1faab3239e8e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77ea79c4b96ac54e6b2d1eed281b60a261ca5cc1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976333"
---
# <a name="configuring-batching"></a>Configuración de procesamiento por lotes
Usa [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] para crear el lote, el Explorador de configuración por lotes en / por lotes de procesamiento por lotes y para seleccionar los esquemas disponibles para el procesamiento por lotes saliente.  
  
> [!NOTE]
>  Debe configurar a socios comerciales mediante el Explorador de BizTalk antes de configurar el procesamiento por lotes de mensajes.  
  
 La siguiente ilustración muestra el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuración Explorer **definición de lote** ficha.  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-batchdef.gif "hl7_ops_batchdef")  
  
 Use los procedimientos siguientes para abrir [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración y configurar el procesamiento por lotes.  
  
### <a name="to-enable-message-batching-for-outbound-batching-create-batch"></a>Para habilitar el procesamiento por lotes de mensajes por lotes saliente (creación de lote)  
  
1.  En el **iniciar** menú Abrir **administración de BizTalk Server**.  
  
2.  En la consola de administración, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda **BizTalk Aplicación 1**.  
  
3.  Haga clic en **orquestaciones**, haga clic en **BatchOrchestration.Orchestration_1**y, a continuación, seleccione **propiedades**.  
  
4.  En el cuadro de diálogo Propiedades de orquestación, haga clic en **enlaces** en el árbol de consola.  
  
5.  En el **enlaces** panel, seleccione el host adecuado para **Host**. Haga clic en **Aceptar**.  
  
6.  Haga clic en **BatchOrchestration.Orchestration_1**y, a continuación, seleccione **Enlist**.  
  
7.  Haga clic en **BatchOrchestration.Orchestration_1**y, a continuación, seleccione **iniciar**.  
  
### <a name="to-run-btahl7-configuration-explorer"></a>Para ejecutar el Explorador de configuración de BTAHL7  
  
-   En el **iniciar** menú Abrir **Acelerador de Microsoft BizTalk para HL7** y, a continuación, haga clic en **Explorador de configuración de BTAHL7**.  
  
### <a name="to-configure-batching"></a>Para configurar el procesamiento por lotes  
  
- En [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración, en el **Explorador de configuración de BTAHL7** cuadro de diálogo el **partes** pestaña, seleccione la entidad que desea configurar, y, a continuación, en el **por lotes Definición** ficha, realice lo siguiente:  
  
  |Use|Para|  
  |--------------|----------------|  
  |**Fragmentación necesaria**|Seleccione una de las siguientes opciones:<br /><br /> -   **Sí**. Para habilitar la fragmentación.<br />-   **No**. Para deshabilitar la fragmentación. **Nota:** para una entidad nueva, **requerida fragmentación** el valor predeterminado es **No**.|  
  |**Seleccionar los mensajes**|Seleccione los tipos de mensaje que desea enviar como un lote desde el **mensajes disponibles** ventana y, a continuación, haga clic en la migración a la flecha derecha (**>>**).|  
  |**Seleccione las confirmaciones de mensajes**|Seleccione los tipos de mensaje para el que desea que las confirmaciones que se envían como un lote a partir del **confirmaciones de mensajes disponibles** ventana y, a continuación, haga clic en el traslado a la derecha (**>>**).|  
  
  > [!NOTE]
  >  Puede que no vea los esquemas que agregue a su en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] proyecto mientras se encuentre en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] se está ejecutando el Explorador de configuración. Con el fin de ver estos archivos, es posible que deba reiniciar en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración.  
  
## <a name="see-also"></a>Vea también  
 [Programación del procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/scheduling-batching.md)