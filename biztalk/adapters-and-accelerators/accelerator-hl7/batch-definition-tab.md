---
title: Pestaña de la definición de batch | Microsoft Docs
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
ms.openlocfilehash: d8eb06321fc5025efa17796a79cddcbe2d14ef9e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970821"
---
# <a name="batch-definition-tab"></a>Pestaña definición de lote
Usa el **definición de lote** tab para habilitar la entrada por lotes de procesamiento por lotes, en o salida de procesamiento por lotes y seleccione los esquemas disponibles para el procesamiento por lotes saliente.  

 En el **Explorador de configuración de BTAHL7** cuadro de diálogo el **definición de lote** ficha, realice lo siguiente:  


|                   Use                   |                                                                                                                                                            Para                                                                                                                                                            |
|----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|          **Fragmentación necesaria**          |                                                           Seleccione una de las siguientes opciones:<br /><br /> -   **Sí**. Para habilitar la fragmentación.<br />-   **No**. Para deshabilitar la fragmentación. **Nota:** para una entidad nueva, **requerida fragmentación** el valor predeterminado es **No**.                                                           |
| **Soporte técnico de intercambio recuperable requerido** | Seleccione una de las siguientes opciones:<br /><br /> -   **True**. Para habilitar la compatibilidad de intercambio recuperable.<br />-   **FALSE**. Para deshabilitar la compatibilidad de intercambio recuperable. **Nota:** para una entidad nueva, **requerida fragmentación** el valor predeterminado es **FALSE** y solo se habilita si el valor de **requerida fragmentación** es **No**. |
|             **Seleccionar los mensajes**              |                              Seleccione los tipos de mensaje que desea enviar como un lote desde la ventana de mensajes disponibles y, a continuación, haga clic en la migración a la flecha derecha (**>>**).<br /><br /> Para procesar por lotes los mensajes de confirmación entrantes, debe agregar el tipo de mensaje de confirmación. Hacerlo mediante la implementación del esquema de mensaje de confirmación.                              |
|      **Seleccione las confirmaciones de mensajes**      |                               Seleccione los tipos de mensaje que desea [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] para enviar las confirmaciones como un lote desde la ventana de mensajes de confirmación de mensaje disponibles y, a continuación, haga clic en la migración a la flecha derecha (**>>**).                                |

