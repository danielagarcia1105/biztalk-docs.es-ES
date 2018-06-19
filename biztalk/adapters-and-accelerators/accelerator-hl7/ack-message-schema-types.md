---
title: Tipos de esquema de mensaje de confirmación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, ACK schemas
- acknowledgements, ACK schema types
- ACK messages
ms.assetid: da6981a0-a70a-481e-8db4-4a6851f205f1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09537a9fda34ee1148e3e4d880f17f35f83f761c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25960962"
---
# <a name="ack-message-schema-types"></a>Tipos de esquema de mensaje de confirmación
Esquemas de mensaje de confirmación tienen dos formas:  
  
-   **General confirmación (ACK)**. Puede usar una confirmación (ACK) general en el que la aplicación no define un mensaje de confirmación de nivel de aplicación de línea de negocio especial o se produjo un error que impide el procesamiento de la aplicación. También puede utilizarlo para aceptar confirmaciones de nivel. La tabla siguiente muestra la estructura del mensaje de confirmación.  
  
    |Confirmación ^ varía ^ confirmación|Confirmación general|Capítulo|  
    |--------------------|----------------------------|-------------|  
    |MSH|Encabezado de mensaje|2|  
    |MSA|Confirmación de mensajes|2|  
    |[ERROR]|Error|2|  
  
-   **Retrasa la confirmación (MCF)**. Este mensaje solamente existe por compatibilidad con versiones anteriores con HL7 versión 2.1. Se utiliza como parte del protocolo que se crea un formulario genérico de una confirmación de nivel de aplicación asincrónica, el mensaje MCF. La tabla siguiente muestra la estructura del mensaje MCF.  
  
    |MCF ^ varía ^ confirmación|Confirmación diferida|Capítulo|  
    |--------------------|----------------------------|-------------|  
    |MSH|Encabezado de mensaje|2|  
    |MSA|Confirmación de mensajes|2|  
    |[ERROR]|Error|2|  
  
 Mensajes de confirmación tienen el MSH9 campo establecido como **confirmación ^\<***eventos de desencadenador***\>^ confirmación** o **MCF ^\<**  *eventos de desencadenador***\>^ confirmación**. Como resultado, el primer componente de MSH9 es suficiente para determinar el esquema de confirmación. Nombre del documento que la [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) utilizan canalizaciones siempre contiene HL7 como el espacio de nombres. El nombre de tipo es el contenido del campo MSH9_1, que es la confirmación o MCF. Como resultado, como se muestra en el ejemplo anterior, el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] canalización busca un esquema con los nombres de HL7. Confirmación o HL7. MCF, dependiendo del valor del campo MSH9_1. El esquema para el cuerpo del mensaje es el mismo para todos los mensajes de la versión 2.X.  
  
> [!NOTE]
>  En un lote en / lote escenario de confirmación, el contenido del encabezado de confirmación es como sigue:  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]establece MSH1, 2, 8 y 15 para configurar en la interfaz de usuario.  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]establece MSH7 a la hora del sistema.  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]MSH9 se establece en confirmación.  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]establece MSH12 2.4 o 2.5.  
  
## <a name="see-also"></a>Vea también  
 [Creación y procesamiento de confirmaciones](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [Segmento de confirmación del mensaje](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md)   
 [Cómo configurar un puerto de envío para recibir mensajes de confirmación](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)   
 [Condiciones de error de confirmación](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-error-conditions.md)