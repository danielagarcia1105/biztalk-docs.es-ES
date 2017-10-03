---
title: "Modos de mensaje de confirmación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message modes, ACK messages
- messages, acknowledgements
- acknowledgements, message modes
- ACK message modes
ms.assetid: ab4a9470-dab2-46d4-8d0a-54dc12f2fa90
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 122f0851005c7d8abba6c1739ae86a1d65d89625
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="ack-message-modes"></a>Modos de mensaje de confirmación
Para los mensajes de confirmación (ACK), [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) determina el modo de confirmación y los valores que se usará para rellenar los campos MSH15 y MSH16 de la confirmación de que desea generar. Estos valores están presentes en la configuración de administración de socios comerciales (TPM). Los valores siguientes son posibles para el modo de confirmación:  
  
> [!NOTE]
>  En la lista siguiente, la especificación de HL7 exige elementos 1 a 3 y que contienen valores MSH15 y MSH16. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]define el elemento 4 para indicar que no se debe generar una confirmación.  
  
1.  Original: una confirmación enviado después de validar el encabezado y el cuerpo. Este modo implica la validación del esquema.  
  
2.  Mejorado - dos mensajes de confirmación enviados:  
  
    -   Aceptar confirmación – el sistema receptor envía este tipo de confirmación después de la validación del encabezado. Esta confirmación señala a la aplicación iniciadora que el mensaje se compromete a la base de datos.  
  
    -   Sistema de recepción de confirmación-la aplicación envía este tipo de confirmación después de la validación del mensaje completo, incluido el encabezado y el cuerpo.  
  
3.  Aplazado - dos mensajes de confirmación enviados.  
  
    -   Modo original: El sistema receptor envía este tipo de confirmación después de la validación del encabezado y cuerpo. Este modo implica la validación del esquema.  
  
    -   Modo diferido: La aplicación de línea de negocio reconoce el mensaje después de procesarlo. La aplicación entrega el mensaje diferido a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], que lo procesa como un mensaje independiente y lo entrega al destino.  
  
4.  Estático - un correctamente o en caso de error enviado de confirmación.  
  
## <a name="see-also"></a>Vea también  
 [Creación y procesamiento de confirmaciones](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [Guía de programación](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)   
 [Modelo de proceso de confirmación](../../adapters-and-accelerators/accelerator-hl7/ack-process-model.md)   
 [Confirmaciones estáticas](../../adapters-and-accelerators/accelerator-hl7/static-acknowledgments.md)