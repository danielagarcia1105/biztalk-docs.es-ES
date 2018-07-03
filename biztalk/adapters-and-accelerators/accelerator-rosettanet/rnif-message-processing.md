---
title: Procesamiento de mensajes RNIF | Microsoft Docs
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
ms.openlocfilehash: 3cda3468bfc6ada0ca9a4088fca5efc6c6d365f1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991437"
---
# <a name="rnif-message-processing"></a>Procesamiento de mensajes RNIF
La organización RosettaNet define el intercambio de mensajes en las especificaciones de RosettaNet Implementation Framework (RNIF). RNIF define cómo los sistemas de integración transportan los mensajes. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] totalmente implementa las especificaciones de RNIF, agregar esa funcionalidad en lo que Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] proporciona de forma nativa de fábrica.  
  
Las comunicaciones de RNIF son complejas. Los procesos públicos que realizan el procesamiento de RNIF incluyen una serie de comprobaciones de validación y lógica de flujo de trabajo complejo. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] proporciona esta funcionalidad de forma nativa. Esto le permite usar un sistema compatible con RosettaNet sin desarrolla o mantiene la lógica RNIF desde cero.  
  
## <a name="btarn-support-for-rnif"></a>Compatibilidad con BTARN RNIF  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] es compatible con ambas versiones de RNIF: RNIF 1.1 y RNIF 2.0 (V02.00.01). RNIF 2.0 agrega funciones no compatibles con RNIF 1.1, incluido el cifrado, los datos adjuntos y transacciones sincrónicas. RNIF 2.0 no es compatible con RNIF 1.1.  
  
> [!NOTE]
>  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] ¿es compatible con RosettaNet listo RNIF 2.0.  
  
Las dos versiones definen el mensaje de RosettaNet de forma diferente. Para obtener más información acerca de los contenedores de mensajes diferentes, consulte [estándar RNIF](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md).  
  
Sistemas de integración realizan la transferencia RNIF a través de HTTP/HTTPS y SMTP; Sin embargo, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] implementa sólo HTTP/HTTPS. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] no admite datos adjuntos y las transacciones sincrónicas en RNIF 1.1.  
  
### <a name="non-repudiation"></a>Sin repudio  
El estándar RNIF incluye un requisito para el no rechazo. Esto implica almacenar el formato de cualquier mensaje recibido o enviado por [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] en una base de datos sin repudio, por lo que puede resultar legalmente que ha recibido o enviado. Para este propósito, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] utiliza la tabla MessageStorageIn en la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]archivar la base de datos para los mensajes entrantes y la tabla MessageStorageOut de la misma base de datos para los mensajes salientes.  
  
Se establecen sin repudio requisitos para el contenido de servicio y las confirmaciones por separado en el perfil de configuración de proceso. Si establece uno o ambos de la **sin repudio del origen y del contenido** y **sin repudio necesario** opciones para `True`, a continuación, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] se almacenarán los datos siguientes:  
  
|data|Contenido|  
|----------|--------------|  
|RecordID|Su propiedad Id. único del mensaje almacenado|  
|MessageCategory|Solicitud (0), la respuesta (1) o señal (2)|  
|DestinationParty|Nombre de la entidad de destino|  
|SourceParty|Nombre de la entidad de origen|  
|PIPCode|Por ejemplo, PIP3A4|  
|PIPVersion|Por ejemplo, V02.00|  
|Elemento MessageContent|Mensaje en formato binario|  
|MessageTrackingID|Identificador del mensaje de seguimiento de mensajes|  
|PIPInstanceID|Id. de instancia PIP del proceso|  
  
## <a name="see-also"></a>Vea también  
 [Qué agrega el Acelerador de BizTalk para RosettaNet a BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md)   
 [Implementación de PIP](../../adapters-and-accelerators/accelerator-rosettanet/pip-implementation.md)
