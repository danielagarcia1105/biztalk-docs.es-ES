---
title: Ejemplo del controlador NAK FRR | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, NAKs
- examples, FRR
- NAKs
- acknowledgements
- FRR, examples
- examples, FRR NAK handler
ms.assetid: be992507-ba8c-461f-a563-f1d7b2ab221d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a3881b8bcf4b62af7653ef6214b4fccdf8402d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207412"
---
# <a name="frr-nak-handler-sample"></a>Ejemplo del controlador FRR NAK
El ejemplo del controlador de NAK FRR muestra cómo crear un controlador personalizado para procesar los mensajes que se correlacionan conciliación de respuesta de FIN (FRR) con las respuestas SWIFT. Este controlador personalizado procesa los mensajes que se correlacionan FRR con un mensaje de confirmación negativo MTS21_FIN_ACKNAK, lo que indica que SWIFT no recibido correctamente el mensaje de A4SWIFT. El controlador personalizado agrega un objeto de error para el mensaje, hacer que el mensaje de un mensaje de dos partes y promociona las propiedades que provocan la orquestación de reparación de mensajes recoger el mensaje. Como resultado, un taller de reparación puede corregir el mensaje y enviarlo para SWIFT Alliance acceso (AAS).  
  
 **Componentes de ejemplo**  
  
 El ejemplo del controlador de FRR NAK incluye los siguientes componentes:  
  
-   **RepairSWIFTRejectedMessage.odx.** Esta orquestación es el controlador personalizado que procesa un mensaje que SWIFT podría no recibe correctamente, enviarlo a la orquestación de reparación de mensajes para que un taller de reparación puede corregir y volver a enviar el mensaje.  
  
-   **RepairSWIFTRejectedMessage.btproj.** Este proyecto incluye RepairSWIFTRejectedMessage.odx y las referencias necesarias para el proyecto para generar e implementar.  
  
-   **RepairSWIFTRejectedMessage.sln.** Esta solución incluye el proyecto RepairSWIFTRejectedMessage.btproj.  
  
 Esta sección contiene:  
  
-   [Implementar el ejemplo del controlador FRR NAK](../../adapters-and-accelerators/accelerator-swift/implementing-the-frr-nak-handler-sample.md)  
  
-   [Cómo funciona el ejemplo del controlador FRR NAK](../../adapters-and-accelerators/accelerator-swift/how-the-frr-nak-handler-sample-works.md)  
  
