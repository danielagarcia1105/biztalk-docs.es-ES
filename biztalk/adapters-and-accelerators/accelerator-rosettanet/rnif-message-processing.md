---
title: Procesamiento de mensajes RNIF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RosettaNet Implementation Framework (RNIF)
- RosettaNet, about RosettaNet
- RNIF
- RNIF, non-repudiation
- RNIF, BizTalk Accelerator for RosettaNet
- non-repudiation
- RNIF, about RNIF
- BizTalk Accelerator for RosettaNet, RNIF
- RosettaNet
ms.assetid: 994f15bc-765c-4220-8ab1-176919e9e821
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 810f673b9ae2cf9c6e1b64ccab6a6a541118cbca
ms.sourcegitcommit: 436ebffd959a9c4bdaafd4da9a5843c59a018eb7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2018
ms.locfileid: "34855527"
---
# <a name="rnif-message-processing"></a>Procesamiento de mensajes RNIF
La organización RosettaNet define el intercambio de mensajes en las especificaciones de RosettaNet Implementation Framework (RNIF). RNIF define cómo sistemas de integración transportan los mensajes. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] implementa por completo las especificaciones de RNIF, agregar esta funcionalidad a lo que [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] proporcionan de forma nativa de cuadro.  
  
Las comunicaciones de RNIF son complejas. Los procesos públicos que realizan el procesamiento de RNIF incluyen una serie de comprobaciones de validación y la lógica de flujo de trabajo complejo. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] proporciona esta funcionalidad de forma nativa. Esto le permite usar un sistema compatible con RosettaNet sin desarrollar o mantener la lógica RNIF desde el principio.  
  
## <a name="btarn-support-for-rnif"></a>Compatibilidad con BTARN RNIF  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] es compatible con ambas versiones de RNIF: RNIF 1.1 y RNIF 2.0 (V02.00.01). RNIF 2.0 agrega funciones no compatibles con RNIF 1.1, incluido el cifrado, los datos adjuntos y transacciones sincrónicas. RNIF 2.0 no es compatible con RNIF 1.1.  
  
> [!NOTE]
>  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] es compatible con RosettaNet listo RNIF 2.0.  
  
Las dos versiones definen los mensajes de RosettaNet de manera diferente. Para obtener más información acerca de los contenedores de mensajes diferente, consulte [RNIF estándar](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md).  
  
Sistemas de integración realizan la transferencia RNIF con HTTP/HTTPS y SMTP; Sin embargo, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] implementa sólo HTTP/HTTPS. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] no admite datos adjuntos y las transacciones sincrónicas en RNIF 1.1.  
  
### <a name="non-repudiation"></a>Sin repudio  
El estándar RNIF incluye un requisito para sin repudio. Esto implica almacenar el formato de los mensajes recibidos o enviados mediante [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] en una base de datos sin repudio, por lo que se puede demostrar legalmente que ha recibido o enviado. Para este propósito, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] utiliza la tabla MessageStorageIn en la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]archivar la base de datos para los mensajes entrantes y la tabla MessageStorageOut de la misma base de datos para los mensajes salientes.  
  
Se establecen sin repudio requisitos para el contenido de servicio y para las confirmaciones por separado en el perfil de configuración de proceso. Si establece uno o ambos de la **sin repudio del origen y del contenido** y **sin repudio necesario** opciones para `True`, a continuación, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] se almacenarán los datos siguientes:  
  
|data|Contenido|  
|----------|--------------|  
|RecordID|Propiedad Id. único del mensaje almacenado|  
|MessageCategory|(0) de la solicitud, respuesta (1) o señal (2)|  
|DestinationParty|Nombre de la entidad de destino|  
|SourceParty|Nombre de la entidad de origen|  
|PIPCode|Por ejemplo, PIP3A4|  
|PIPVersion|Por ejemplo, V02.00|  
|MessageContent|Mensaje en formato binario|  
|MessageTrackingID|Identificador del mensaje de seguimiento de mensajes|  
|PIPInstanceID|Id. de instancia PIP del proceso|  
  
## <a name="see-also"></a>Vea también  
 [Lo que agrega el Acelerador de BizTalk para RosettaNet a BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md)   
 [Implementación de PIP](../../adapters-and-accelerators/accelerator-rosettanet/pip-implementation.md)
