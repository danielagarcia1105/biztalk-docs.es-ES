---
title: "Aplicación de cliente de adaptador interAct | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cdab4624-0fc2-42a3-9867-8f77e144b40c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dac8f459799f59b63976c29f4a87dfe22b56e7ac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="interact-adapter-client-application"></a>Aplicación de cliente de adaptador interAct
Interactuar adaptador aplicación cliente solicite mensajes son documentos XML que se pasan de la aplicación de cliente para el vínculo de SWIFTNet de lado cliente (SNL). Se producen mensajes de este tipo como la primera parte de las primitivas de solicitud/respuesta que SWIFTNet ejecutado en el cliente.  
  
 Este tema describe el mensaje SwInt:ExchangeRequest. Se usa para las llamadas de cliente "sincrónicas" para SWIFTNet. En este contexto, "sincrónico" significa que la llamada de función bloquea la aplicación cliente, forzando que debe esperar hasta que se reciba la respuesta de la aplicación de servidor. (O, alternativamente, se produce una condición de error y dicho error se notifica de nuevo al cliente.)  
  
 Los bloques de cifrado (SwSec:Crypto), si los hay, contienen los resultados de la firma del mensaje o procesamiento de comprobación. Además, en determinadas fases de procesamiento, pueden contener instrucciones que le indiquen procesamiento criptográfico que se pueden realizar por el SNL.  
  
## <a name="interact-adapter-payload-format"></a>Interactuar formato de carga del adaptador  
 La carga de solicitud contiene la sustancia del mensaje de negocio. La estructura de la carga debe cumplir los requisitos de XML con formato correcto (esto simplemente significa que la carga no interrumpe el análisis de XML, pero por lo tanto, no es necesario que use la estructura del documento XML). Si se aplica la validación del mensaje SWIFTNet, hay otros requisitos estructurales en el que debe cumplir la carga. Aparte de esto, la estructura de carga y el contenido se determina mediante la aplicación de negocios.  
  
## <a name="see-also"></a>Vea también  
 [Interactuar de arquitectura de adaptador](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [Componentes de adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [Interactuar mensajes del adaptador para el intercambio de negocios](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [Aplicación de servidor del adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [Interactuar el adaptador de almacenamiento y reenvío](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [Arquitectura de seguridad del adaptador de interactuar](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [Interactuar entrega confiable de adaptador-to-End](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [Estado del adaptador de interactuar de supervisión](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)   
 [Interactuar sin repudio de adaptador](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)