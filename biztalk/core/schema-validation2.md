---
title: Esquema Validation2 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2f9d1576-10df-4c5a-9ae0-618f0dd54b4e
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 317fa8e0e5e557993922bba383ebf5eca460fa69
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="schema-validation"></a>Validación de esquemas
La canalización de recepción EDI y la canalización de envío EDI validan un mensaje usando los siguientes esquemas:  
  
-   **Validación de sobres**: esquema de servicio en `Microsoft.BizTalk.Edi.BaseArtifacts.dll` en[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]  
  
-   **Validación del conjunto de transacciones**: esquemas de mensaje en el esquema de almacenamiento en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI  
  
-   **Validación del mensaje de confirmación**: CONTRL, 997 y TA1 esquema en `Microsoft.BizTalk.Edi.BaseArtifacts.dll`.  
  
 El programa de instalación implementa automáticamente los esquemas de `Microsoft.BizTalk.Edi.BaseArtifacts.dll`. Estos esquemas se enumeran en la **esquemas** nodo de la **aplicación EDI de BizTalk** en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
 Para utilizar los esquemas del mensaje, debe instalarlos en el disco duro del servidor ejecutando el archivo autoextraíble MicrosoftEdiXSDTemplates.exe de la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI y, a continuación, implementarlos en su proyecto en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
 **Determinación de esquemas**  
  
 Cuando la canalización de recepción EDI procesa un mensaje de recepción, determina el espacio de nombres del esquema que va a usarse en el procesamiento del mensaje a través del proceso de búsqueda del acuerdo y de detección de esquemas. Para obtener más información, consulte [resolución de acuerdos, detección de esquemas y autorización para los mensajes de EDI recibidos](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md).  
  
 Cuando la canalización de envío EDI crea un mensaje para enviarlo, usa las propiedades del acuerdo para rellenar el sobre y, después, realiza la validación de esquema de la información del conjunto de transacciones. Tras cargar el esquema, la canalización de envío valida el esquema con respecto a las propiedades del acuerdo (o del acuerdo de reserva si no se ha designado ningún acuerdo). Si el esquema se valida, la canalización valida el conjunto de transacciones en relación con el esquema.  
  
## <a name="see-also"></a>Vea también  
 [Validación del mensaje EDI](../core/edi-message-validation.md)