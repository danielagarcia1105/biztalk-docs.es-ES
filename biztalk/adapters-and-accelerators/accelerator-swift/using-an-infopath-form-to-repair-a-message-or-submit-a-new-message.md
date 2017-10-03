---
title: "Uso de un formulario de InfoPath para reparar un mensaje o envíe un mensaje nuevo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, messages
- InfoPath forms, verifying messages
- submitting, messages
- InfoPath forms, repairing messages
- Bank Identifier Code (BIC)
- messages, submitting
- messages, repairing
- unparsed messages
- repairing messages, unparsed messages
- messages, unparsed messages
- messages, modifying
- messages, InfoPath forms
- modifying, messages
- messages, approving
- repairing messages, InfoPath forms
- messages, creating
- approving messages
- messages, verifying
- verifying, messages
ms.assetid: fb1a885f-fb01-42be-88bc-f68715f689f7
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f89959b1900ce03717f2bb28efda7651c5008e7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-an-infopath-form-to-repair-a-message-or-submit-a-new-message"></a>Uso de un formulario de InfoPath para reparar un mensaje o envíe un mensaje nuevo
Para reparar, comprobar, aprobar o crear un mensaje, se trabaja en un [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario que se abre desde el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] sitio Web de MRSR. El sitio MRSR contiene un [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formato de cada tipo de mensaje y un [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formato para los mensajes sin analizar. Reparación de mensajes y nuevo envío envía mensajes que necesita reparación, la comprobación o la aprobación a la biblioteca de documentos MRSR adecuada, donde se puede abrir.  
  
 Al abrir un mensaje en una biblioteca de documentos MRSR [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] muestra un [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario que se rellena con los datos del mensaje. Para realizar la operación dentro de la [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario, lo que permite manipular los datos en los campos con la etiqueta, para seleccionar valores de listas de lista desplegable (si procede) y para ver si un campo es obligatorio u opcional. [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]garantiza que la reparación de mensajes y nuevo envío proceso es seguro, que requieren una cuenta de dominio y una firma con un certificado para el envío.  
  
 Para realizar una operación en un mensaje en el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] sitio MRSR, debe implementar la [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario de ese tipo de mensaje. Esto carga la [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] requerida para el mensaje en la biblioteca de documentos de plantillas de formulario.  
  
## <a name="repairing-a-message"></a>Reparación de un mensaje  
 Para reparar, comprobar, aprobar o crear un mensaje, se trabaja en un formulario de InfoPath que se abre desde dentro del sitio de SharePoint de MRSR. El mensaje que se desean reparar se publica en el sitio MRSR. Reparación de mensajes y nuevo envío envía mensajes que necesita reparación, la comprobación o la aprobación a la biblioteca de documentos de sitio MRSR adecuada, donde se puede abrir.  
  
 Cuando se abre un mensaje en una biblioteca de documentos del sitio MRSR, A4SWIFT muestra un formulario de InfoPath que se rellena con los datos del mensaje. Realizar la operación en el formulario de InfoPath, que permite manipular los datos en los campos con la etiqueta, para seleccionar valores de listas de lista desplegable (si procede) y para ver si un campo es obligatorio u opcional. A4SWIFT garantiza que la reparación de mensajes y nuevo envío proceso es seguro, que requieren una cuenta de dominio y una firma con un certificado para el envío.  
  
 Para llevar a cabo una operación en un mensaje en el sitio MRSR, debe implementar el formulario de InfoPath para ese tipo de mensaje. Esto carga el formulario de InfoPath requerido para el mensaje en la biblioteca de documentos de plantillas.  
  
## <a name="verifying-a-message"></a>Comprobación de un mensaje  
 Un flujo de trabajo de reparación puede incluir una fase de comprobación. En esta fase, una vez un taller de reparación ha reparado un mensaje, un comprobador de comprueba que las reparaciones en el mensaje están correctas. Para ello, abra el mensaje en una [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario desde el \<nombre de departamento > _RekeyVerify biblioteca de documentos de su sitio MRSR y compruebe que las reparaciones que se realizaron en el mensaje están correctas. También debe regenerar los datos en algunos de los campos que requieren la regeneración de claves. Todas las fases de comprobación requieren la regeneración de claves, pero se pueden personalizar los campos (si existe) necesitan regeneración. Para obtener más información acerca de la comprobación de regeneración de claves, consulte [un procesamiento especial en la reparación de mensajes y nuevo envío](../../adapters-and-accelerators/accelerator-swift/special-processing-in-message-repair-and-new-submission.md).  
  
 Un flujo de trabajo que consta de todas las fases posibles incluye una o varias fases de comprobación. Sin embargo, no necesita incluir una fase de comprobación un flujo de trabajo.  
  
## <a name="approving-a-message"></a>Aprobación de un mensaje  
 Un flujo de trabajo de reparación puede incluir una fase de aprobación. En esta fase, después de un comprobador ha comprobado las reparaciones en un mensaje o los datos en un mensaje nuevo, aprobador comprueba visualmente que son correctas las reparaciones en el mensaje. Tenga en cuenta que una fase de comprobación se compone de una comprobación de la regeneración de claves, mientras que una fase de aprobación está formada por una comprobación visual.  
  
## <a name="accepting-or-rejecting-the-changes-to-a-message"></a>Aceptar o rechazar los cambios realizados en un mensaje  
 Después de completar una fase, un creador, Taller de reparación, Comprobador o aprobador puede aceptar los cambios, cancelar los cambios o rechazar los cambios. Si el envío se realiza correctamente, aceptación mueve el mensaje a la siguiente fase. Rechazo envía el mensaje con los cambios rechazados. Cancelación cancela el proceso de envío y el mensaje permanece en la fase actual.  
  
 Si se rechaza un mensaje en Verifique o aprobar fase, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] devuelve el mensaje a la primera fase definida para ese flujo de trabajo (crear o reparar). El flujo de trabajo se restablece, por lo que cualquier taller de reparación puede reparar el mensaje. Si la primera fase del flujo de trabajo rechaza el mensaje, la orquestación de reparación publica el mensaje en el cuadro de mensajes con las propiedades promocionadas correspondientes. Puede escribir un controlador personalizado para procesar estos mensajes. Para obtener más información, consulte [crear un controlador personalizado para los mensajes rechazados](../../adapters-and-accelerators/accelerator-swift/creating-a-custom-handler-for-rejected-messages.md).  
  
 Si se rechaza un mensaje en la fase create o reparación, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] suspende el mensaje, y recibirá el mensaje de error: "No se pudo restablecer a la primera fase del flujo de trabajo."  
  
## <a name="repairing-an-unparsed-message"></a>Reparación de un mensaje sin analizar  
 Si se produce un error en un mensaje debido a un error de análisis, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] enruta el mensaje a la biblioteca de documentos sin analizar en el sitio MRSR. Al igual que con los mensajes que no superan la validación, cuando haga doble clic en el mensaje, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] muestra un [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario que se rellena con los datos del mensaje. Repare el mensaje desde dentro del formulario. Cuando se envía el mensaje, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] envía el mensaje directamente a la Bandeja de salida sin comprobar o aprobación. Para obtener más información, consulte [reparar sin analizar mensajes](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md).  
  
## <a name="creating-and-submitting-a-new-message"></a>Crear y enviar un mensaje nuevo  
 Puede crear un nuevo mensaje en el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] sitio de MRSR para mostrar un formulario de mensaje nuevo, escribir datos y su envío. Para obtener más información, consulte [crear y enviar un mensaje nuevo](../../adapters-and-accelerators/accelerator-swift/creating-and-submitting-a-new-message.md).  
  
 Para crear un nuevo mensaje, debe implementar un nuevo formulario de mensaje para ese tipo de mensaje. Esto carga el formulario XML requerido para el mensaje en una biblioteca de documentos que se crea para contienen formularios de mensaje nuevo.  
  
 Cuando se crea un mensaje desde el formulario de mensaje nuevo de forma predeterminada, ninguno de los campos se rellenan, necesidad de escribir datos en todos los campos. Puede rellenar los campos en forma de abrir un mensaje, escribir datos y, a continuación, ejecuta la operación de guardar-como comando en el menú archivo en el sitio MRSR. Puede asignar a la [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] forman un nombre diferente y guárdelo en una biblioteca de documentos diferente.  
  
## <a name="looking-up-a-bic"></a>Buscar un BIC  
 Cuando se trabaja un [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formar en el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] sitio MRSR, puede que necesite escribir un código de identificador de banco (BIC). [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]Proporciona una utilidad que puede usar para buscar un BIC. En el [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] de formulario, haga clic en búsqueda BIC en el panel derecho del formulario. Esto muestra un formulario para buscar el BIC basándose en el nombre del banco, o viceversa. Se busca en la tabla Bicplus de la [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] base de datos. Para obtener más información sobre la tabla Bicplus, consulte [habilitar la validación de Bank identificador códigos](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md) y [administración de la tabla Bicplus en la base de datos de A4SWIFT](../../adapters-and-accelerators/accelerator-swift/managing-the-bicplus-table-in-the-a4swift-database.md).