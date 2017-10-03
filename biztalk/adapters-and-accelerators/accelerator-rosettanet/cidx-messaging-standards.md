---
title: "CIDX mensajería estándares | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CIDX, RosettaNet
- RosettaNet, CIDX
ms.assetid: 6f70fa56-1fc3-4016-ac9e-6af18026292a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d37cd02f92a8a13857071d0b3d84ab40c480787
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="cidx-messaging-standards"></a>Estándares de mensajería CIDX
CIDX (intercambio de datos de la industria química) funciona como una organización de estándares que admite y mantiene las normas europeas de química intercambio de mensajes estándar de. Las compañías en la industria química utilizan estos estándares para sus necesidades de mensajes específicos del sector.  
  
 CIDX ha adoptado el RosettaNet Implementation Framework (RNIF) en la capa de mensajería para habilitar el intercambio de documentos XML. CIDX no ha adoptado la capa de proceso público de los estándares RNIF.  
  
 Normas europeas de química definen definiciones de tipo de documento XML (DTD) que describen el contenido del servicio de un mensaje que intercambian los sistemas. El mensaje es igual que un objeto de RNIF 1.1 RosettaNet de estructura, con las diferencias en el contenido del servicio y algunos valores de encabezado. Cuando hay una correspondencia entre los estándares CIDX y mensajes de RosettaNet, el estándar CIDX adopta las estructuras de datos y nombres de elemento de RosettaNet.  
  
 CIDX tradicionalmente ha utilizado el intercambio de documentos electrónicos (EDI) para el intercambio de mensajes, pero ha formado un nuevo conjunto de documentos en función de las tecnologías XML. Normas europeas de química proporcionan las réplicas XML de mensajes EDI.  
  
 Normas europeas de química crear mensajes individuales para cada transacción comercial. Normas europeas de química usan dos tipos de las respuestas del mensaje: técnicas respuestas y las respuestas de la transacción. Para la mensajería confiable y segura, normas europeas de química solo usar procesos de tipo de notificación de RNIF 1.1. Normas europeas de química no utilizan 0A1 de proceso de interfaz de socio (PIP).  
  
## <a name="cidx-and-rosettanet-differences"></a>CIDX y diferencias de RosettaNet  
 En la tabla siguiente muestra algunas de las diferencias entre RosettaNet y CIDX.  
  
|Implementación de RosettaNet|Implementación de CIDX|  
|-------------------------------|-------------------------|  
|RosettaNet utiliza "Application/x-RosettaNet" como el tipo Extensiones multipropósito de correo Internet (MIME).|CIDX utiliza "Application/x-ChemXML" como el tipo MIME.|  
|Para los encabezados de RosettaNet, RosettaNet utiliza GlobalAdministeringAuthorityCode = RosettaNet|CIDX usa GlobalAdministeringAuthorityCode = CIDX|  
|RosettaNet admite mensajes de acción única y de doble acción.|CIDX admite solo los mensajes de acción única.|  
|RosettaNet admite PIP 0A1 (notificación del error).|CIDX no admite PIP 0A1.|  
|Mensajes de RosettaNet pueden ser de transacciones o notificación de tipo.|Todos los mensajes CIDX son del tipo de notificación.|  
|En RosettaNet, debe derivar valores de configuración de PIP de las especificaciones de PIP.|En CIDX, debe derivar valores de configuración de PIP de las especificaciones de normas europeas de química CIDX.|  
  
## <a name="see-also"></a>Vea también  
 [RosettaNet y CIDX estándares de mensajería](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md)   
 [Estándar RNIF](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md)   
 [PIP de RosettaNet](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md)   
 [Compatibilidad con CIDX](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md)