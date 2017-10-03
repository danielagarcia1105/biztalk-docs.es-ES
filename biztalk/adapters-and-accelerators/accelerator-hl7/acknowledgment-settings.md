---
title: "Configuración de confirmación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- acknowledgements, configuring
- acknowledgements, acknowledgement types
- configuring, acknowledgements
ms.assetid: 99ab8caa-8788-4438-96db-8001a6523cc8
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34eda8a977de0dadbad974268b46e4d580cc1f33
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="acknowledgment-settings"></a>Configuración de confirmación
Usa el **confirmación** ficha de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración (en el nivel superior **partes** pestaña) para configurar opciones de confirmación (ACK).  
  
 Están disponibles los siguientes tipos de confirmación:  
  
-   **Ninguna**. Seleccione esta opción si no desea configurar las confirmaciones.  
  
-   **Original**. Seleccione esta opción para configurar **MSH1: separador de campos**, **MSH2: codificación de caracteres**y el **MSH8 – seguridad** opciones solo.  
  
-   **Mejorado**. Seleccione esta opción para configurar todas las opciones de confirmación disponibles.  
  
-   **Deferred**. Seleccione esta opción para configurar **MSH1: separador de campos**, **MSH2: codificación de caracteres**, y **MSH8 – seguridad** opciones solo.  
  
-   **Estático**. Seleccione esta opción para configurar el **en caso de éxito** y **en caso de error** opciones de confirmación.  
  
 Una vez que se establece el tipo de confirmación, puede establecer valores para los campos de encabezado y confirmaciones, dependiendo del tipo de confirmación.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Opciones de configuración de confirmación](../../adapters-and-accelerators/accelerator-hl7/ack-configuration-settings.md)  
  
-   [Configurar confirmaciones de mensajes](../../adapters-and-accelerators/accelerator-hl7/configuring-message-acknowledgments.md)