---
title: Reparación de mensajes y enviar mensajes nuevos | Documentos de Microsoft
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
ms.openlocfilehash: 59ece524ce06430492a3927c0cd1437eef4b216d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214028"
---
# <a name="repairing-messages-and-submitting-new-messages"></a>Reparación de mensajes y enviar mensajes nuevos
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]Reparación de mensajes y nuevo envío permite reparar un mensaje que no se pudo validar XML o motor de reglas de negocios. El proceso de reparación incluye pasos de comprobación y aprobación que garantizan la precisión y la idoneidad de la reparación de mensajes. Este proceso se realiza con [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formas dentro de sitio MRSR.  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]También le permite enviar un mensaje nuevo con este proceso. Un creador de envía el mensaje y el flujo de trabajo puede incluir un taller de reparación y un comprobador, aprobador realizar las mismas tareas como en la reparación de mensajes.  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]garantiza la seguridad de este proceso mediante la asignación de usuarios diferentes para realizar cada tarea. Asignar la reparación adecuada, compruebe o aprobar rol a cada uno de estos usuarios, y cada usuario debe utilizar un certificado específico para realizar la tarea. [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]también admite el uso de departamentos en el procesamiento de mensajes enviados y reparados. Cada departamento implica un flujo de trabajo específico de las tareas realizadas en un conjunto específico de mensajes. En cualquiera de la creación, reparación, compruebe o aprobar pasos, cuando se envía el mensaje, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] llama validación BRE y comprueba que el usuario es miembro de los departamentos apropiados. Para obtener más información acerca de la reparación de mensajes y nuevo envío, consulte [reparar mensajes y nuevo envío](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission.md).  
  
 Si recibe un mensaje sin analizar, reparación de mensajes y nuevo envío muestra el mensaje y una descripción del error en un [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formato y le permite imprimir el mensaje o guardarlo en un archivo. Puede reparar y volver a enviar el mensaje. Sin embargo, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] no ejecutar la validación de BRE o comprobar la pertenencia a un departamento cuando se envía un mensaje sin analizar que ha reparado. Además, un mensaje sin analizar reenviado no es comprobar ni aprobado. Para obtener más información acerca de los mensajes sin analizar, consulte [reparar sin analizar mensajes](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md).  
  
 Esta sección contiene:  
  
-   [Reparación de un mensaje](../../adapters-and-accelerators/accelerator-swift/repairing-a-message.md)  
  
-   [Comprobación de un mensaje](../../adapters-and-accelerators/accelerator-swift/verifying-a-message.md)  
  
-   [Aprobación de un mensaje](../../adapters-and-accelerators/accelerator-swift/approving-a-message.md)  
  
-   [Administrar un mensaje sin analizar](../../adapters-and-accelerators/accelerator-swift/handling-an-unparsed-message.md)  
  
-   [Crear y enviar un mensaje nuevo](../../adapters-and-accelerators/accelerator-swift/creating-and-submitting-a-new-message.md)  
  
-   [Crear una nueva plantilla de mensaje](../../adapters-and-accelerators/accelerator-swift/creating-a-new-message-template.md)