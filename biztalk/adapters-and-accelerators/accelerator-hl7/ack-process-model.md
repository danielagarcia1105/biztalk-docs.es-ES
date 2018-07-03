---
title: Modelo de proceso de confirmación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, process flow
- ACK process model
ms.assetid: 3c6a5eef-57ef-41f7-9782-e1cbc4dd78e1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98fac157c3c3bfa62825fd3c5cb59c68aac528e6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970637"
---
# <a name="ack-process-model"></a>Modelo de proceso de confirmación
La siguiente secuencia de pasos describe el modelo de proceso de confirmación (ACK):  
  
1. Cuando el personal de admisión registrar información de admisión de pacientes en el sistema de pacientes (ADT), el sistema genera un evento de desencadenador.  
  
2. El sistema ADT genera un mensaje de registro de paciente de HL7 codificado (ADT ^ A04) y lo entrega al Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]).  
  
3. El [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] sistema aplica un contenedor MLLP en el ADT ^ A04 mensaje y lo envía a la [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] motor de interfaz.  
  
   -   Requisito de confirmación 'Modo Original' está preconfigurado  
  
   -   MSH 15 y 16 tienen valores null  
  
4. El [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] interfaz motor valida el mensaje y si se produce la validación correctamente, genera el mensaje de confirmación con el estado **MSA01 = AA**.  
  
5. El [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] motor interfaz transforma el ADT ^ A04 mensaje delimitarlo con contenedores MLLP y enrutarlo a del sistema de información de laboratorio (LIS).  
  
   - [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] preconfigura la confirmación 'Modo mejorado'  
  
   - MSH 15 y 16 = AL  
  
6. La capa de interfaz de LIS valida el encabezado al confirmar el mensaje y generar una confirmación Aceptar con el estado **MSA1 = CA**. La capa de interfaz enruta el mensaje con el contenedor MLLP el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] motor de interfaz.  
  
7. La capa de interfaz de LIS valida el mensaje completo y genera una confirmación de la aplicación con el estado **MSA1 = AA**. La capa de interfaz enruta el mensaje con el contenedor MLLP el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] motor de interfaz.  
  
   - [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] preconfigura 'Confirmación necesaria' reconocer la confirmación  
  
   - 15 de MSH = AL., lo que indica que el sistema receptor debe confirmar la confirmación con un mensaje de confirmación de aceptación  
  
8. La capa de interfaz de LIS entrega el mensaje a la capa de aplicación según los requisitos de formato.  
  
9. El [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] interfaz motor valida la confirmación recibida de la capa de interfaz de LIS (en el paso 7 anterior) y responde con una confirmación a la capa de interfaz de LIS con el estado **MSA1 = CA**.  
  
10. Un usuario del sistema LIS revisa la información del paciente.  
  
## <a name="see-also"></a>Vea también  
 [Creación y procesamiento de confirmaciones](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [Guía de programación](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)