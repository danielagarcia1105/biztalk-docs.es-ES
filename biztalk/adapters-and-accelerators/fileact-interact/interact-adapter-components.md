---
title: Componentes de adaptador interAct | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aad60b57-4cc8-44b9-98f5-e5a2ba3a41e2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e909e49713377172d01540f4c8e660756d68ed72
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224692"
---
# <a name="interact-adapter-components"></a>Componentes de adaptador interAct
El adaptador de InterAct tiene un cliente y un componente de servidor. Tenga en cuenta que puede haber una instalación de A4SWIFT (mínima) en el mismo equipo como puerta de enlace de Alliance de SWIFT (SAG) si se está ejecutando Windows Server. Tenga en cuenta también que el vínculo de SWIFTNet (SNL) pueden estar en un equipo diferente desde el SAG. El adaptador de host (API) de la interfaz proporcionada por SWIFT de programación de aplicaciones remoto se utilizan para comunicarse de A4SWIFT con SAG, independientemente de la ubicación de los componentes.  
  
 La siguiente ilustración muestra que los componentes que componen la cadena completa de adaptador y las comunicaciones relacionadas con el adaptador de InterAct residen.  
  
 ![Componentes interAct](../../adapters-and-accelerators/fileact-interact/media/cf257c5a-3668-4aff-bce9-7acc6eb672bd.gif "cf257c5a-3668-4aff-bce9-7acc6eb672bd")  
  
 En la siguiente ilustración, la aplicación cliente usa A4SWIFT y el adaptador de InterAct. BizTalk Server es el middleware, que se comunica con el adaptador de host remoto de API a través de TCP/IP.  
  
 ![Aplicación cliente interAct](../../adapters-and-accelerators/fileact-interact/media/7aeada39-6264-498b-92e8-303eb0cf369b.gif "7aeada39-6264-498b-92e8-303eb0cf369b")  
  
 En la ilustración siguiente, la aplicación de servidor utiliza A4SWIFT y el adaptador de InterAct. BizTalk Server es el middleware, que se comunica con el adaptador de host remoto de API a través de TCP/IP.  
  
 ![Aplicación del servidor interAct](../../adapters-and-accelerators/fileact-interact/media/51cbae6a-41e9-4a50-9574-5e86bc04ddba.gif "51cbae6a-41e9-4a50-9574-5e86bc04ddba")  
  
## <a name="see-also"></a>Vea también  
 [Interactuar de arquitectura de adaptador](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [Interactuar mensajes del adaptador para el intercambio de negocios](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [Aplicación de cliente de adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [Aplicación de servidor del adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [Interactuar el adaptador de almacenamiento y reenvío](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [Arquitectura de seguridad del adaptador de interactuar](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [Interactuar entrega confiable de adaptador-to-End](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [Estado del adaptador de interactuar de supervisión](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)   
 [Interactuar sin repudio de adaptador](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)