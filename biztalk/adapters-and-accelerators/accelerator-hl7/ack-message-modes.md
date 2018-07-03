---
title: Modos de mensaje de confirmación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message modes, ACK messages
- messages, acknowledgements
- acknowledgements, message modes
- ACK message modes
ms.assetid: ab4a9470-dab2-46d4-8d0a-54dc12f2fa90
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 181617a41ba892a8ac04f2bf2154bbe78e8c892e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967861"
---
# <a name="ack-message-modes"></a>Modos de mensaje de confirmación
Para los mensajes de confirmación (ACK), el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) determina el modo de confirmación y los valores que se usará para rellenar los campos MSH15 y MSH16 de la confirmación de que desea generar. Estos valores están presentes en la configuración de administración de socios comerciales (TPM). Los valores siguientes son posibles para el modo de confirmación:  
  
> [!NOTE]
>  En la lista siguiente, la especificación de HL7 exige los elementos 1 a 3 y que contienen valores MSH15 y MSH16. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] define el elemento 4 para indicar que no se debe generar una confirmación.  
  
1. Original - una confirmación enviado después de validar el encabezado y el cuerpo. Este modo implica la validación del esquema.  
  
2. Mejorado - enviaron dos mensajes de confirmación:  
  
   -   Acepte la confirmación: el sistema receptor envía este tipo de confirmación después de la validación del encabezado. Esta confirmación señala a la aplicación iniciadora que el mensaje está comprometido con la base de datos.  
  
   -   Sistema de aplicación ACK: el receptor envía este tipo de confirmación después de la validación del mensaje completo, incluya el encabezado y el cuerpo.  
  
3. Aplaza - enviaron dos mensajes de confirmación.  
  
   - Modo original: El sistema receptor envía este tipo de confirmación después de la validación del encabezado y cuerpo. Este modo implica la validación del esquema.  
  
   - Modo diferido: La aplicación de línea de negocio reconoce el mensaje después de procesarlo. La aplicación entrega el mensaje aplazado a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], que lo procesa como un mensaje independiente y lo entrega al destino.  
  
4. Static: un correctamente o en caso de error enviado de confirmación.  
  
## <a name="see-also"></a>Vea también  
 [Creación y procesamiento de confirmaciones](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [Guía de programación](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)   
 [Modelo de proceso de confirmación](../../adapters-and-accelerators/accelerator-hl7/ack-process-model.md)   
 [Confirmaciones estáticas](../../adapters-and-accelerators/accelerator-hl7/static-acknowledgments.md)