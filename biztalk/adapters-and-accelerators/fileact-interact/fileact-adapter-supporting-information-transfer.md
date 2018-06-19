---
title: Compatibilidad con la transferencia de información de adaptador de FileAct | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0fc27561-9abb-4496-9db7-f221a6c90738
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5aefba5fe85a8a275d3b2050d8c08cc98f74d06
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222820"
---
# <a name="fileact-adapter-supporting-information-transfer"></a>Transferencia de información de soporte de adaptador de FileAct
El adaptador de FileAct permite a la transferencia de información complementaria con archivos opcional. Esta información se transfiere a discreción de la aplicación. El adaptador no realiza ningún procesamiento especial de esta información en el lado de origen excepto para validar que se encuentra en el formato correcto. Los elementos que componen la información de apoyo incluyen:  
  
-   Descripción del archivo y la información de archivo  
  
-   Descripción de la transferencia y la información de transferencia  
  
-   Descripción de confirmación y la información de confirmación  
  
-   Información de descripción y el rechazo de rechazo  
  
> [!NOTE]
>  Uno de los componentes de la información de archivo define la compresión y descompresión. Compresión y descompresión son responsabilidad de la aplicación, no el adaptador.  
  
## <a name="see-also"></a>Vea también  
 [Arquitectura del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)   
 [Primitivas de extremo a extremo de FileAct adaptador en tiempo real](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md)   
 [Primitivos locales de FileAct adaptador en tiempo real](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md)   
 [Almacenamiento de adaptador FileAct y reenvío](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md)   
 [Arquitectura de seguridad del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md)   
 [Archivo de adaptador FileAct e identificación de transferencia](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md)   
 [Notificación de entrega del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)   
 [Estado del adaptador de FileAct supervisión](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)