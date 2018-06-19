---
title: Problemas conocidos de confirmaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- known issues, acknowledgements
- acknowledgements, known issues
ms.assetid: cb45f80e-ba89-4b3f-a770-4b1cf9b8e220
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af5964e94f2ddc1d53d5259b174f8e551353711d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204580"
---
# <a name="acknowledgments-known-issues"></a>Problemas conocidos de confirmaciones
Esta sección contiene información útil que puede ayudar a evitar errores de confirmación (ACK).  
  
## <a name="hl7-v21-acknowledgment-message-accepted-even-if-it-contains-msa6-field"></a>Aceptar el mensaje de confirmación de HL7 V2.1 aunque contenga MSA6 campo  
 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) aceptará un mensaje de confirmación de HL7 V2.1 incluso si contiene el campo MSA6.  
  
## <a name="msa-01-value-not-generated-for-commit-acknowledgment-errors"></a>Valor de MSA-01 no generado errores de reconocimiento de confirmación  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]no genera un código de confirmación de MSA-01 para errores de confirmaciones de confirmación (CE).  
  
## <a name="two-way-mllp-adapter-might-not-detect-a-problem-with-an-ack"></a>Adaptador MLLP bidireccional podría no detectar un problema con una confirmación  
 Cuando [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] recibe una confirmación en un adaptador MLLP bidireccional, el adaptador realiza una validación ligera en la confirmación para determinar su validez. Si se encuentra sea válido, se extrae el campo MSA1 y dependiendo de su valor, el adaptador de reintentos, suspende o elimina el mensaje original a la que se responde la confirmación. Sin embargo, dado que la validación realizada por el adaptador no es una validación completa, es posible que el adaptador no detectan un problema con la confirmación. Por ejemplo, el adaptador puede determinar que la confirmación es válida y eliminar el mensaje original, mientras que la canalización podría determinar que la confirmación no tenía el formato correcto y suspender el mensaje de confirmación.  
  
## <a name="v2xml-acks-with-multiple-errors-will-fail-validation"></a>V2. Confirmaciones de XML con varios errores se considerará no válido  
 Si una entrada V2. Mensaje XML que contiene más de un error, el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] analizador puede generar un V2. XML ACK con más de un error en el campo de error. Este tipo V2. XML ACK se producirá un error de validación, porque el estándar HL7 especifica que el analizador puede informar solo error en una V2. Campo de error de XML ACK.  
  
## <a name="mllp-performance-counters-do-not-count-acks"></a>Contadores de rendimiento de MLLP no cuentan confirmaciones  
 Una medida de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] rendimiento es el número de mensajes procesados por un adaptador MLLP, como se indica en los contadores de rendimiento de MLLP. Este contador mide el número de mensajes recibidos o transmitida. Sin embargo, el recuento no mide el número de confirmaciones recibidos o enviados.  
  
## <a name="nak-generated-by-two-way-mllp-adapter"></a>NAK generado por el adaptador MLLP bidireccional  
 Cuando un adaptador MLLP bidireccional suspende un mensaje, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] genera un NAK (confirmación negativa) y lo coloca en la base de datos de cuadro de mensajes. Esto puede ser un comportamiento inesperado. Puede que desee quitar el NAK desde la base de datos de cuadro de mensajes o asignar a otro mensaje.  
  
## <a name="data-type-of-an-ack-to-a-batch-message"></a>Tipo de datos de una confirmación para un mensaje por lotes  
 En un mensaje de confirmación generado en respuesta a un mensaje por lotes, el campo MSH10 (Id. de control de mensajes) será un GUID, en lugar de basarse en el tipo de datos del campo MSH10 en el mensaje de lote.  
  
## <a name="generated-acknowledgments-doc-type"></a>Tipo de documento de confirmaciones generado  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]genera las confirmaciones mediante el tipo de documento http://[!INCLUDE[btsCoName](../../includes/btsconame-md.md)].com/HealthCare/HL7/2X#ACK_24_GLO_DEF o http://[!INCLUDE[btsCoName](../../includes/btsconame-md.md)].com/HealthCare/HL7/2X #ACK_25_GLO_DEF. Si la entidad de destino usa un espacio de nombres diferente, debe aplicar una asignación de cuerpo en el puerto de envío; de lo contrario, podría experimentar errores de serialización.  
  
## <a name="see-also"></a>Vea también  
 [Problemas conocidos](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)