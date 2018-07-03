---
title: Ejemplo del controlador NAK de FRR | Microsoft Docs
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
ms.openlocfilehash: 35574f47af789054bd8192da93ce5cffa1b3984b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996941"
---
# <a name="frr-nak-handler-sample"></a>Ejemplo del controlador NAK de FRR
El ejemplo del controlador NAK de FRR muestra cómo crear un controlador personalizado para procesar los mensajes que se correlacionan conciliación de respuesta de FIN (FRR) con las respuestas de SWIFT. Este controlador personalizado procesa los mensajes que se correlacionan FRR con un mensaje de confirmación negativo MTS21_FIN_ACKNAK, que indica que SWIFT no recibido correctamente el mensaje de A4SWIFT. El controlador personalizado agrega un objeto de error para el mensaje, que el mensaje de un mensaje de dos partes y promociona las propiedades que provocan la orquestación de reparación de mensajes recoger el mensaje. Como resultado, un taller de reparación puede corregir el mensaje y lo vuelva a enviar a SWIFT Alliance acceso (AAS).  
  
 **Componentes de ejemplo**  
  
 El ejemplo del controlador NAK de FRR incluye los siguientes componentes:  
  
- **RepairSWIFTRejectedMessage.odx.** Esta orquestación es el controlador personalizado que procesa un mensaje que SWIFT podría no recibe correctamente, enrutarlo a la orquestación de reparación de mensajes para que pueda corregir y volver a enviar el mensaje de un taller de reparación.  
  
- **RepairSWIFTRejectedMessage.btproj.** Este proyecto incluye RepairSWIFTRejectedMessage.odx y las referencias necesarias para el proyecto para compilar e implementar.  
  
- **RepairSWIFTRejectedMessage.sln.** Esta solución incluye el proyecto RepairSWIFTRejectedMessage.btproj.  
  
  Esta sección contiene:  
  
- [Implementación del ejemplo del controlador NAK de FRR](../../adapters-and-accelerators/accelerator-swift/implementing-the-frr-nak-handler-sample.md)  
  
- [Cómo funciona el ejemplo del controlador NAK de FRR](../../adapters-and-accelerators/accelerator-swift/how-the-frr-nak-handler-sample-works.md)  
  
