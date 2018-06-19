---
title: Arquitectura de seguridad del adaptador de FileAct | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5faeebd6-5287-4ac4-a1db-e3c055d323d2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ed8352b788af12fd3c38f489e9ddb65d8375f2a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222796"
---
# <a name="fileact-adapter-security-architecture"></a>Arquitectura de seguridad del adaptador de FileAct
Seguridad para la transmisión de archivos y la recepción se implementa mediante las características de certificado y clave criptográfica inherentes en SNL y el SAG.  La administración de certificados, etc., es completamente fuera del ámbito del adaptador de FileAct. Siempre y cuando la instancia asociada de SNL/SAG se registra para el servicio de FileAct con SWIFT y el software está instalado correctamente en SNL/SAG, el adaptador hace uso de la a través de instalaciones las API de SNL. El adaptador de FileAct siempre establecerá el FACryptoMode en "Advanced" (se recomienda).  
  
> [!NOTE]
>  Para el adaptador, puede crear un contexto de seguridad independientes para cada puerto de envío.  
  
## <a name="see-also"></a>Vea también  
 [Arquitectura del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)   
 [Primitivas de extremo a extremo de FileAct adaptador en tiempo real](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md)   
 [Primitivos locales de FileAct adaptador en tiempo real](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md)   
 [Almacenamiento de adaptador FileAct y reenvío](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md)   
 [Archivo de adaptador FileAct e identificación de transferencia](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md)   
 [Transferencia de información de soporte de adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md)   
 [Notificación de entrega del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)   
 [Estado del adaptador de FileAct supervisión](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)