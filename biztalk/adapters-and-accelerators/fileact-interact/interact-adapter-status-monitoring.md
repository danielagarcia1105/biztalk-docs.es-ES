---
title: Estado del adaptador de interactuar supervisión | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2bbc6a45-8d3a-444e-b760-aef0dfa7218a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32cf2f197508c0cd703a05780804c6bc880b5f32
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224300"
---
# <a name="interact-adapter-status-monitoring"></a>Estado del adaptador de interactuar de supervisión
Vínculo de SWIFTNet (SNL-C) mantiene el estado local sobre SWIFTNet almacén y reenvíos sesiones (SnF) adquiridas en ese SNL. Para obtener la información acerca de la sesión, utilice SwCall() con el tipo primitivo siguiente:  
  
 ![Obtener información de sesión](../../adapters-and-accelerators/fileact-interact/media/b7feb4b4-de92-4bb9-bcfe-363a127d0ed2.gif "b7feb4b4-de92-4bb9-bcfe-363a127d0ed2")  
  
 Tenga en cuenta que no son necesarios para proporcionar un AuthorizationContext. Se devuelve la información que se ve el SNL local, como se muestra en la ilustración siguiente.  
  
 ![Información de estado de sesión](../../adapters-and-accelerators/fileact-interact/media/afd46393-a11d-4b4a-a66b-eba5f049f306.gif "afd46393-a11d-4b4a-a66b-eba5f049f306")  
  
## <a name="see-also"></a>Vea también  
 [Interactuar de arquitectura de adaptador](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [Componentes de adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [Interactuar mensajes del adaptador para el intercambio de negocios](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [Aplicación de cliente de adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [Aplicación de servidor del adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [Interactuar el adaptador de almacenamiento y reenvío](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [Arquitectura de seguridad del adaptador de interactuar](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [Interactuar entrega confiable de adaptador-to-End](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [Interactuar sin repudio de adaptador](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)