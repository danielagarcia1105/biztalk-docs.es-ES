---
title: Reparación y nuevo envío de mensajes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- repairing messages
- resubmitting messages
- errors, messages
- messages, errors
- messages, resubmitting
ms.assetid: 5bc6bfa2-8210-4dd3-89bb-5455e294ca92
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5bc15351848fe68d6ef54c31fc6d58c075bb1c58
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209988"
---
# <a name="message-repair-and-new-submission"></a>Reparación de mensajes y nuevo envío
La característica de reparación de mensajes y nuevo envío de [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] proporciona una manera para que pueda reparar MT y MX mensajes que no superan la validación. Mediante el sitio de SharePoint de MRSR (implementado por el usuario), puede ver cómo el mensaje de error de validación. En el sitio MRSR, puede abrir el mensaje en un formulario de InfoPath que permite identificar el error, repare el mensaje y enviarlo para volver a procesar.  
  
 Reparación de mensajes y nuevo envío admite la reparación de mensajes basada en roles. Un flujo de trabajo de reparación completa incluye la aprobación, comprobación y reparación. Un flujo de trabajo de reparación se asocia a un departamento que define los roles (o fases) del flujo de trabajo y configura un usuario de A4SWIFT para cada rol. Cada función de reparación tiene una vista de sitio MRSR independiente adaptada para el rol. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]realiza la validación y cada usuario de A4SWIFT realizar una firma de función en el mensaje, mediante un certificado, para garantizar un proceso seguro.  
  
 Además de reparación de mensajes, A4SWIFT le permite enviar un mensaje nuevo con un mejor [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario. Un cuarto usuario de A4SWIFT, un creador, realiza esta función. El proceso también realiza la validación y puede incluir funciones de reparación, verificación y aprobación para garantizar el envío con éxito. A4SWIFT controla nuevo envío de mensajes a través de un [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] forman la misma manera que controla un mensaje reparado.  
  
 Esta sección contiene:  
  
-   [Proceso de reparación de mensajes](../../adapters-and-accelerators/accelerator-swift/message-repair-process.md)  
  
-   [Crear Roles y departamentos de reparación de mensajes y nuevo envío](../../adapters-and-accelerators/accelerator-swift/creating-departments-and-roles-for-message-repair-and-new-submission.md)  
  
-   [Uso de un formulario de InfoPath para reparar un mensaje o envíe un mensaje nuevo](../../adapters-and-accelerators/accelerator-swift/using-an-infopath-form-to-repair-a-message-or-submit-a-new-message.md)  
  
-   [Procesamiento especial en la reparación de mensajes y nuevo envío](../../adapters-and-accelerators/accelerator-swift/special-processing-in-message-repair-and-new-submission.md)  
  
-   [Reparación de mensajes sin analizar](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md)  
  
-   [Reparación de mensajes y nuevo procesamiento de servicio de envío](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission-service-processing.md)