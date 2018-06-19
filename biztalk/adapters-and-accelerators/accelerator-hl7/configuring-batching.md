---
title: Configurar el procesamiento por lotes | Documentos de Microsoft
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
ms.openlocfilehash: b9ab9ead01273e54826db670e7e6d6a2e9af6200
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204572"
---
# <a name="configuring-batching"></a>Configurar el procesamiento por lotes
Utiliza [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] para crear el lote, el Explorador de configuración por lotes en / lote procesamiento por lotes y para seleccionar los esquemas disponibles para el procesamiento por lotes saliente.  
  
> [!NOTE]
>  Debe configurar a socios comerciales mediante el Explorador de BizTalk para poder configurar el procesamiento por lotes de mensajes.  
  
 La siguiente ilustración muestra la [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuración explorador **definición por lotes** ficha.  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-batchdef.gif "hl7_ops_batchdef")  
  
 Utilice los procedimientos siguientes para abrir [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el Explorador de configuración y configurar el procesamiento por lotes.  
  
### <a name="to-enable-message-batching-for-outbound-batching-create-batch"></a>Para habilitar el procesamiento por lotes de mensajes por lotes saliente (Crear lote)  
  
1.  En el **iniciar** menú Abrir **administración de BizTalk Server**.  
  
2.  En la consola de administración, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda **BizTalk Aplicación 1**.  
  
3.  Haga clic en **orquestaciones**, haga clic en **BatchOrchestration.Orchestration_1**y, a continuación, seleccione **propiedades**.  
  
4.  En el cuadro de diálogo Propiedades de orquestación, haga clic en **enlaces** en el árbol de consola.  
  
5.  En el **enlaces** panel, seleccione un host apropiado para **Host**. Haga clic en **Aceptar**.  
  
6.  Haga clic en **BatchOrchestration.Orchestration_1**y, a continuación, seleccione **dar de alta**.  
  
7.  Haga clic en **BatchOrchestration.Orchestration_1**y, a continuación, seleccione **iniciar**.  
  
### <a name="to-run-btahl7-configuration-explorer"></a>Para ejecutar el Explorador de configuración de BTAHL7  
  
-   En el **iniciar** menú Abrir **Acelerador de Microsoft BizTalk para HL7** y, a continuación, haga clic en **BTAHL7 configuración explorador**.  
  
### <a name="to-configure-batching"></a>Para configurar el procesamiento por lotes  
  
-   En [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el Explorador de configuración, en el **Explorador de configuración de BTAHL7** cuadro de diálogo la **partes** ficha, seleccione la entidad que desea configurar, y, a continuación, en la **por lotes Definición de** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Requerido fragmentación**|Seleccione una de las siguientes opciones:<br /><br /> -   **Sí**. Para habilitar la fragmentación.<br />-   **Ya no**. Para deshabilitar la fragmentación. **Nota:** para una entidad nueva, **requerida fragmentación** tiene como valor predeterminado **No**.|  
    |**Seleccionar los mensajes**|Seleccione los tipos de mensaje que desea enviar como un lote a partir de la **mensajes disponibles** ventana y, a continuación, haga clic en el movimiento a la flecha derecha (**>>**).|  
    |**Seleccione las confirmaciones de mensaje**|Seleccione los tipos de mensaje para el que desea que las confirmaciones para enviar como un lote a partir de la **confirmaciones de mensajes disponible** ventana y, a continuación, haga clic en el movimiento a la derecha (**>>**).|  
  
    > [!NOTE]
    >  Puede que no vea los esquemas que agregue a su en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] proyecto mientras se encuentre en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuración Explorer se está ejecutando. Para ver estos archivos, debe reiniciar en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el Explorador de configuración.  
  
## <a name="see-also"></a>Vea también  
 [Programar el procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/scheduling-batching.md)