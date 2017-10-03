---
title: "Proceso de reparación de mensajes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- repairing messages
- errors, messages
- messages, errors
- validating, messages
- messages, validating
ms.assetid: 87b97cec-5796-4684-bcf0-53285aca7ee2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 442e49c347b4adf84dd7e6ee86c3b3595452cb34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-repair-process"></a>Proceso de reparación de mensajes
De forma predeterminada, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] suspende los mensajes con errores en la cola de suspensión de la base de datos de cuadro de mensajes. Este proceso controla los mensajes error por separado de los mensajes correctos. Mediante este mecanismo de forma predeterminada, sin embargo, tiene una capacidad limitada para recuperar mensajes con errores y corregirlos. La característica de reparación de mensajes y nuevo envío de [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] permite un [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] usuario reparar un mensaje y enviarlo de nuevo. Otro [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] usuario, a continuación, puede comprobar las reparaciones, y una tercera puede aprobar las reparaciones.  
  
> [!NOTE]
>  En este contexto, un [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] trata de un usuario que realiza un rol en un flujo de trabajo de reparación de departamento. Este usuario de A4SWIFT está definido y asociada con un certificado, en el vínculo de los usuarios del cliente Web de perfil. Esto [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] usuario no es el mismo que un [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] cuenta de usuario, como se define en el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] de grupo de usuarios en el [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] utilidad de administración de equipos. La persona que funciona como un [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] usuario debe tener un [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] cuenta de usuario pueden utilizar los certificados de esa cuenta al enviar un mensaje. Sin embargo, esa persona también puede actuar como otro [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] a los usuarios: taller de reparación, Comprobador, aprobador o creador. Para obtener más información, consulte [crear departamentos y Roles para la reparación de mensajes y nuevo envío](../../adapters-and-accelerators/accelerator-swift/creating-departments-and-roles-for-message-repair-and-new-submission.md).  
  
 Con este flujo de trabajo de reparación, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] no suspende un mensaje con errores. Realiza un procesamiento adicional en el mensaje con errores y, a continuación, coloca el mensaje en el cuadro de mensajes, tal como haría con un mensaje correcto. La orquestación de reparación coloca el mensaje en el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] sitio MRSR, donde los usuarios pueden realizar sus funciones en [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formularios.  
  
## <a name="message-validation"></a>Validación del mensaje  
 Reparación de mensajes y nuevo envío envía los mensajes que se producen errores en las siguientes de validación al sitio MRSR para la reparación:  
  
-   Validación estructural realizada por el analizador de archivos sin formato (sin analizar mensajes)  
  
-   Validación de datos realizada por el lector de validación de XML  
  
-   SWIFT validación de regla de red y el uso realizado por el motor de reglas de negocios (BRE)  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]recopila los errores encontrados durante la validación en un objeto de colección de errores que acompaña al mensaje SWIFT. El proceso de reparación incluye información de error serializar en XML y adjuntarlo al mensaje como parte de un error. Este procesamiento también incluye marcar el mensaje con una propiedad promocionada que indica que el mensaje no pudo validar ([!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed == True), y los recuentos de otra propiedad promocionada que notifica el error para cada fase de validación. El mensaje de varias partes resultante consta de las siguientes acciones:  
  
-   Una parte del cuerpo que contiene el mensaje error  
  
-   Una parte de error que contiene el XML de la colección de errores  
  
-   Promocionar propiedades que indican el estado de error  
  
## <a name="message-repair"></a>Reparación de mensajes  
 La regla de negocios MRSRDepartmentRule dentro de la MRSRDepartmentPolicy determina qué departamento tratará el mensaje error. La orquestación de reparación de mensajes inicia el flujo de trabajo de reparación al enrutar el mensaje a una bandeja de entrada asociado a la función de reparación en el departamento. El [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] usuario que realiza la función de reparación abre el mensaje en el [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario, repara el mensaje y, a continuación, inicia sesión y lo envía. La orquestación enruta el mensaje reparado a cada una de la reparación, comprobación de regeneración de claves o funciones de aprobación y, después de que se haya completado correctamente el flujo de trabajo, enruta el mensaje al puerto de envío.  
  
 Además de la validación, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] comprueba las firmas del mensaje para determinar lo siguiente:  
  
-   Los usuarios del flujo de trabajo de reparación pertenecen al mismo departamento  
  
-   Cada usuario ha iniciado sesión con una sola vez  
  
-   La secuencia de los roles correspondientes a los usuarios coincide con la secuencia en el flujo de trabajo definido para dicho departamento  
  
 Para obtener más información acerca de los departamentos, consulte [crear departamentos y Roles para la reparación de mensajes y nuevo envío](../../adapters-and-accelerators/accelerator-swift/creating-departments-and-roles-for-message-repair-and-new-submission.md).  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]También permite reparar mensajes sin analizar. Sin embargo, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] realice el procesamiento diferentes en un mensaje sin analizar reparado. Para obtener más información, consulte [reparar sin analizar mensajes](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md).