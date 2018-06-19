---
title: Ficha Definición de lote | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- btahl7.configurationexplorer.tab.batchdefinition
helpviewer_keywords:
- Batch Definition tab [Configuration Explorer]
- batching, configuring
- configuring, batching
ms.assetid: fe8685ef-5de5-4337-8691-8e4094056ace
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2270625a6e4512f2a99bea7a06812b601b48d44c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204516"
---
# <a name="batch-definition-tab"></a>Pestaña de la definición de proceso por lotes
Usa el **definición por lotes** ficha para habilitar la entrada por lotes de procesamiento por lotes, en / lote espera de procesamiento por lotes y seleccione los esquemas disponibles para el procesamiento por lotes saliente.  
  
 En el **Explorador de configuración de BTAHL7** cuadro de diálogo la **definición por lotes** ficha, realice lo siguiente:  
  
|Use|Para|  
|--------------|----------------|  
|**Requerido fragmentación**|Seleccione una de las siguientes opciones:<br /><br /> -   **Sí**. Para habilitar la fragmentación.<br />-   **Ya no**. Para deshabilitar la fragmentación. **Nota:** para una entidad nueva, **requerida fragmentación** tiene como valor predeterminado **No**.|  
|**Compatibilidad de intercambio recuperable requerida**|Seleccione una de las siguientes opciones:<br /><br /> -   **True**. Para habilitar la compatibilidad de intercambio recuperable.<br />-   **FALSE**. Para deshabilitar la compatibilidad de intercambio recuperable. **Nota:** para una entidad nueva, **requerida fragmentación** tiene como valor predeterminado **FALSE** y solo está habilitada si el valor de **requerida fragmentación** es **No**.|  
|**Seleccionar los mensajes**|Seleccione los tipos de mensaje que desea enviar como un lote de la ventana de mensajes disponibles y, a continuación, haga clic en el movimiento a la flecha derecha (**>>**).<br /><br /> Para procesar por lotes los mensajes entrantes de confirmación, debe agregar el tipo de mensaje de confirmación. La forma de hacerlo es mediante la implementación del esquema de mensaje de confirmación.|  
|**Seleccione las confirmaciones de mensaje**|Seleccione los tipos de mensaje que desea [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] para enviar las confirmaciones como un lote desde la ventana de mensajes de confirmación de mensaje disponibles y, a continuación, haga clic en el movimiento a la flecha derecha (**>>**).|