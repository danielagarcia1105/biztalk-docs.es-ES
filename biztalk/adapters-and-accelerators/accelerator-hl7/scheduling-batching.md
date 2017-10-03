---
title: Programar el procesamiento por lotes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching, scheduling
- scheduling batching
ms.assetid: 037626f1-1b3b-43e6-80eb-5fb900cdbd46
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08337171897a4a78e605054e9126e8c8238d5fa5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="scheduling-batching"></a>Programar el procesamiento por lotes
Usa [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] Explorador de configuración para activar, solicitar o finalizar un lote saliente. Activar un lote saliente consta de dos pasos: configurar basado en tiempo o mensaje de recuento de criterios y, a continuación, iniciar la orquestación de procesamiento por lotes saliente.  
  
 La siguiente ilustración muestra la [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuración explorador **programación por lotes** ficha.  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-batchsch.gif "hl7_ops_batchsch")  
  
 Utilice los procedimientos siguientes para abrir [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración y la programación de procesamiento por lotes.  
  
### <a name="to-open-btahl7-configuration-explorer"></a>Para abrir el Explorador de configuración de BTAHL7  
  
-   Haga clic en **iniciar**, seleccione **programas**, seleccione **Microsoft BizTalk \<versión > Accelerator for HL7**y, a continuación, haga clic en **BTAHL7 Explorador de configuración**.  
  
### <a name="to-schedule-message-batching"></a>Para programar el procesamiento por lotes de mensajes  
  
1.  Abra el Explorador de configuración de BTAHL7.  
  
2.  En el Explorador de configuración de BTAHL7, en la **Explorador de configuración de BTAHL7** cuadro de diálogo la **partes** ficha, seleccione la entidad que desea configurar, y, a continuación, en la **programación por lotes** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Horas antes de que en primer lugar por lotes**|Escriba el número de horas antes de que el primer lote consiste en iniciar.|  
    |**Repita el proceso por lotes después de**|Seleccione una de las opciones siguientes:<br /><br /> -   **Horas**. Escriba el número de horas que se repita el proceso por lotes.<br />-   **Mensajes**. Escriba el número de mensajes que van a procesar antes de que el proceso por lotes siguiente comienza.|  
    |**Control de proceso por lotes**|Seleccione una de las opciones siguientes:<br /><br /> -   **Iniciar la programación**: seleccione esta opción para iniciar el programa por lotes.<br />-   **Enviar ahora**: seleccione esta opción para iniciar el lote se procesará inmediatamente.<br />-   **Detener la programación**: seleccione esta opción para detener la programación por lotes actual.|  
  
## <a name="see-also"></a>Vea también  
 [Configurar confirmaciones de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/configuring-batching-acknowledgments.md)