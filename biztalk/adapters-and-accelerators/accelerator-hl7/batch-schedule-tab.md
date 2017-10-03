---
title: "Procesar por lotes pestaña programación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: btahl7.configurationexplorer.tab.batchschedule
helpviewer_keywords:
- batching, scheduling
- Batch Schedule tab [Configuration Explorer]
- scheduling batching
ms.assetid: 3792388b-6af2-41c2-8f41-bdfda7e17b2b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d870abad399dcca76c32a3a8d0e8c6637fc93284
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="batch-schedule-tab"></a>Ficha de programación por lotes
Usa el **programación por lotes** tab para activar, solicitar o finalizar un lote saliente. Activar un lote saliente consta de dos pasos: configurar basado en tiempo o mensaje de recuento de criterios y, a continuación, iniciar la orquestación de procesamiento por lotes saliente.  
  
 Puede configurar [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] para crear un lote saliente mediante basado en tiempo o mensajes criterios de recuento o una combinación de ambos. Establecer criterios de activación por lotes es opcional. Si no se especifica, puede activar un lote manualmente. Si desea activar un lote mediante basado en tiempo o criterios de recuento de mensajes, debe especificar estos criterios antes de activar el lote.  
  
 En el **Explorador de configuración de BTAHL7** cuadro de diálogo, en la **programación por lotes** ficha, realice lo siguiente:  
  
|Use|Para|  
|--------------|----------------|  
|**Horas antes de que en primer lugar por lotes**|Escriba el número de horas antes de iniciar el primer lote.<br /><br /> Esta opción no está disponible cuando se selecciona el número de mensajes como el control del lote.|  
|**Repita el proceso por lotes después de**|Seleccione una de las siguientes opciones:<br /><br /> -                   **Horas**. Escriba el número de horas que esperar antes de repetir el proceso por lotes.<br /><br /> -                   **Mensajes**. Escriba el número de mensajes que se van a procesar antes de iniciar el siguiente lote.|  
|**Control de proceso por lotes**|Utilice las siguientes opciones:<br /><br /> -                   **Iniciar la programación**: seleccione esta opción para iniciar la programación por lotes.<br /><br /> -                   **Enviar ahora**: seleccione esta opción para iniciar inmediatamente el proceso por lotes. Esto invalida la **horas antes del primer lote** y **repita lote después** configuración.<br /><br /> -                   **Detener la programación**: seleccione esta opción para detener la programación por lotes actual. Esto completa el lote actual y, a continuación, detiene la orquestación del lote.|