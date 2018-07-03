---
title: Proceso de reparación de mensajes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- repairing messages
- errors, messages
- messages, errors
- validating, messages
- messages, validating
ms.assetid: 87b97cec-5796-4684-bcf0-53285aca7ee2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb8e8cd5a23cd0187b5476688a00d1ca800c45d4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999069"
---
# <a name="message-repair-process"></a>Proceso de reparación de mensajes
De forma predeterminada, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] suspende los mensajes con errores en la cola de suspensión de la base de datos de cuadro de mensajes. Este proceso controla los mensajes con errores por separado de los mensajes correctos. Mediante este mecanismo de forma predeterminada, sin embargo, tiene una capacidad limitada para recuperar los mensajes con errores y corregirlos. La característica de reparación de mensajes y nuevo envío de [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] permite un [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] usuario reparar un mensaje y enviarlo de nuevo. Otro [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] usuario, a continuación, puede comprobar las reparaciones y un tercero puede aprobar las reparaciones.  
  
> [!NOTE]
>  En este contexto, un [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] trata de un usuario que realiza una función en un flujo de trabajo de reparación de departamento. Este usuario A4SWIFT está definida y asociada con un certificado, en el vínculo de los usuarios del cliente Web de perfil. Esto [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] usuario no es el mismo que un [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] cuenta de usuario, como se define en el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] de grupo de usuarios en el [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] utilidad de administración de equipos. La persona que funciona como un [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] usuario debe tener un [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] cuentas de usuario para que pueden usar certificados de la cuenta al enviar un mensaje. Sin embargo, esa persona también puede actuar como otro [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] usuarios: taller de reparación, Comprobador, aprobador o creador. Para obtener más información, consulte [creando los departamentos de TI y los Roles de reparación de mensajes y nuevo envío](../../adapters-and-accelerators/accelerator-swift/creating-departments-and-roles-for-message-repair-and-new-submission.md).  
  
 Con este flujo de trabajo de reparación, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] no suspende un mensaje con errores. Realiza el procesamiento adicional en el mensaje con errores y, a continuación, coloca el mensaje en el cuadro de mensajes, tal como lo haría con un mensaje correcto. La orquestación de reparación coloca el mensaje en el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] sitio MRSR, donde los usuarios pueden realizar sus funciones en [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formularios.  
  
## <a name="message-validation"></a>Validación de mensajes  
 Reparación de mensajes y nuevo envío envía cualquier mensaje que se producen errores en la siguiente validación al sitio MRSR de reparación:  
  
- Validación estructural realizada por el analizador de archivos planos (sin analizar mensajes)  
  
- Validación de datos realizada por el lector de validación de XML  
  
- SWIFT validación de regla de red y el uso realizado por el motor de reglas de negocios (BRE)  
  
  [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] recopila los errores detectados durante la validación en un objeto de colección de errores que acompaña al mensaje SWIFT. El proceso de reparación incluye información de errores de serialización en XML y adjuntarlo al mensaje como parte de un error. Este procesamiento también incluye marcar el mensaje con una propiedad promocionada que indica que el mensaje de error de validación ([!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed == True), y los recuentos de otra propiedad promocionada que notifica el error para cada fase de validación. El mensaje de varias partes resultante consta de las siguientes acciones:  
  
- Una parte del cuerpo que contiene el mensaje con errores  
  
- Una parte de error que contiene el XML de la colección de errores  
  
- Que indica el estado de error de propiedades promocionadas  
  
## <a name="message-repair"></a>Reparación de mensajes  
 La regla de negocios MRSRDepartmentRule dentro de la MRSRDepartmentPolicy determina qué departamento va a controlar el mensaje con errores. La orquestación de reparación de mensajes inicia el flujo de trabajo de reparación de enrutar el mensaje a una bandeja de entrada asociado a la función de reparación en el departamento. El [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] usuario que realiza la función de reparación, abre el mensaje en el [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario, se repara el mensaje y, a continuación, inicia sesión y lo envía. La orquestación enruta el mensaje reparado a cada uno de la reparación, comprobación de regeneración de claves o funciones de aprobación y, después de que el flujo de trabajo se haya completado correctamente, enruta el mensaje al puerto de envío.  
  
 Además de la validación, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] comprueba las firmas del mensaje para determinar lo siguiente:  
  
- Los usuarios en el flujo de trabajo de reparación pertenecen al mismo departamento  
  
- Cada usuario ha iniciado sesión con una sola vez  
  
- La secuencia de funciones corresponden a los usuarios coincide con la secuencia en el flujo de trabajo definido para dicho departamento  
  
  Para obtener más información acerca de los departamentos de TI, consulte [creando los departamentos de TI y los Roles de reparación de mensajes y nuevo envío](../../adapters-and-accelerators/accelerator-swift/creating-departments-and-roles-for-message-repair-and-new-submission.md).  
  
  [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] También permite reparar los mensajes sin analizar. Sin embargo, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] realiza un procesamiento diferente en un mensaje sin analizar reparado. Para obtener más información, consulte [reparación de mensajes sin analizar](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md).