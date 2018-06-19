---
title: Reparación de mensajes y nuevo envío las propiedades promocionan | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- promoted properties, Message Repair and New Submission
- Message Repair and New Submission, promoted properties
ms.assetid: e980c905-d07f-4fc2-89ca-05e597410733
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76e4f57e9f5179ceea073ef281131a8cd3573703
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22208660"
---
# <a name="message-repair-and-new-submission-promoted-properties"></a>Propiedades promocionadas reparación de mensajes y nuevo envío
El [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] reparación de mensajes y nuevo envío conciliación incluye las siguientes propiedades promocionadas.  
  
|Nombre promocionada|Description|Tipo de datos|Intervalo de valores|Ejemplo de uso|  
|-------------------|-----------------|---------------|-----------------|-------------------|  
|**BTS. Operaciones**|Indica el estado de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] de procesamiento. Puede ser uno de los valores siguientes:<br /><br /> **A4SWIFT_MrsrCompleted** indica que la reparación de mensajes y el nuevo proceso de envío se realizó correctamente.<br /><br /> **A4SWIFT_MrsrFailed** indica que la reparación de mensajes y el nuevo proceso de envío ha fallado.<br /><br /> **A4SWIFT_MrsrUnparsedFailed** indica que ha fallado la reparación de un mensaje sin analizar.<br /><br /> **A4SWIFT_MrsrUnparsedComplete** indica que se realizó correctamente la reparación de un mensaje sin analizar.<br /><br /> **A4SWIFT_DasmMarkedAsFailed** indica que el mensaje de error de procesamiento en la fase de desensamblador de la canalización de recepción.|String|-A4SWIFT_MrsrCompleted<br />-A4SWIFT_MrsrFailed<br />-A4SWIFT_MrsrUnparsedFailed<br />-A4SWIFT_MrsrUnparsedCompleted<br />-A4SWIFT_DasmMarkedAsFailed|Cuando la orquestación MrsrRepair recibe un mensaje sin analizar reparado después de la reparación, Establece la **BTS. Operación** propiedad a "A4SWIFT_MRSRCompleted" y la **A4SWIFT_Failed** propiedad en False, y, a continuación, enruta el mensaje en el cuadro de mensajes. Estas propiedades Asegúrese de que el mensaje sin analizar reparado no especifique el proceso de reparación de mensaje nuevo.|  
|**Microsoft.Solutions.A4SWIFT. Property.A4SWIFT_Failed**|Indica si [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] correcta o incorrectamente ha procesado el mensaje.|Boolean|True, False|Utilizadas por la orquestación MrsrRepair para suscribirse solo a mensajes del cuadro de mensajes con errores de validación.|  
|**Microsoft.Solutions.A4SWIFT. Property.A4SWIFT_SwiftBound**|Indica si el mensaje está vinculado a la red SWIFT.|Boolean|True, False|Utilizadas por la orquestación MrsrRepair para suscribirse solo a mensajes del cuadro de mensajes que se enlazan para la red SWIFT.|  
|**Microsoft.Solutions.A4SWIFT. MRSRProperty.A4SWIFT_MRSRIsNewSubmission**|Indica si el mensaje que se está procesando es un nuevo envío.|Boolean|True, False|Utilizadas por la orquestación MrsrRepair para indicar que se ha creado un mensaje en la fase de creación del flujo de trabajo.|  
|**Microsoft.Solutions.A4SWIFT. MRSRProperty.A4SWIFT_MRSRLastStage**|Indica la última fase del flujo de trabajo de reparación que se realizó correctamente.|String|-|Una de las fases definidas para un flujo de trabajo de departamento. Puede crear, reparar, compruebe de regeneración de claves, o una fase de aprobación.|  
|**Microsoft.Solutions.A4SWIFT. MRSRProperty.A4SWIFT_ MRSRDepartment**|Indica que el departamento que se usa en la reparación de mensajes y nuevo envío, tal y como especifica la directiva del BRE MrsrDepartmentPolicy.|String|-|Establecer en el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] consola de administración.|  
|**Microsoft.Solutions.A4SWIFT. MRSRProperty.A4SWIFT_ MRSRFailedReason**|Indica el motivo del error de la reparación de mensajes y el nuevo proceso de envío. Puede ser uno de los valores siguientes:<br /><br /> Rechazado indica que el usuario rechazó el mensaje desde el [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario.<br /><br /> InvalidDigitalSignature indica que el certificado del usuario no es válido.<br /><br /> Tiempo de espera indica que se ha alcanzado el valor de tiempo de espera de MRSROrchestration.<br /><br /> InvalidWorkFlow indica que el flujo de trabajo definido para un departamento no es válido.<br /><br /> CantRepairIn[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] indica que no se pudo abrir el mensaje XML entrante en [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)].<br /><br /> Excepción general|String|-Rechazado<br />-InvalidDigitalSignature<br />-El tiempo de espera<br />-InvalidWorkFlow<br />-Excepción general<br />-CantRepairIn[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]|Establecer la orquestación de reparación de mensajes y nuevo envío después de error en el proceso.|  
  
## <a name="see-also"></a>Vea también  
 [Propiedades promocionadas, A4SWIFT_ *](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)   
 [Propiedades promocionadas de conciliación de respuesta FIN](../../adapters-and-accelerators/accelerator-swift/fin-response-reconciliation-promoted-properties.md)