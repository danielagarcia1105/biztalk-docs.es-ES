---
title: Arquitectura de seguridad del adaptador de FileAct | Microsoft Docs
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
ms.openlocfilehash: be9997dca0a4b7a5c619848e4ed38cf9099bbc16
ms.sourcegitcommit: be6273d612669adfbb9dc9208aaae0a8437d4017
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2018
ms.locfileid: "52826380"
---
# <a name="fileact-adapter-security-architecture"></a>Arquitectura de seguridad del adaptador de FileAct
Seguridad para la transmisión de archivos y la recepción se implementa mediante las características de certificado y clave criptográfica inherentes SNL y el SAG.  La administración de certificados, etc., está completamente fuera del ámbito del adaptador de FileAct. Siempre que la instancia asociada de SNL/SAG está registrada para el servicio de FileAct con SWIFT y el software está instalado correctamente en SNL/SAG, el adaptador realiza el uso de las funciones a través de la API de SNL. El adaptador de FileAct siempre establecerá el FACryptoMode en "Advanced" (recomendado).  
  
> [!NOTE]
>  Para el adaptador, puede crear un contexto de seguridad independientes para cada puerto de envío.  
  
## <a name="see-also"></a>Vea también  
 [Arquitectura del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)   
 [Primitivas to-End en tiempo real del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md)   
 [Primitivas locales en tiempo real del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md)   
 [Avance y Store de adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md)   
 [Identificación de transferencia y archivo de adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md)   
 [Transferencia de información complementaria de adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md)   
 [Notificación de entrega del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)   
 [Supervisión de estado del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)
