---
title: Configuración de las confirmaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, configuring
- acknowledgements, acknowledgement types
- configuring, acknowledgements
ms.assetid: 99ab8caa-8788-4438-96db-8001a6523cc8
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8c1f19fa1a0d1abaad29f454f25f0d8608ed497
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967141"
---
# <a name="acknowledgment-settings"></a>Configuración de confirmación
Usa el **confirmación** ficha de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración (bajo el alto nivel **partes** pestaña) para configurar las opciones de confirmación (ACK).  
  
 Están disponibles los siguientes tipos de confirmación:  
  
- **Ninguna**. Seleccione esta opción si no desea configurar confirmaciones.  
  
- **Original**. Seleccione esta opción para configurar **MSH1: separador de campos**, **MSH2: codificación de caracteres**y el **MSH8 – seguridad** sólo las opciones.  
  
- **Mejorado**. Seleccione esta opción para configurar todas las opciones disponibles de confirmación.  
  
- **Aplaza**. Seleccione esta opción para configurar **MSH1: separador de campos**, **MSH2: codificación de caracteres**, y **MSH8 – seguridad** sólo las opciones.  
  
- **Estática**. Seleccione esta opción para configurar el **en caso de éxito** y **en caso de error** opciones de confirmación.  
  
  Una vez que se establece el tipo de confirmación, puede establecer los valores de campos de encabezado y las confirmaciones, en función del tipo de confirmación.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Parámetros de configuración de ACK](../../adapters-and-accelerators/accelerator-hl7/ack-configuration-settings.md)  
  
-   [Configuración de confirmaciones de mensajes](../../adapters-and-accelerators/accelerator-hl7/configuring-message-acknowledgments.md)