---
title: Reparación de mensajes y envío de mensajes nuevos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- repairing messages
- Message Repair and New Submission
- submitting, messages
- submitting, Message Repair and New Submission
- messages, Message Repair and New Submission
- messages, submitting
- Message Repair and New Submission. about Message Repair and New Submission
ms.assetid: 6abcce90-f611-422a-b3c8-e25f1e75b039
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 569ab44588c2bd89c3533af8cc765e58f743a229
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003317"
---
# <a name="repairing-messages-and-submitting-new-messages"></a>Reparación de mensajes y envío de mensajes nuevos
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Reparación de mensajes y nuevo envío permite reparar un mensaje que no se pudo validar XML o el motor de reglas de negocios. El proceso de reparación incluye pasos de comprobación y aprobación que garantizar la precisión y la adecuación de la reparación de mensajes. Este proceso se realiza mediante Microsoft [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formularios en el sitio MRSR.  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] También le permite enviar un mensaje nuevo con este proceso. Un creador envía el mensaje y el flujo de trabajo puede incluir un taller de reparación, un comprobador y aprobador realiza las mismas tareas como en la reparación de mensajes.  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] garantiza la seguridad de este proceso mediante la asignación de usuarios diferentes para realizar cada tarea. Asignar la reparación correspondiente, compruebe o aprobar rol a cada uno de estos usuarios, y cada usuario debe usar un certificado específico para realizar la tarea. [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] también admite el uso de los departamentos de TI en el procesamiento de mensajes enviados y reparados. Cada departamento implica un flujo de trabajo específico de las tareas realizadas en un conjunto específico de mensajes. En cualquiera de la creación, reparación, compruebe o aprobar los pasos, al enviar el mensaje, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] llama a la validación del BRE y comprueba que el usuario es miembro del departamento apropiado. Para obtener más información acerca de reparación de mensajes y nuevo envío, consulte [reparación de mensajes y nuevo envío](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission.md).  
  
 Si recibe un mensaje sin analizar, reparación de mensajes y nuevo envío muestra el mensaje y una descripción del error en un [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formar y le permite imprimir el mensaje o guardarlo en un archivo. Puede reparar y volver a enviar el mensaje. Sin embargo, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] no llamar a la validación del BRE o comprobar la pertenencia a un departamento cuando se envía un mensaje sin analizar que se ha reparado. Además, un mensaje sin analizar reenviado no comprobado o aprobado. Para obtener más información acerca de los mensajes sin analizar, consulte [reparación de mensajes sin analizar](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md).  
  
 Esta sección contiene:  
  
-   [Reparación de un mensaje](../../adapters-and-accelerators/accelerator-swift/repairing-a-message.md)  
  
-   [Comprobación de un mensaje](../../adapters-and-accelerators/accelerator-swift/verifying-a-message.md)  
  
-   [Aprobación de un mensaje](../../adapters-and-accelerators/accelerator-swift/approving-a-message.md)  
  
-   [Administración de un mensaje sin analizar](../../adapters-and-accelerators/accelerator-swift/handling-an-unparsed-message.md)  
  
-   [Creación y envío de un mensaje nuevo](../../adapters-and-accelerators/accelerator-swift/creating-and-submitting-a-new-message.md)  
  
-   [Creación de una plantilla de mensaje](../../adapters-and-accelerators/accelerator-swift/creating-a-new-message-template.md)