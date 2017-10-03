---
title: "Modelo de proceso de confirmación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- acknowledgements, process flow
- ACK process model
ms.assetid: 3c6a5eef-57ef-41f7-9782-e1cbc4dd78e1
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 846ecf4d8eee4eca0e8a75a3444a1478b7db5910
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="ack-process-model"></a>Modelo de proceso de confirmación
La siguiente secuencia de pasos describe el modelo de proceso de confirmación (ACK):  
  
1.  Cuando el personal de admisión registrar información de pacientes admisión en el sistema de admisión (ADT), el sistema genera un evento de desencadenador.  
  
2.  El sistema ADT genera un mensaje de registro de paciente codificado para HL7 (ADT ^ A04) y lo entrega para el Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]).  
  
3.  El [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] system aplica a un contenedor MLLP en el ADT ^ A04 mensaje y lo envía a la [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] motor de interfaz.  
  
    -   Requisito de confirmación de 'Modo Original' está preconfigurado  
  
    -   15 de MSH y 16 tienen valores null  
  
4.  El [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] interfaz motor valida el mensaje y si se produce la validación correctamente, genera el mensaje de confirmación con el estado **MSA01 = AA**.  
  
5.  El [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] motor interfaz transforma el ADT ^ A04 mensaje envolvente con contenedores MLLP y enrutamiento para el sistema de información de laboratorio (LIS).  
  
    -   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]preconfigura confirmación 'Modo mejorado'  
  
    -   15 de MSH y 16 = AL.  
  
6.  La capa de interfaz de LIS valida el encabezado de confirmar el mensaje y generar una confirmación Aceptar con el estado **MSA1 = CA**. La capa de interfaz enruta el mensaje con el contenedor MLLP el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] motor de interfaz.  
  
7.  La capa de interfaz de LIS valida el mensaje completo y se genera una confirmación de la aplicación con el estado **MSA1 = AA**. La capa de interfaz enruta el mensaje con el contenedor MLLP el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] motor de interfaz.  
  
    -   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]preconfigura 'Confirmación necesaria' confirmación de la confirmación  
  
    -   15 de MSH = AL., lo que indica que el sistema receptor debe confirmar la confirmación con un mensaje de aceptación de confirmación  
  
8.  La capa de interfaz de LIS entrega el mensaje a la capa de aplicación según los requisitos de formato.  
  
9. El [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] interfaz motor valida la confirmación recibida de la capa de interfaz de LIS (en el paso 7 anterior) y responde con una confirmación a la capa de interfaz de LIS con el estado **MSA1 = CA**.  
  
10. Un usuario del sistema LIS revisa la información del paciente.  
  
## <a name="see-also"></a>Vea también  
 [Creación y procesamiento de confirmaciones](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [Guía de programación](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)